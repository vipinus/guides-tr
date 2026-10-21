# 07 · Çin'deki ev kameralarınızı yurt dışından izlemek

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/home-camera?utm_source=github&utm_content=china-access-07

## Üç durum, her birinin çözümü farklı

| Evdeki kamera sisteminiz hangi türden | Yurt dışından doğrudan izleyebilir misiniz | Çözüm |
|---|---|---|
| Bulut hizmetli üretici uygulaması (EZVIZ, Xiaomi, TP-Link, Imou vb.) | Çoğunlukla evet; bazı bölgelerde kısıtlı ya da çok yavaş | Çin IP'sine geçin ve uygulamanın Çin sürümünü kullanın |
| Yalnızca ev yerel ağında izlenebilen bir ağ video kaydedici (NVR) | Hayır, internete açık bir giriş noktası yok | Evdeki bir cihazı özel ağa ekleyin, yurt dışındaki cihaz da özel ağ üzerinden ev yerel ağına girsin |
| Üretici uygulaması, ama yurt dışı mağazadaki kendi sunucuları olan ayrı bir sistem | Hesaplar uyuşmuyor | Uygulamanın Çin sürümünü kurun ve Çin hesabını kullanın |

## Birinci durum: üretici bulutu

Kamera görüntüyü üreticinin sunucusuna gönderir, uygulama da sunucudan çeker. Yurt dışı bir ağdan Çinli bir üreticinin sunucusuna giden hat kötüdür; bu da yavaş yükleme ve kesik yayın olarak kendini gösterir. Çin IP'sine geçince Çin içindeki bir hatta olursunuz ve belirgin biçimde düzelir.

Yurt dışı mağazadaki aynı adlı uygulamanın genellikle yurt dışı sunuculara bağlandığını ve hesapların birbirinin yerine geçmediğini unutmayın. Uygulamanın Çin sürümünü kurun; mağaza bölgesi sorunları için [sorun giderme ve kurulum rehberine](../client/06-ios-app-store.md) bakın.

## İkinci durum: kaydedici yalnızca yerel ağda

En yaygın ve aynı zamanda en zor durum budur. NVR'nin genel IP'si yoktur ve Çin'deki ev genişbantlarında port yönlendirme çoğunlukla yapılamaz. İşe yarayan yol **özel ağ**dır:

1. Evde sürekli açık bir cihaz bırakın; bir bilgisayar, NAS, Raspberry Pi ya da desteklenen bir router olabilir. Üzerine özel ağ istemcisini kurun, özel ağınıza ekleyin ve "yerel ağı paylaş" seçeneğini açın.
2. Yurt dışındaki telefonu ya da bilgisayarı da aynı özel ağa ekleyin.
3. Bundan sonra yurt dışındaki cihaz NVR'ye, tıpkı evdeymişsiniz gibi, ev yerel ağındaki adresinden doğrudan ulaşır.

LeoTun'un "Özel ağ"ı tam olarak bu tür bir özel ağdır. Tek hesapla kaç cihaza kurduğunuzun sınırı yoktur; aynı anda çevrim içi sayısı plana göredir: Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz. Evde bir cihaz artı yurt dışında birkaç cihaz Aile planına tam uyar.

## Üçüncü durum: hesaplar uyuşmuyor

Çin'de satın alınan bir cihaz Çin hesabına bağlıdır ve yurt dışı mağazadaki uygulama ona giriş yapamaz. Tek çözüm uygulamanın Çin sürümünü kurmaktır. Cihazı yeniden eşleştirmeyin; bu, ailenizin hesabını cihazdan atar.

## Gizlilik hatırlatması

Ev kameralarınızın görüntüsü yalnızca sizin cihazlarınızla eviniz arasında akmalıdır. Özel ağ seçeneği doğrudan uçtan uca bağlantıyı tercih eder, yalnızca doğrudan bağlantı kurulamadığında bir aracı sunucu üzerinden iletir ve görüntü hiçbir sunucuda saklanmaz; üretici bulutu seçeneğinde ise görüntü üreticiden geçer. Her iki durumda da kaynağı belirsiz "tünel araçları" kullanmayın; bu, ev kameralarınızı başkasına teslim etmek demektir.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-07) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-07) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
