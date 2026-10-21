# 05 · Bir Linux sunucuyu ve komut satırı araçlarını hattan nasıl geçirirsiniz

Linux'ta hatta giden iki yol var; ihtiyaca göre seçin. Bilgisayarın tamamını geçirmek için (Docker imajları çekmek, yurt dışı ağ gerektiren servisleri çalıştırmak, gözetimsiz çalışma) OpenVPN kullanın: /etc/openvpn/client/ içine konan ve açılışta başlatılan tek bir yapılandırma dosyası. Yalnızca birkaç komutu geçirmek için (git, pip, npm, curl) Web Proxy kullanın: Proxy adresini http_proxy ortam değişkenine yazın, geri kalan trafiğe dokunulmaz. Masaüstü Linux'ta NetworkManager'a da içe aktarabilirsiniz. Bu yazı üçünü de, parola dosyasının nasıl yazılacağı ve doğrulama komutlarıyla birlikte anlatıyor.

## Birinci yol: bilgisayarın tamamı hattan (OpenVPN)

1. İstemciyi kurun: Debian / Ubuntu sudo apt install openvpn, Fedora sudo dnf install openvpn, Arch sudo pacman -S openvpn.
2. Bu siteye giriş yapın ve OpenVPN sayfasında .ovpn'i indirmek için bir bölgenin bayrağına tıklayın. Linux'a verilen yapılandırmada hesap ve parola hazır gelmez (NetworkManager kimlik bilgileri gömülü dosyaları kabul etmez); bu yüzden ayrı bir parola dosyası oluşturun: iki satır, ilki bu sitedeki e-postanız, ikincisi parolanız; chmod 600.
3. .ovpn'i /etc/openvpn/client/<bölge>.conf olarak kopyalayın ve dosyadaki auth-user-pass satırının sonuna parola dosyasının yolunu ekleyin.
4. sudo systemctl enable --now openvpn-client@<bölge>. Durumu systemctl status openvpn-client@<bölge> ile kontrol edin ve curl -s https://ipinfo.io/country komutunun seçtiğiniz bölgeyi gösterdiğini doğrulayın.
5. Bölge değiştirmek için başka bir yapılandırma indirip başka bir birimi etkinleştirin; aynı anda yalnızca birini çalıştırın.

## İkinci yol: yalnızca komut satırı araçları hattan (Web Proxy)

Bu sitenin Proxy sayfasında verilen proxy adresi, hesabınız ve parolanızla birlikte doğrudan ortam değişkenlerine yazılabilir: export https_proxy=https://username:password@proxy-address export http_proxy=$https_proxy. Paroladaki özel karakterler URL kodlamasıyla yazılmalıdır. Bundan sonra bu terminalde curl, wget, git, pip ve npm hattan geçer; diğer programlar etkilenmez.

Docker servisi kabuk ortam değişkenlerini okumaz; ayarı /etc/systemd/system/docker.service.d/proxy.conf dosyasındaki Environment= satırına yazıp docker'ı yeniden başlatın. apt için /etc/apt/apt.conf.d/proxy.conf dosyasına Acquire::https::Proxy yazın.

Bu yolda tasarım gereği kopacak bir bağlantı yoktur; root yetkisi gerekmez ve yönlendirmeleri değiştirmez. Şirket sunucularına ve yalnızca indirmeleri hızlandırmak istediğiniz durumlara uygundur; yalnızca proxy değişkenlerine uyan programlar için geçerlidir, geri kalan trafiğe dokunulmaz.

## Üçüncü yol: masaüstü Linux'ta NetworkManager

1. network-manager-openvpn-gnome'u kurun (bu sitenin OpenVPN sayfasındaki tek tık yazılım merkezini açabilir).
2. Ayarlar → Ağ → VPN → "+" → Dosyadan içe aktar; .ovpn'i seçin, bu sitedeki e-postanızı ve parolanızı girip kaydedin.
3. VPN'i üst çubuktan ya da sistem tepsisinden açıp kapatın. Açılışta otomatik bağlanması için kablolu/kablosuz bağlantının ayarlarında "VPN'e otomatik bağlan"ı işaretleyin.

## Doğrulama ve sorun giderme

