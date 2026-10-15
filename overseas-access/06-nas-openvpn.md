# 06 · Synology ya da QNAP NAS'ı hattan nasıl geçirirsiniz

NAS, evde hatta en çok ihtiyaç duyan ama en az ilgi gören cihazdır: İndirme aracının yurt dışı kaynaklara ulaşması, Docker'ın imaj çekmesi, Cloud Sync'in yurt dışı bulut depolamalarla eşitlemesi, Plex'in meta veri toplaması gerekir. NAS'ta Hiddify çalışmaz, ama Synology ve QNAP'ta yerleşik bir OpenVPN istemcisi vardır: Bu sitenin OpenVPN sayfasından bir .ovpn indirin, içe aktarın, bağlanır; açılışta da otomatik yeniden bağlanır. Bu yazı içe aktarmanın Synology'de ve QNAP'ta nerede olduğunu, kilit seçenek olan "Use default gateway"i (varsayılan ağ geçidini kullan), parolanızı değiştirdikten sonra ne yapacağınızı ve "NAS'a dışarıdan ulaşmanın" neden Özel ağ gerektiren ayrı bir iş olduğunu anlatıyor.

## Önce iki şeyi birbirinden ayırın

NAS'ın kendisini hattan geçirmek (indirme, imaj çekme, yurt dışı bulut depolamalarla eşitleme): OpenVPN kullanın; bu yazının konusu bu.

NAS'a dışarıdan ulaşmak (iş seyahatinde paylaşımları açmak, kameraları izlemek): NAS'ı ve telefonunuzu aynı özel ağa koyan Özel ağı (Tailscale) kullanın; "Çin'deki ev kameralarınızı ve NAS'ınızı yurt dışından izlemek" yazısına bakın. Bu işi Özel ağa bırakın: OpenVPN NAS'ı bizim hattımıza bağlar, Özel ağ ise sizi evinize bağlar.

## Synology

1. Bu siteye giriş yapın ve OpenVPN sayfasında bir bölgenin bayrağına tıklayarak o bölgenin .ovpn dosyasını indirin.
2. Control Panel (Denetim Masası) → Network (Ağ) → Network Interface (Ağ Arayüzü) → Create (Oluştur) → Create VPN profile (VPN profili oluştur) → OpenVPN (via importing a .ovpn file) (.ovpn dosyası içe aktararak); bu sitedeki hesap e-postanızı ve parolanızı girin.
3. "Use default gateway" (varsayılan ağ geçidini kullan): İşaretliyse NAS'ın tüm giden trafiği hattan geçer (indirmeler, Docker ve Cloud Sync'in hepsi bundan yararlanır); işaretsizse yalnızca tünel kurulur ve giden trafik yine yerelden çıkar. Neredeyse her durumda işaretli olmalıdır.
4. NAS yeniden başladıktan ya da hat dalgalandıktan sonra kendiliğinden toparlanması için "Reconnect when the VPN connection is lost" (VPN bağlantısı koptuğunda yeniden bağlan) seçeneğini işaretleyin. Bağlanın, ardından bir pakette bir kez çekme işlemi deneyin.

## QNAP

1. .ovpn dosyasını aynı şekilde indirin.
2. QVPN Service → VPN Client (VPN istemcisi) → Add (Ekle) → OpenVPN; dosyayı içe aktarın, hesabı ve parolayı girin.
3. Bağlantı ayarlarında "Use VPN as the default gateway of the NAS" (VPN'i NAS'ın varsayılan ağ geçidi olarak kullan) ile otomatik yeniden bağlanmayı işaretleyin, sonra bağlanın.

## Hangi trafik geçer, hangisi geçmez

- Geçer: Download Station / Download Station'daki BT ve HTTP görevleri, Docker imaj çekmeleri, Cloud Sync ile Google Drive / Dropbox / OneDrive eşitlemesi, Plex ve Emby meta veri toplama ve Package Center güncellemeleri.
- Geçmez: Yerel ağ içinde sizin NAS'a eriştiğiniz trafik — zaten yerel ağın içindedir, etkilenmez.
- Çin'desiniz ve Çin sitelerinin doğrudan bağlanmasını istiyorsunuz: NAS'ta bölünmüş yönlendirme betiği yoktur; OpenVPN bağlandığında NAS'ın tüm giden trafiği hattan geçer. Çin'deki indirme kaynakları yavaşsa indirme görevlerinde Çin'deki yansı adreslerini kullanın ya da hatta yalnızca ihtiyacınız olduğunda bağlanın.

## Bilmeniz gerekenler

- Yapılandırma dosyası hesabınızı taşır; parolanızı değiştirdikten sonra NAS'taki parola alanı çalışmaz olur: .ovpn'yi yeniden indirip değiştirin ya da VPN profilinde yalnızca parolayı güncelleyin.
- Hesabın süresi dolunca NAS'ın bağlantısı kesilir; yeniledikten sonra otomatik yeniden bağlanır, yapılandırmayı değiştirmeniz gerekmez.
- NAS bir cihaz sayılır ve aynı anda çevrim içi kotasını diğer cihazlarınızla paylaşır (Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz).
- Hat UDP üzerinden çalışır; ev genişbandındaki bir NAS neredeyse hiçbir zaman UDP kısıtlamasıyla karşılaşmaz.

## SSS

**"Use default gateway"i işaretledikten sonra NAS'a yerel ağda hâlâ ulaşılabilir mi?** Evet. Yerel ağ trafiği ağ geçidinden geçmez; paylaşımlar, Plex oynatma ve yönetim sayfası hiç etkilenmez.

**NAS hattan geçtikten sonra Plex uzaktan oynatma yavaşladı mı?** Plex uzaktan oynatma NAS'ın giden trafiğini kullanır; varsayılan ağ geçidi işaretlendiğinde hattan dolaşarak gider. Uzaktan oynatma için NAS'a Özel ağ üzerinden ulaşmak daha doğrudandır; ya da OpenVPN'i yalnızca indirme yapmanız gerektiğinde bağlayın.

**Yalnızca Download Station hattan geçebilir mi?** Synology ve QNAP'ta uygulama başına bölünmüş yönlendirme yoktur. İnce ayar için Docker'da OpenVPN'li bir indirme konteyneri çalıştırın (örneğin qbittorrent + gluetun) ve yalnızca onu hattan geçirin.

**Linux tabanlı bir NAS (TrueNAS, Unraid) ne olacak?** Linux yöntemiyle yapın: openvpn paketi ve /etc/openvpn/client/ içine konan bir yapılandırma dosyası; "Bir Linux sunucuyu ve komut satırı araçlarını hattan nasıl geçirirsiniz" yazısına bakın.

## Devamı için

- [OpenVPN sayfası: istemci indirmeleri ve yapılandırma dosyaları](https://www.leotun.com/tr/openvpn?utm_source=github&utm_content=overseas-access-06)
- [OpenVPN nasıl kullanılır, ne zaman seçilmeli](https://www.leotun.com/tr/guides/openvpn-setup?utm_source=github&utm_content=overseas-access-06)
- [Çin'deki ev kameralarınızı ve NAS'ınızı yurt dışından izlemek](https://www.leotun.com/tr/guides/home-camera?utm_source=github&utm_content=overseas-access-06)
- [Bir Linux sunucuyu ve komut satırı araçlarını hattan nasıl geçirirsiniz](https://www.leotun.com/tr/guides/linux-server?utm_source=github&utm_content=overseas-access-06)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/nas-openvpn?utm_source=github&utm_content=overseas-access-06

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=overseas-access-06) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=overseas-access-06) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
