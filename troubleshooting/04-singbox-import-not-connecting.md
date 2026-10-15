# 04 · Hiddify içe aktarıldı ama bağlanmıyor

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/singbox-subscription?utm_source=github&utm_content=troubleshooting-04

Aldığınız hatayı tabloda bulun. İçe aktarmanın kendisi için [Abonelik bağlantısı nasıl içe aktarılır (Hiddify, Clash, Shadowrocket)](../client/02-singbox-subscription-links.md) yazısına bakın.

| Belirti | Nedeni | Ne yapmalı |
|---|---|---|
| "Unable to fetch subscription" (abonelik alınamadı), 401 | Hesabın süresi dolmuş ya da parola değiştirilmiş (parolayı değiştirmek eski yapılandırmaları anında geçersiz kılar; bu bilerek böyle tasarlandı) | Siteye giriş yapıp geçerlilik süresine bakın; yeniledikten ya da parolayı değiştirdikten sonra QR kodunu yeniden tarayın |
| İçe aktarma başarılı, bağlantı zaman aşımına uğruyor | O bölgenin adresi az önce değişti ya da o giriş noktasına operatör müdahale ediyor | İstemcide "Update subscription"a (aboneliği güncelle) dokunarak en son yapılandırmayı çekin; başka bir bölgeye geçin — her bölge ayrı bir yapılandırmadır, birbirini etkilemez |
| Bağlı ama internet yok | İstemcinin kendi yönlendirme kuralları trafiği "direct"e (doğrudan) gönderiyor | Varsayılan çıkışı o düğüme çevirin ya da kendi eklediğiniz kuralları silin |
| Tarayınca "Invalid QR code" (geçersiz QR kodu) çıkıyor | Pencere ilk açıldığında QR kodu Hiddify / sing-box içindir; diğer istemciler onu doğrudan tarayınca bu hatayı alır. Ya da başkasının ekran görüntüsünden taranmıştır | Önce kendi istemcinizin düğmesine tıklayın, QR kodu uygun türe geçer; sonra tarayın ya da yapıştırın: Clash ailesindeki istemciler için "Clash subscription", Shadowrocket / NekoBox / v2rayN vb. için "Share link". QR kodu sizin kendi kimlik bilgilerinizi içerir; başkasınınki çalışmaz |
| Hız düşük | Seçilen bölgenin yükü yüksek ya da yerel genişbant ile bölge uyuşmuyor | Sitedeki bölge listesinde kırmızı, sarı ve yeşil ışıklara bakıp yeşil ışıklı bir bölgeye geçin; hâlâ yavaşsa operatörünüze göre bölge değiştirin |
| Clash ailesinden bir istemci paylaşım bağlantısını içe aktaramıyor | Clash Meta, Clash Verge, FlClash, Stash ve benzerleri tek satırlık bir hysteria2:// bağlantısını profil olarak içe aktaramaz | "Clash subscription" düğmesine tıklayın ve URL'yi istemcinin abonelik listesine yapıştırın; orijinal Clash ve Clash for Windows'un çekirdeğinde hysteria2 yoktur, bunun yerine mihomo çekirdekli bir istemci kullanın |
| Paylaşım bağlantısı içe aktarılamıyor ya da bağlanmıyor | Paylaşım bağlantısı birkaç istemcinin çözümleyemediği genişletilmiş bir biçim kullanıyor | Hiddify'a geçin |

## Yenileme, plan değiştirme ya da parola değiştirmeden sonra yeniden içe aktarmak gerekir mi

- **Yenileme ya da plan değiştirme (Bireysel / Aile / Kurumsal)**: Hayır. Mevcut yapılandırma çalışmaya devam eder.
- **Parola değiştirme**: Eski yapılandırma anında çalışmaz olur; QR kodunu yeniden tarayın. Telefonunuzu kaybederseniz ya da bağlantı sızarsa erişimi iptal etmek için bunu kullanın.
- **Hesabın süresi doldu**: Yapılandırma 401 döndürür. Yeniledikten sonra yeni yapılandırma gerekmez, yeniden bağlanmanız yeterli.
- **Eylül 2026'dan önce içe aktarılanlar**: IPv6'yı reddeden kural eksiktir; bu yüzden yurt dışından Çin videosu izlerken telif kısıtlaması uyarısı çıkar. Silip yeniden içe aktarın; bkz. [03](03-ipv6-and-dns-leak.md).

## Destekle ne zaman iletişime geçmeli

Desteğe üç şey söyleyin: istemcinin adı ve sürümü, bölge ve hatanın tam metni ya da ekran görüntüsü.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=troubleshooting-04) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-04) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerlidir
