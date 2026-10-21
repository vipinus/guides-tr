# 02 · Abonelik bağlantısı nasıl içe aktarılır (Hiddify, Clash, Shadowrocket)

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/singbox-subscription?utm_source=github&utm_content=client-02

Bir proxy hattı sağlayıcısının verdiği "abonelik bağlantısı", istemcinin eksiksiz bir yapılandırma indirdiği bir HTTPS adresinden ibarettir: Sunucu, port ve kimlik bilgileri hepsi içindedir, elle bir şey yazmanız gerekmez. LeoTun'un Hiddify sayfası da size aynı türden bir şey verir, üstelik doğrudan üç biçimde; böylece Hiddify, Clash ve Shadowrocket her biri kendi biçimini alır ve hiçbir şeyi dönüştürmek gerekmez.

## Açılan penceredeki üç düğme

Siteye giriş yapın → Hiddify sayfası → bir bölgenin bayrağına tıklayın. Bir QR kodu açılır, altında üç düğme vardır. Düğmeler işletim sistemine göre değil, **abonelik türüne göre** gruplanmıştır; bu yüzden telefonda ve bilgisayarda aynı düğmeler görünür:

| Düğmede adı geçen istemciler | Alt başlık | Tıklayınca ne kopyalanır |
|---|---|---|
| Hiddify / sing-box / GUI.for.SingBox / Karing | sing-box aboneliği | Telefonda uygulamayı açan `sing-box://import-remote-profile?url=…` içe aktarma bağlantısı; bilgisayarda yapıştırmak için düz `https://…` yapılandırma adresi. Yapılandırma yönlendirme kurallarını ve IPv6'yı reddeden bir kuralı zaten içerir; bu yüzden bir "abonelik şablonu"na sarmaya gerek yoktur |
| Clash Meta / Clash Verge / FlClash / Stash / Mihomo Party / Clash Nyanpasu / ClashX Meta / OpenClash | Clash aboneliği | İstemcinin abonelik / profil listesine yapıştırılacak Clash biçiminde (YAML) bir abonelik adresi |
| NekoBox / Shadowrocket / v2rayN / v2rayNG / Streisand / V2Box / Loon / Egern / Husi / NekoRay / Pharos Pro / Bedlam / Furious / daed / Lumen KVN / Kitty Pro | Paylaşım bağlantısı | Tek satırlık bir `hysteria2://…`; yalnızca düğümü taşır, yönlendirme kuralı yoktur |

- Adlar tek satıra sığmayınca döngü hâlinde kayar; bu normaldir.
- **Bir düğmeye tıklamak, üstteki QR kodunu da o türe çevirir**; böylece ilgili istemci onu tarayabilir. Pencere ilk açıldığında QR kodu Hiddify / sing-box içindir; başka istemciler onu doğrudan tararsa "Invalid QR code" (geçersiz QR kodu) alır: Önce kendi istemcinizin düğmesine tıklayın, sonra tarayın ya da yapıştırın.
- Sayfanın üstündeki "Import all regions · auto-select" (tüm bölgeleri içe aktar · otomatik seç) penceresinde yalnızca ilk iki düğme vardır, paylaşım bağlantısı yoktur.

**Abonelik dönüştürme**: Bir biçimi diğerine çeviren üçüncü taraf siteler. LeoTun üç biçimin hepsini doğrudan verdiği için **dönüştürmeye gerek yoktur**; kimlik bilgilerinizi içeren bir bağlantıyı bir dönüştürme sitesine vermek, hesabınızı üçüncü bir tarafa vermek demektir, bunu yapmayın.

## Hiddify / sing-box ailesi: birinci düğme

1. Hiddify'ı kurun (Android: sitenin indirme sayfası ya da Google Play; iOS: App Store; masaüstü uygulaması Windows / macOS / Linux'u kapsar). sing-box çekirdeği içinde gelir.
2. Bir bölgenin bayrağına tıklayın, QR kodu açılır.
3. Telefon: Birinci düğmeye dokunup Hiddify'a geçin; panodan eklemeyi önerecektir. Ya da başka bir cihazdaki Hiddify'da "Scan QR code" (QR kodu tara) kullanın. Bilgisayar: Aynı düğmeye tıklayın, bir https:// adresi kopyalanır; sonra Hiddify'da "+" → "Add from clipboard" (panodan ekle) yapıp kaydedin.
4. Bağlan'a dokunun ve ilk seferde VPN iznini verin. Bölge eklemek için başka bir bayrağa tıklayın; her bölge ayrı bir profildir.

