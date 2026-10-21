# 10 · Dropbox ve diğer yazılımlar HTTP / SOCKS proxy istediğinde

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/app-proxy?utm_source=github&utm_content=client-10

**Önce mevcut durum: Proxy şifreli olmak zorunda.** Şifresiz proxy'ler (düz HTTP, SOCKS4, SOCKS5) Çin'deki ağlarda tespit edilir ve bunlara müdahale edilir; kısa süre sonra bağlantı yavaşlar ya da kopar, üstelik hesap adı ve parola da açık metin olarak gider. Uzun vadede yalnızca şifreli bağlantılar kullanılabilir kalır; bu yüzden bu sitenin Web Proxy'si baştan sona şifreli bağlantı kullanır. **Yalnızca HTTP / SOCKS5 kabul eden yazılımlar için bilgisayarın tamamını Hiddify'a devredin** (aşağıya bakın).

Dropbox, Telegram Desktop, Steam, bulut disk istemcileri ve geliştirici araçları gibi bağımsız yazılımlar tarayıcının ayarlarını okumaz; kendi proxy ayarları da yalnızca şifresiz HTTP / SOCKS5 kabul eder. İki taraf birbirine uymadığı için bir proxy girmek bağlantıyı sağlamaz. Çözüm **proxy girmemektir**: Hiddify ile bilgisayarın tamamını hattan geçirin ve yazılımdaki proxy ayarını "Proxy yok" yapın.

## Proxy girdikten sonra neden yine bağlanmıyor

| Nedeni | Açıklama |
|---|---|
| Tür uyuşmazlığı | Yazılım yalnızca HTTP, SOCKS4 ve SOCKS5 sunar, hiçbiri şifreli değil; bu sitenin proxy'si şifreli olmak zorunda olduğundan buraya girilemez |
| İnternette bulunan şifresiz bir proxy | Bir süre bağlanır, sonra müdahaleye uğrar ve ancak arada bir çalışır |
| Trafiğin yalnızca bir kısmını kapsar | Birçok yazılımda proxy'yi yalnızca giriş ve eşitleme kullanır; güncellemeler, aramalar ve yerel ağ eşitlemesi doğrudan bağlanmaya devam eder. HTTP proxy oyunların ve aramaların UDP trafiğini hiç iletmez |
| Her programda ayrı ayrı yönetilir | Bölge ya da parola değişince hepsini tek tek değiştirmeniz gerekir; unuttuğunuz hangisiyse o çalışmaz olur |

## Önerilen yol: bilgisayarın tamamını Hiddify'a devredin

1. Hiddify'ı [09 · Hiddify'ı her platforma kurmak](09-hiddify-install-all-platforms.md) yazısına göre kurun, profili de [02](02-singbox-subscription-links.md) yazısına göre içe aktarın.
2. "VPN" modunda (varsayılan) bağlanın. Windows'ta ilk bağlantı yönetici yetkisi ister.
3. Yazılımdaki proxy ayarını "Proxy yok"a geri alın: Dropbox'ta "Preferences → Network → Proxies" (Tercihler → Ağ → Proxy'ler) altında "No proxy" ya da "Auto-detect"i seçin; Telegram Desktop'ta "Settings → Advanced → Connection type" (Ayarlar → Gelişmiş → Bağlantı türü) altında "Disable proxy"yi seçin. Proxy seçeneği olan diğer yazılımlarda da kapatın.
4. Doğrulayın: Dropbox'ın sistem tepsisi simgesi "Up to date" (güncel) gösterir ve eşitleme başlar; tarayıcıda IP'nizi gösteren bir sayfa açın, çıkış seçtiğiniz bölgededir.

"Otomatik yönlendirme" açıkken Dropbox gibi yurt dışı hizmetler hattan geçer; WeChat, internet bankacılığı ve Çin siteleri ise her zamanki gibi doğrudan bağlanır.

## Sık kullanılan yazılımlar

| Yazılım | Nasıl ayarlanır |
|---|---|
| Dropbox | Proxy: "No proxy" ya da "Auto-detect"; başka bir adresle "Manual"da bırakırsanız Hiddify kapanınca çevrim dışı kalır |
| Telegram Desktop | Bağlantı türü: "Disable proxy"; tünelin üstüne eklenen yerleşik MTProto / SOCKS5 yalnızca yavaşlatır |
| OneDrive, Google Drive, masaüstü iCloud | Sistemin ağ ayarlarını izler; ayarlanacak bir şey yok |
| Steam, Epic, Battle.net | Proxy gerekmez; indirmeler yavaşsa daha yakın bir bölgeye geçin |
| Zoom, Teams, Slack, Discord | Ses ve görüntü UDP'dir; bunu yalnızca bilgisayarın tamamını kapsayan bir yöntem taşır |
| VS Code, JetBrains, Cursor | Sistemin ağ ayarlarını izler; araç içinde ayrıca girilmiş proxy varsa silin |

## İstemci kuramıyorsanız (şirket bilgisayarı)

- Dropbox'ın ve bulut disklerin web sürümünü kullanın: [Web Proxy](03-web-proxy-extension.md) açıkken tarayıcıda dropbox.com'u açın; yükleme ve indirme yapabilirsiniz ama otomatik eşitleme olmaz.
- Komut satırı araçları (git, pip, npm, curl) şifreli proxy kabul eder: Web Proxy adresini `https_proxy` içine yazın; bkz. [Çin'den yurt dışı hizmetlere erişim 05 · Linux ve komut satırı](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/05-linux-server.md) (Çince).
- Yalnızca HTTP / SOCKS5 kabul eden diğer masaüstü yazılımlarını kendi bilgisayarınızda ya da telefonunuzda kullanmanız en iyisidir; bunun için şirket bilgisayarına bütün cihazı kapsayan bir VPN kurmayın, şirketin güvenlik alarmlarını tetikler.

## SSS

**Bana bir SOCKS5 ya da HTTP proxy adresi verebilir misiniz?** Bu sitenin proxy'si baştan sona şifreli bağlantı kullanır; şifresiz olanı kısa sürede ancak arada bir çalışır hâle gelir. Bilgisayarın tamamını Hiddify'a devretmek daha kararlıdır ve tüm yazılımları bir kerede kapsar.

**Hiddify açıkken yazılıma yine de proxy girmem gerekir mi?** Hayır. Girerseniz trafik iki kez dolaşır: En iyi ihtimalle yavaşlar, en kötü ihtimalle bağlanmaz.

**Telefondaki Dropbox ne olacak?** Telefon uygulamalarında proxy ayarı yoktur. Hiddify kurun ya da Cisco (AnyConnect) kullanın; bağlandıktan sonra tüm uygulamalar hattan geçer.

**Hiddify olmadan olur mu?** Evet. Cisco, Özel ağ ve OpenVPN de bilgisayarın tamamını devralır; yazılım yine "Proxy yok" olarak ayarlanır. Hiddify'ın avantajı yerleşik yönlendirmesi ve paket kaybı yüksek ağlarda daha iyi hızıdır.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-10) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-10) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
