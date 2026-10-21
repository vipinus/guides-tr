# 04 · OpenVPN: .ovpn profilini indirin, içe aktarın, bağlanın; router, NAS ve Linux'ta da çalışır

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/openvpn-setup?utm_source=github&utm_content=client-04

OpenVPN köklü, açık kaynaklı bir protokoldür; neredeyse her işletim sistemi, router yazılımı ve NAS onun için bir istemciyle gelir. LeoTun'un profil dosyaları hesabınızı, parolanızı ve şifreleme bilgilerini zaten içerir; içe aktarır aktarmaz bağlanabilirsiniz. Telefon ve bilgisayarda günlük kullanım için AnyConnect ya da Hiddify daha az uğraştırır; OpenVPN'in asıl değeri **yalnızca OpenVPN kabul eden yerlerdedir**: OpenWrt router'lar, Synology / QNAP NAS'lar, Linux sunucular ve eski cihazlar.

## Üç adım

1. [Sitedeki OpenVPN sayfasındaki](https://www.leotun.com/tr/openvpn?utm_source=github&utm_content=client-04) tablodan sisteminize uygun istemciyi kurun (her platformda resmî OpenVPN Connect var; Windows'ta OpenVPN GUI, macOS'ta Tunnelblick de kullanabilirsiniz).
2. Giriş yaptıktan sonra o bölgenin .ovpn dosyasını indirmek için bir bölgenin **bayrağına tıklayın**. Her bölge için bir dosya vardır.
3. Dosyayı istemcide açın ve bağlanın.

| Platform | Notlar |
|---|---|
| Windows / macOS / Android / iOS | Profilde hesap ve parola hazır; içe aktarın ve bağlanın |
| Linux | Sistemin VPN ayarları → dosyadan içe aktar; ilk bağlantıda sitedeki e-postanızı ve parolanızı girin. Komut satırı: `openvpn --config file`; açılışta başlaması için `/etc/openvpn/client/` içine koyun |
| OpenWrt router | luci-app-openvpn'i kurun, .ovpn'i yükleyip etkinleştirin; bu sitenin yazılımı yüklüyse gerekmez |
| Synology NAS | Control Panel → Network → Network Interface → Create → VPN → OpenVPN (Denetim Masası → Ağ → Ağ Arayüzü → Oluştur; .ovpn'i içe aktarın); NAS'ın dışarı giden trafiğini hattan geçirmek için "Use default gateway on remote network"ü (uzak ağdaki varsayılan ağ geçidini kullan) işaretleyin |
| QNAP NAS | QVPN → VPN Client → Add → OpenVPN, içe aktarın |

## Çin'deki kullanıcılar: Çin sitelerine doğrudan bağlantı

Bağlandıktan sonra Çin sitelerine giden trafik dolambaçlı yoldan gider. Sitede bir "Çin doğrudan yönlendirme aracı" var: Çift tıklayıp çalıştırın; Çin IP'leri doğrudan bağlanır, geri kalan her şey hattan geçer. Hem Cisco hem OpenVPN ile çalışır. Çin dışındaki kullanıcılar bunu kullanmamalı.

## Bağlanmıyorsa bu sırayla kontrol edin

| Günlükteki anahtar kelime / belirti | Nedeni | Ne yapmalı |
|---|---|---|
| AUTH_FAILED | Hesap ya da parola yanlış veya süresi dolmuş | Siteye giriş yapıp bitiş tarihine bakın; parolanızı değiştirdiyseniz profili yeniden indirin |
| Önce UDP zaman aşımına uğruyor, sonra TCP üzerinden bağlanıyor | Bulunduğunuz ağ UDP'yi kısıtlıyor ve otomatik olarak TCP'ye düşüldü | Kullanılabilir ama daha yavaş; çok yavaşsa ağ değiştirin ya da AnyConnect kullanın |
| Hem UDP hem TCP "TLS handshake failed" / "key negotiation failed" veriyor | Sunucuya giden ağ yolu kapalı | Bölge ya da ağ değiştirin |
| İçe aktarırken hata | İstemci çok eski (OpenVPN 2.5 öncesi) | İstemciyi güncelleyin |
| Bağlıyken birden kopuyor | Hesabın süresi doldu ve sunucu bağlantınızı kesti | Yenileyip yeniden bağlanın; profili değiştirmeniz gerekmez |

## UDP mi TCP mi

İkisi de mevcut, seçim yapmanız gerekmez. Profilde UDP önce geldiği için istemci önce UDP'yi dener; UDP kısıtlıysa ya da bağlanamıyorsa birkaç saniye sonra otomatik olarak TCP'ye geçer. UDP'nin gecikmesi daha düşüktür ve daha hızlıdır; TCP yalnızca yedektir ve sınır ötesinde belirgin şekilde daha yavaştır. UDP'yi kalıcı olarak kısıtlayan ağlarda (bazı kampüs ve şirket ağları) doğrudan AnyConnect kullanmanızı öneririz.

> 15 Eylül 2026'dan önce indirilen profiller yalnızca UDP içerir; otomatik geçiş istiyorsanız yeniden indirin.

## Güvenlik

Profil dosyası hesabınızı ve parolanızı içerir, yani hesabın kendisiyle aynı değerdedir; başkasına vermeyin. Sızarsa sitede parolanızı değiştirin, eski dosya anında çalışmaz olur. El sıkışmanın kendisi de şifrelidir: Profildeki anahtar olmadan el sıkışma başlatılamaz bile ve sunucu tarayıcılara görünmez.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-04) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-04) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
