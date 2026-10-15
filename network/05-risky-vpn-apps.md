# 05 · Riskli VPN yazılımları nasıl anlaşılır

Tüm trafiğiniz bir VPN uygulamasının elinden geçer ve o uygulama istediği her şeye bakabilir. Piyasada özellikle dikkat edilmesi gereken iki tür şey var: Biri, Çince konuşulan çevrelerde "kırmızı VPN" denen türdür; arkasında denetim makamları vardır, uyum adına gerçek kimliğinizi ister ve kayıtları teslim eder. Diğeri, kaynağı belirsiz ücretsiz hızlandırıcılardır; verinizden, cihazınızdan ya da içine yerleştirdiği bir şeyden para kazanır. İkisinin ortak noktası "kullanırken gayet iyi çalışması"dır; sorun göremediğiniz yerdedir. Aşağıda kendiniz doğrulayabileceğiniz on işaret, zaten kurduysanız ne yapacağınız ve üç dakikalık bir kendi kendine kontrol var.

## VPN yazılımı neden sıradan bir uygulamadan daha riskli

VPN sistem düzeyinde çalışır: Cihazdaki her programın trafiğini alır, arka planda çalıştığından haberiniz olmayanlar dahil. Sıradan bir uygulama yalnızca kendi topladığı veriyi sızdırır; bir VPN ise o cihazda yaptığınız her şeyi sızdırır. Bu yüzden VPN yazılımı seçme ölçütü, sıradan bir uygulama seçmekten çok daha katı olmalıdır.

"Kullandım, bir şey olmadı" güvenliğin kanıtı değildir. Kayıt tutma, raporlama ve enjeksiyon hep sunucu tarafında ya da arka planda olur ve kullanıcı tarafında hissedilmez; bir şey ters gittiğinde ise çoğu zaman aylar geçmiştir ve hangi yazılımdan kaynaklandığı geriye doğru izlenemez.

## On işaret

- Belirsiz kaynak: Kurulum dosyası bir grup sohbetinden, bir bulut diskten ya da bir QR kodundan gelir; resmî sitesi ya da uygulama mağazası sayfası yoktur. Meşru bir istemci ya uygulama mağazasından, ya geliştiricinin resmî sitesinden ya da imzası kontrol edilebilen bir yayın sayfasından gelir.
- Kök sertifika kurmanızı ister: Kurulum sırasında "sertifikaya güvenin" ya da "profili yükleyin" der ve bir sertifika yetkilisine (CA) güvenmenizi şart koşar. Kök sertifika kurulunca internet bankacılığı ve e-posta dahil tüm HTTPS trafiğinizi açabilir. Normal bir VPN'in bu adıma ihtiyacı yoktur.
- Fazla izin: Kişilere, SMS'lere, arama kayıtlarına, hassas konuma ve fotoğraf arşivine erişim isteyen bir VPN. Bir VPN'in yalnızca tünel kurma iznine ihtiyacı vardır; gerisi işine yaramaz.
- Gerçek kimlikle kayıt şartı: Kaydolmak için kimlik kartı, yüz taraması ya da bir Çin anakarası cep telefonu numarası bağlamak gerekir. Sözde uyumlu bir VPN kimliğinizi trafik kayıtlarınıza böyle bağlar; meşru bir hizmetin yalnızca bir e-posta adresine ihtiyacı vardır.
- Özel protokol + kaynağı kapalı istemci: Yalnızca kendi uygulamasını kullanabilirsiniz ve hiçbir standart protokolü (AnyConnect, OpenVPN, WireGuard, Hiddify) desteklemez; bu yüzden gerçekte ne ilettiğini üçüncü taraf, kaynağı açık bir istemciyle doğrulayamazsınız.
- Ücretsiz, görünür bir gelir kaynağı yok: Ücretli planı yok, reklamı yok, kurumsal müşterisi yok, ama yıllardır çalışıyor. Çin anakarası çıkış bant genişliği kullanıma göre faturalanır; ücret almayan bir hizmet bunu her zaman başka bir yerden çıkarır.
- Şirket yok, destek yok, geçmiş yok: İşleten kurum bulunamaz, ulaşılacak kimse yoktur, alan adı bir yıldan kısa süre önce alınmıştır ve sık sık adını ve kılığını değiştirir.
- Olağan dışı arka plan trafiği: Siz kullanmazken bile cihaz sürekli veri yükler, pil ve mobil veri hızla tükenir. Cihazınızı başkasının çıkışı olarak kullanıyor ya da verilerinizi eşitliyor olabilir.
- Tanıtımında "resmî", "kayıtlı", "yasal ve uyumlu" vurgusu yapar ve diğer her şeyin yasa dışı olduğunu ima eder: Bu, bir "kırmızı VPN"in en tipik söylemidir; uyumu da kayıt tutup raporlamaktan ibarettir.
- Uygulama mağazası puanları tek yönlü, yorumlar birbirine benziyor, indirme sayısı yorum sayısıyla orantısız: Bunlar sahtedir.

## Nasıl doğrulanır

1. Protokole bakın: Resmî sitede hangi protokolü kullandığı yazıyor mu, üçüncü taraf bir istemci kullanılabiliyor mu? OpenVPN, AnyConnect, Hiddify ve Tailscale gibi kaynağı açık ya da standart istemcilerle bağlanabildiğiniz bir hizmette paketleri kendiniz yakalayıp neyin iletildiğini görebilirsiniz.
2. İzinlere bakın: Kurduktan sonra sistem ayarlarında hangi izinleri istediğine bakın, VPN dışındaki her şeyi kapatın ve hâlâ çalışıyor mu görün. Çalışmıyorsa kaldırın.
3. Sertifikalara bakın: iOS'ta Ayarlar → Genel → VPN ve Aygıt Yönetimi; Android'de Ayarlar → Güvenlik → Şifreleme ve kimlik bilgileri → Güvenilir kimlik bilgileri → Kullanıcı; Windows sertifika yöneticisinde "Güvenilen Kök Sertifika Yetkilileri". Onun kurduğu bir sertifika varsa silin ve uygulamayı kaldırın.
4. Sızıntıları kontrol edin: Bağlandıktan sonra bir DNS sızıntı testi ve bir IPv6 test sayfası açarak hem çözümlemenin hem adresin onun sunucularından geçip geçmediğine bakın; sonra bir HTTPS sitesi açıp sertifikayı verenin özgün CA olup olmadığını kontrol edin.
5. Kurumu kontrol edin: Resmî sitede şirketi ya da ekibi tanıtan bir bölüm var mı, kaç yıldır işletiliyor, destek nerede; iade kuralları yazılı mı; gizlilik politikası neyin kaydedildiğini açıkça söylüyor mu?

## Zaten kurduysanız ne yapmalı

1. Yazılımı kaldırın, sonra yukarıda anılan yerleri kontrol ederek kurduğu sertifikaları ve profilleri silin.
2. Parolaları değiştirin: internet bankacılığı, e-posta, sık kullanılan hesaplar; özellikle o yazılımı kullanırken giriş yaptıklarınız.
3. İki adımlı doğrulaması açık hesaplarda giriş geçmişini kontrol edin ve tanımadığınız cihazları kaldırın.
4. Bir router'a kurulduysa fabrika ayarlarına döndürün, ardından resmî ya da güvenilir bir yazılımı yeniden yükleyin.

## Doğrulamanızı nasıl sağlıyoruz

LeoTun'un tüm istemcileri resmî üreticilerden ve tanınmış kaynak açık kuruluşlardan gelir: Cisco, OpenVPN, Hiddify ve Tailscale; değiştirilmeden olduğu gibi kopyalanır ve bu siteden indirdiğiniz kopyayı istediğiniz an resmî ya da kaynak açık istemciyle değiştirebilirsiniz. Protokollerin hepsi standart protokollerdir ve paket yakalayarak doğrulanabilir.

Kaydolmak için yalnızca bir e-posta adresi gerekir; telefon numarası da kimlik kartı da gerekmez. Yalnızca faturalama için gereken bilgileri tutarız; neleri ziyaret ettiğinizi kaydetmeyiz, reklam enjekte etmeyiz ve veri satmayız.

Sertifika kurmayız, kişilerinize ya da konumunuza erişim istemeyiz. Bir gün istemcimiz sizden kök sertifika kurmanızı isterse bu kesinlikle biz değiliz.

## SSS

**Ücretsiz olan her şey kullanılamaz mı?** Kaynak açık topluluğun istemcileri (OpenVPN, Hiddify, Tailscale) zaten ücretsiz ve güvenilirdir; risk "ücretsiz yazılımda" değil, "ücretsiz hizmette"dir. Ücretsiz bir hizmette neyle ayakta durduğuna bakın.

**Uygulama mağazasında yer alıyorsa güvenli midir?** Mağazada yer alması yalnızca mağazanın otomatik incelemesinden geçtiğini gösterir; sunucu tarafında kayıt tutulmadığı anlamına gelmez. Yukarıdaki on işaretten izinlere, gerçek kimlik kaydına, protokole ve kuruma bakın; mağaza bunları sizin için kontrol etmez.

**Sözde "kırmızı VPN" nedir?** Bu çevrelerde, arkasında denetim makamları olan, uyum adına gerçek kimlikle kayıt isteyen ve kayıt tutan VPN'lere verilen ad. Genellikle kendilerini "resmî" ve "yasal" diye tanıtırlar ve kullanırken normal çalışırlar; sorun, kimliğinizin ve tüm trafik kayıtlarınızın birbirine bağlanmasıdır.

**Bir VPN'in içeriğimi kaydedip kaydetmediğini nasıl anlarım?** Kullanıcı tarafından anlayamazsınız; yalnızca size kaç doğrulama aracı sunduğuna bakabilirsiniz: Protokol standart mı, istemcinin kaynağı açık mı, gizlilik politikası somut mu, işleten kurum sorgulanabiliyor mu? Dördü de yoksa kayıt tutuyor kabul edin.

**Router yazılımında da bu tür bir risk var mı?** Evet; kaynağı belirsiz "engel aşma yazılımları" tüm ev ağını ele geçirebilir. Yalnızca resmî OpenWrt'yi ya da kaynağı kontrol edilebilen yazılımları yükleyin; bu sitenin yazılımı OpenWrt'den derlenir, yalnızca hatta bağlanma bileşenleri ve bölünmüş yönlendirme kuralları eklenmiştir.

## Devamı için

- [Diğer VPN'lerden farkımız](https://www.leotun.com/tr/guides/why-us?utm_source=github&utm_content=network-05)
- [Çin'e giden VPN: ücretsiz mi, ücretli mi](https://www.leotun.com/tr/guides/free-vs-paid?utm_source=github&utm_content=network-05)
- [Tencent Video yurt dışında telif kısıtlaması gösterdiğinde ne yapmalı](https://www.leotun.com/tr/guides/overseas-video?utm_source=github&utm_content=network-05)
- [Hakkımızda: nasıl kurulu, neleri kaydediyoruz](https://www.leotun.com/tr/about?utm_source=github&utm_content=network-05)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/risky-vpn-apps?utm_source=github&utm_content=network-05

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=network-05) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=network-05) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
