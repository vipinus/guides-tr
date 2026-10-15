# 04 · İnternet bankacılığı, mobil bankacılık ve ödemeler

## Bankanın risk kontrolü neye bakar

Banka yalnızca IP'ye bakmaz. Birkaç sinyali bir araya getirip puanlar:

1. **IP'nin kayıtlı olduğu yer**: Yurt dışı bir IP risk seviyesini hemen yükseltir.
2. **SIM kart**: Mobil bankacılık uygulaması SIM bilgisini okur; yurt dışı bir operatörün kartı aleyhinize sayılır.
3. **Cihaz parmak izi**: Yeni bir cihaz ya da jailbreak / root yapılmış bir cihaz.
4. **Davranış**: Yeni bir konumdan yapılan ilk girişte hemen yüklü bir para transferi.

Bu yüzden sık görülen durum şudur: Çin IP'sine geçtikten sonra giriş yapabilirsiniz, ama transfer yine engellenir. IP yalnızca ilk maddeyi çözer.

## Neler yapabilirsiniz

- Çin IP'sine geçtikten sonra **önce küçük işlemler yapın**, risk kontrolü bu ortama alışsın; büyük işlemleri sonra yapın.
- Bir Çin SIM kartı tutun ve dolaşımı açık bırakın; hem doğrulama kodları hem de SIM kontrolü buna bağlıdır.
- Mümkünse mobil bankacılık uygulamasının Çin sürümünü kurun; mağaza bölgesi sorunları için [iOS bir uygulamayı yüklemenize izin vermiyorsa](../client/06-ios-app-store.md) yazısına bakın.
- Engellendiyseniz tekrar tekrar denemeyin. Art arda başarısız denemeler geçici bir dondurmayı tetikler; kilidi açtırmanın en hızlı yolu müşteri hizmetleri hattını aramaktır.

## Alipay ve WeChat Pay

İkisi de IP konusunda bankalardan daha hoşgörülüdür ve genellikle yurt dışı IP'den çalışır; ama yurt dışı bir karta bağlı hesapların tutar ve kullanım yeri sınırları vardır. Çin'de çıkarılmış bir kartla ödeme yapmanız ya da Çinli bir satıcıya para göndermeniz gerektiğinde Çin IP'sine geçmek işleri çok kolaylaştırır.

## Yapmamanız gerekenler

Hattan geçiyor olun ya da olmayın, halka açık Wi-Fi'de bankacılık işlemi yapmayın. Hat yalnızca çıkış IP'nizi değiştirir, bankanın ötesinde sizin için hiçbir şeyi şifrelemez; güvenliği sağlayan, banka uygulamasının kendi şifrelemesidir.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-04) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-04) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