- Çıkışı kontrol edin: curl -s https://ipinfo.io çıktısındaki ülke seçtiğiniz bölgedir.
- DNS'i kontrol edin: resolvectl status çıktısında VPN arayüzünün DNS'i hattın gönderdiği DNS olmalıdır; sızıntı varsa yapılandırmaya dhcp-option DNS ekleyin ya da update-systemd-resolved betiğini kullanın.
- AUTH_FAILED: Parola dosyası yanlış ya da hesabın süresi dolmuş; parolanızı değiştirdiyseniz parola dosyasını güncelleyin.
- TLS el sıkışması zaman aşımı: Sunucuya giden UDP geçmiyor; bölge ya da ağ değiştirin. Bulut sunucusunda güvenlik grubu dışarı giden UDP'ye izin vermelidir.
- Sunucu Çin'de ve Çin kaynaklarının doğrudan bağlanması gerekiyor: OpenVPN bağlandıktan sonra dışarı giden tüm trafik hattan geçer. apt / pip / npm kaynaklarını Çin aynalarına çevirin ya da yalnızca belirli komutların hattan geçmesi için ikinci yolu kullanın.

## Bilmeniz gerekenler

- Bir Linux makinesi bir cihaz sayılır ve aynı anda çevrim içi kotasını diğer cihazlarınızla paylaşır (Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz); ikinci yoldaki Web Proxy bağlantı başına sayılır ve bu kotaya dahildir.
- Yapılandırma dosyası ve parola dosyası hesabınızla aynı değerdedir; bunları bir git deposuna göndermeyin ya da bir imajın içine koymayın.
- Parolanızı değiştirdikten sonra eski yapılandırma anında çalışmaz olur; bu, tasarım gereği iptal mekanizmasıdır. Parola dosyasını güncellemeniz yeterlidir.
- Hattı bir bulut sunucusunda çalıştırırken sağlayıcının kullanım koşullarına uyun; hat yalnızca bağlantı süresini ve toplam trafiği kaydeder.

## SSS

**Linux yapılandırmasında hesap ve parola neden hazır gelmiyor?** NetworkManager bir yapılandırmayı içe aktarırken kimlik bilgileri gömülü dosyayı kabul etmez ve içe aktarma hatası verir; bu yüzden Linux için verilen kopyada bunları kendiniz doldurursunuz. systemd yönteminde parola dosyasına yazın.

**Yalnızca Docker'ı hattan geçirebilir miyim?** Evet: Proxy değişkenlerini yalnızca Docker servisi için ayarlayın (ikinci yol) ya da içinde OpenVPN çalışan bir konteyner (gluetun) kullanarak belirli konteynerleri hattan geçirin.

**Linux'ta Özel ağ (Tailscale) nasıl?** Resmî betik tek satırda kurar, tailscale up --login-server=<bu sitenin kontrol sunucusu> ile giriş yapılır. Bu makineye dışarıdan ulaşmanız gerektiğinde ya da bir kez kurup sürekli çevrim içi kalmasını istediğinizde uygundur; yalnızca indirmeleri hızlandırmak için OpenVPN ya da proxy daha basittir.

**Router'daki OpenWrt için de aynı mı?** OpenWrt'de luci-app-openvpn'i kurup .ovpn'i yükleyin, tüm yerel ağ hattan geçer; bu sitenin yazılımı yüklü bir router'da buna gerek yoktur, hesabınıza giriş yapmanız yeterli.

## Devamı için

- [OpenVPN sayfası: istemci indirmeleri ve yapılandırma dosyaları](https://www.leotun.com/tr/openvpn?utm_source=github&utm_content=overseas-access-05)
- [OpenVPN nasıl kullanılır, ne zaman seçilir](https://www.leotun.com/tr/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-05)
- [Synology ya da QNAP NAS'ı hattan nasıl geçirirsiniz](https://www.leotun.com/tr/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-05)
- [Web Proxy nedir, ne zaman kullanılır](https://www.leotun.com/tr/guides/web-proxy?utm_source=github&utm_content=overseas-access-05)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/linux-server?utm_source=github&utm_content=overseas-access-05

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=overseas-access-05) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=overseas-access-05) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerlidir
