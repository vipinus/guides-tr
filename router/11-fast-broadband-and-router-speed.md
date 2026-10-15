# 11 · Router ile gigabit ya da 2 Gbps genişbant: hızı ne belirler

Ev genişbandı giderek hızlanıyor, bu yüzden şu soru sık geliyor: Hattım gigabit, hatta 2 Gbps; bir VPN router'ından ne kadar hız alırım?

## Kısa cevap

Tünelden geçen trafikte hızı Çin'den çıkan bacak belirler. **Darboğaz evinizin hattı değil, Çin'den çıkan bacaktır.** YouTube'un takılmadan oynayacağını taahhüt ediyoruz. Kesin hız aşağıdaki etkenlere bağlıdır.

Çin hizmetlerine giden trafik tüneli kullanmaz ve genişbandınızın tam hızıyla çalışmaya devam eder. Bkz. [10 · NAS, yazıcı ve kameralar etkilenir mi?](10-nas-printer-camera-behind-router.md)

## Hızı belirleyen dört etken

**1. Sınır ötesi bacak**
Uluslararası kapasiteyi herkes paylaşır ve evinizdeki tarifenin hızıyla ilgisi yoktur. Pekin saatiyle 20:00–23:00 ülke genelinde yoğun saattir; bu aralıkta yeşil ışıklı bir bölge seçin. Hâlâ yavaşsa genellikle neden yerel genişbanttır (site ya da apartman genelinde paylaşılan toplu genişbant ya da birbirine uymayan operatör ve bölge; bir sonraki maddeye bakın). Bkz. [Neden bazen hızlı bazen yavaş](../network/06-why-sometimes-fast-sometimes-slow.md).

**2. Operatörünüz ve seçtiğiniz bölge**
Her operatör Çin'den farklı bir yoldan çıkar ve doğru bölgeyi seçmek her şeyden daha önemlidir:
- Kuzeyde China Unicom: önce Japonya ve Kore'yi deneyin
- Güneyde China Telecom: önce Güneydoğu Asya'yı deneyin
- Diğer operatörler: önce Çin giriş bölgelerini deneyin

**3. Router'ın kendisi**
Trafiğin tünele girmeden önce şifrelenmesi gerekir ve bu router'ın işlemcisine düşen bir iştir. Modeller arasında büyük fark var:
- GL-MT300N-V2 (mini): 100 Mbps portlar. Telefonda ya da dizüstünde 1080p için yeterli, hızlı bir hatta denk değil
- GL-MT3000 (taşınabilir): küçük bir haneyi kaldırır. Çoğu kişi için ilk tercih
- GL-MT6000 (masaüstü): 2.5G port. Çok cihaz, 4K ve oyun konsolları için

Hattınız hızlı ve evde çok kullanım varsa mini modeli değil, MT3000'i ya da MT6000'i seçin.

**4. Evdeki son birkaç metre**
TV'yi ve masaüstü bilgisayarı mümkün olan her yerde kabloyla bağlayın. Kalabalık bir apartmanda Wi-Fi ciddi parazite maruz kalır; "hat yavaş" şikâyetlerinin çoğu aslında evin içindeki sorundur.

## Yavaş hissettiğinde sırayla şunları deneyin

1. Bölge değiştirin. İki üç bölge deneyin ve günün bu saatinde dayanan bölgeyi bulun.
2. Yönetim sayfasında "Automatically select the fastest line" (en hızlı hattı otomatik seç) seçeneğini açın. Gecikmesi ve kaybı en düşük hattı seçer, bu değişince de geçiş yapar. Bu durumda çıkış ülkesinin seçtiğiniz bölgeden farklı olabileceğini unutmayın.
3. Video izlediğiniz cihazı kabloya bağlayın.
4. Yalnızca bu siteyle mi sınırlı, kontrol edin. Aynı anda diğer siteler hızlıysa yavaş olan karşı tarafın sorunudur.

## Satın almadan önce nasıl anlarsınız

Kaydolun ve 24 saatlik ücretsiz denemeyi alın, kredi kartı gerekmez. En çok kullandığınız saatte, örneğin akşam bağlanın ve YouTube'da HD bir video izleyin. Telefonda ya da dizüstünde gördüğünüz, router'ın size vereceğine yakındır. Router kararını ondan sonra verin.

## SSS

**Neden bana kaç megabit olduğunu doğrudan söylemiyorsunuz?** Çünkü bu sayı her kişi ve her saat için farklıdır. Genişbandınız iyiyse akşam yoğun saatinde bile YouTube'un takılmadan oynayacağını taahhüt ediyoruz: kuzeyde China Unicom ya da güneyde China Telecom. Site ya da apartman genelinde paylaşılan toplu genişbant bunun istisnasıdır. 24 saatlik ücretsiz denemeyi alıp kendiniz bir kez denemek en doğru testtir.

**Hız testi sitesi düşük bir sayı gösteriyor ama video sorunsuz oynuyor?** Bu normaldir. Hız testi sunucularının da kendi yoğun ve sakin anları vardır; bir dakika arayla yapılan iki test iki kat farklı çıkabilir. Gerçekte ne yapmak istiyorsanız ona göre değerlendirin.

**Daha pahalı bir router daha hızlı yapar mı?** Yalnızca darboğaz router'sa, örneğin hızlı bir hatta mini model kullanılıyorsa. Darboğaz sınır ötesi bacaksa yeni bir router hiçbir şey değiştirmez, farklı bir bölge değiştirir.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-11) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-11) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
