# 01 · Yurt dışından Çin'e erişim nasıl çalışır

## Ne görürsünüz

Yurt dışındasınız; iQIYI, Bilibili ya da NetEase Cloud Music'i açıyorsunuz ve "Bu içerik yalnızca Çin anakarasında kullanılabilir" uyarısıyla karşılaşıyorsunuz. İnternet bankacılığı ve 12306 (Çin demiryolu bilet sitesi) hiç açılmıyor ya da doğrulama kodu bir türlü gelmiyor.

## Tek bir nedeni var: IP adresinizin kayıtlı olduğu yer

Cihazınız internete bağlandığında operatörünüz ona bir genel IP adresi verir. Bu adreslerin hangi ülkeye ve hangi operatöre ait olduğunu gösteren dünya çapında bir kayıt vardır. Çin'in video ve müzik platformları yayın haklarını yalnızca **Çin anakarası** için satın alır ve bu bölgenin dışında yayın yapmaları yasal olarak mümkün değildir; bu yüzden yurt dışı bir IP gördükleri anda sizi geri çevirirler.

Bankalar ve bilet siteleri farklı bir mantıkla çalışır. Onlar için mesele telif hakkı değil, risk kontrolüdür: Yurt dışı IP'den yapılan giriş yüksek riskli sayılır ve doğrudan engellenir.

## Çözüm yaklaşımı

Sunucunun gördüğü IP'yi Çin anakarasına ait bir IP yapmak. Bunun için trafiğiniz önce anakarada bulunan bir sunucuya gönderilir, o sunucu da hedef siteye sizin yerinize bağlanır. Hedef site o sunucunun IP'sini görür ve sizi içeri alır.

"Çin'e giden hat" tam olarak bunu yapar: Trafiğinizi Çin anakarasındaki bir IP'den dışarı çıkarır.

## Sık yapılan üç yanlış

- **DNS'i değiştirmek işe yaramaz.** DNS yalnızca alan adlarını adreslere çevirir; hedef site kullandığınız DNS'e değil, kaynak IP'nize bakar.
- **Bazı platformlar sistem bölgesine de bakar.** IP'nin yanında bazı platformlar cihaz dilini ve uygulama mağazasının bölgesini de kontrol eder; bu durumda sistem bölgesini de değiştirin.
- **Hız, iki nokta arasındaki hattın kalitesine bağlıdır.** Yurt dışından anakaraya uzanan sınır ötesi bağlantı darboğazdır; bu yüzden size yakın ve anakaraya iyileştirilmiş hattı olan bir giriş noktası seçmek, sunucunun kendi donanımından daha önemlidir.

## Devamı için

- [Hangi bağlantı yöntemi hangi duruma uygun](02-choose-your-connection-method.md)
- [Bağlanmıyor, yavaş, kopuyor: kontrol listesi](../troubleshooting/01-cannot-connect-slow-drops.md)

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=network-01) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=network-01) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz ve ödeme yapan her arkadaş için ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, kampanyanın bitiş tarihi yok