## Clash ailesi: ikinci düğme

Clash Meta (mihomo), Clash Verge, FlClash, Stash ve benzerleri için "Clash aboneliği" düğmesine tıklayın ve kopyalanan adresi istemcinin abonelik / profil listesine yapıştırın. Abonelik dönüştürücüye gerek yoktur.

**Clash ailesi istemciler paylaşım bağlantısını kullanmamalıdır**: Tek satırlık bir `hysteria2://` bağlantısını profil olarak içe aktaramazlar.

## Diğer istemciler: üçüncü düğme

"Paylaşım bağlantısı" düğmesine tıklayın, ardından NekoBox / Shadowrocket / v2rayN / v2rayNG vb. uygulamalarda "Import from clipboard" (panodan içe aktar) seçeneğini kullanın ya da düğmeye tıkladıktan sonra üstteki QR kodunu tarayın. Paylaşım bağlantısı kural taşımaz; yönlendirmeyi ve IPv6'yı kendiniz ayarlamanız gerekir: Yurt dışındaysanız ve Çin'deki içerikleri izlemek istiyorsanız Çin alan adlarını düğümden geçirin ve IPv6'yı kapatın.

Düğmede v2rayN'den sonra sayılan istemcilerin hepsi hysteria2'yi destekler, ama paylaşım bağlantısı birkaç istemcinin çözümleyemediği genişletilmiş bir hysteria2 biçimi kullanır; içe aktarma başarısız olursa ya da bağlanmıyorsa Hiddify'a geçin.

## Kullanılamayan istemciler

| İstemci | Neden |
|---|---|
| Surge | hysteria2'yi destekler ama yalnızca kendi yapılandırma biçimini okur; üç türün hiçbiri uymaz |
| Quantumult X | Bu tür hatları desteklemez |
| Orijinal Clash, Clash for Windows | Çekirdekte hysteria2 yok; bunun yerine mihomo çekirdekli bir istemci kullanın |

## Aboneliğin süresi dolar mı?

- **Zamanla dolmaz.** Abonelik adresindeki belirteç hesabınıza bağlıdır ve hesap geçerli olduğu sürece çalışır; yenileme ya da plan değişikliği yeniden içe aktarmayı gerektirmez.
- **Parolanızı değiştirmek eski adresi anında geçersiz kılar.** Telefon kaybolursa ya da bağlantı sızarsa erişimi böyle iptal edersiniz; değiştirdikten sonra kodu yeniden tarayın.
- **Hesabın süresi dolunca** adres 401 döndürür; yeniledikten sonra mevcut profili değiştirmeniz gerekmez.
- **Eylül 2026'dan önce içe aktarılan profillerde** IPv6'yı reddeden kural yoktur; silip yeniden içe aktarın.

İçe aktardığınız hâlde bağlanamıyorsanız bkz. [Sorun giderme 04](../troubleshooting/04-singbox-import-not-connecting.md).

## SSS

**Hiddify aboneliği ile Clash aboneliği arasındaki fark nedir?** Biçim farklıdır (JSON ve YAML) ve her istemci diğerinin aboneliğini tanımaz, ama düğümlerin kendisi ikisinde de çalışır. LeoTun ikisini de doğrudan verir: Clash ailesi istemciler "Clash aboneliği" düğmesine tıklar ve paylaşım bağlantısını kullanmaz.

**Tek bir profilde tüm bölgeler olabilir mi?** Bayraktan içe aktarmak her bölge için bir profil verir ve aralarında istemcinin profil listesinden geçiş yaparsınız; böylece bir bölgenin adresi değişirse yalnızca o bölge etkilenir. Çin dışındaki tüm bölgeleri tek seferde içe aktarıp istemcinin otomatik seçmesini istiyorsanız sayfanın üstündeki "Import all regions · auto-select" düğmesine tıklayın (yalnızca sing-box aboneliği ve Clash aboneliği düğmeleri vardır).

**QR kodunu aileme gönderebilir miyim?** QR kodu hesabınızın kimlik bilgilerini içerir; kime gönderirseniz hesabınızı o alır. Aileyle paylaşmak serbesttir (plana göre aynı anda cihaz: Bireysel 2, Aile 4, Kurumsal 8), ama herkese açık bir yerde paylaşmayın; sızarsa parolanızı değiştirin, çalışmaz olur.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-02) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-02) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
