# 09 · Destek ekibinin bilgisayarınıza ve router'ınıza uzaktan bakması

Bazı sorunlar grupta onlarca ekran görüntüsü gidip gelse de netleşmez; oysa destek ekibi ekrana doğrudan bakarak iki dakikada tespit edebilir. Bu yazı uzaktan yardımın ne zaman istenmeye değer olduğunu, bilgisayarda hangi yazılımın kullanılacağını, bu sitenin sunucu yapılandırmasının nasıl içe aktarılacağını, bağlantı bilgilerinin destek ekibine nasıl güvenle iletileceğini, oturum sırasında nelerin sizin kontrolünüzde olduğunu, sonrasında erişimi nasıl geri alacağınızı ve bu sitenin yazılımını çalıştıran bir router için ne yapmanız gerektiğini anlatıyor.

## Uzaktan yardım ne zaman istenmeye değer

- [01 · Bağlanmıyor, yavaş, kopuyor: kontrol listesi](01-cannot-connect-slow-drops.md) yazısını bir kez baştan sona uyguladınız; bağlantı yöntemini, bölgeyi, hata mesajının tam metnini ya da ekran görüntüsünü ve sorunun yaşandığı saati belirterek sordunuz; yine de çözülmedi.
- Adımları kendiniz tarif edemiyorsunuz: Ayar çok derinde, sistem dilini okuyamıyorsunuz ya da hata yakalayamayacağınız kadar hızlı geçip gidiyor.
- Bir aile üyenizin bilgisayarına yardım ediyorsunuz, yanında değilsiniz ve telefonda anlatamıyorsunuz.

Şu durumda **uzaktan yardım kullanmayın**; bunun yerine grupta yazılı iletişim kurun:

- Şirketin merkezden yönettiği bilgisayarlar. Grup ilkesi genellikle bu tür programların çalışmasını yasaklar ve şirket kurallarına aykırı olabilir.

## Hangi yazılım: RustDesk

Site [RustDesk](https://rustdesk.com)'i öneriyor: Kaynağı açıktır (AGPL-3.0), yani kodu herkes denetleyebilir; oturumun ne zaman başlayıp ne zaman biteceğine de kendi tıklamanızla siz karar verirsiniz. Windows, macOS, Linux, Android ve iOS'u destekler (iPhone / iPad yalnızca başkalarını kontrol edebilir, kontrol edilemez).

[İletişim sayfasında](https://www.leotun.com/tr/contact#downloads) "İndirme merkezi" → "Uzaktan yardım" bölümünden ya da resmî site rustdesk.com'dan indirin. Arama sonuçlarındaki üçüncü taraf indirme sitelerini kullanmayın. Oturumun iki tarafının da kurması gerekir.

## Kurduktan sonra hangi izinler verilmeli

| Sistem | Ne yapmalı |
|---|---|
| macOS | "Sistem Ayarları → Gizlilik ve Güvenlik" altında hem "Ekran Kaydı" hem "Erişilebilirlik" bölümünde RustDesk'i işaretleyin, sonra tamamen kapatıp yeniden açın. Yalnızca birini vermek "görülüyor ama kontrol edilemiyor" durumuna ya da tamamen siyah ekrana yol açar. "Hasarlı" uyarısı çıkarsa bkz. [06](06-antivirus-false-positive.md) |
| Android | Yardım alırken RustDesk'te "Start service"e (hizmeti başlat) dokunun ve ekran kaydına izin verin; destek ekibinin ekranınıza dokunabilmesi için sistemin "Erişilebilirlik" ayarlarında RustDesk'i de açın |
| Windows / Linux | Genellikle kurulur kurulmaz çalışır |

## Kendi sunucumuza bağlanmak

Uzaktan yardım bu sitenin kendi barındırdığı RustDesk sunucusu üzerinden çalışır; bu sunucuya Çin'in içinden de güvenilir şekilde bağlanılır. **Oturumun iki tarafının da yapılandırmayı bir kez içe aktarması gerekir**; iki uç ancak aynı sunucuyu kullandıklarında birbirini bulabilir:

1. Önce siteye giriş yapın, sonra [İletişim sayfasında](https://www.leotun.com/tr/contact#downloads) "İndirme merkezi" → "Uzaktan yardım" → "Sunucumuza bağlanma" bölümüne gidip "Kopyala"ya tıklayın.
2. Bilgisayarda RustDesk'te "Ayarlar → Ağ"ı açın, önce "Ağ ayarlarının kilidini aç"a, sonra "ID/Relay sunucusu"na tıklayın; telefonda "Ayarlar → ID/Relay sunucusu" yolunu izleyin.
3. Açılan pencerede sağ üstteki pano simgesine tıklayın (telefonda "İçe aktar"a dokunun). Yapılandırma otomatik doldurulur; "Tamam"a tıklayın.

**Yapılandırmayı giriş kutularına yapıştırmayın**; bu "failed to lookup address" (adres bulunamadı) hatasına yol açar. Bu yapılandırma yalnızca bu sitedeki hesaplarla kullanım içindir. Başkasına iletmeyin.

## Kimliği ve tek kullanımlık parolayı destek ekibine vermek

RustDesk'i açtığınızda ana ekranda bu makinenin kimliği (ID) ve tek kullanımlık bir parola görünür. Bunları vermeden önce üç şeyi doğrulayın:

1. **Önce siz sordunuz.** Sorununuzu [İletişim sayfasında](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-09) listelenen resmî bir grupta anlattınız ve bir sonraki adıma geçmeden önce uzaktan yardımın gerektiğine destek ekibi karar verdi. Destek ekibimiz size kendiliğinden yaklaşmaz, uzaktan erişim yazılımı kurmanızı ya da bağlantı kodu istemez; kim gelip isterse istesin, önce resmî grupta doğrulayın.
2. **Bunları yalnızca resmî destek kanallarından gönderin**: İletişim sayfasında listelenen insan destek iletişim bilgileri. Grupların dışında "LeoTun desteği" olduğunu söyleyen her özel sohbet biz değiliz.
3. **Gruba yazmayın.** Grup pek çok kişinin görebildiği bir yerdir; kimlik artı parola, bilgisayarınızın anahtarını kapıya asmakla aynıdır.

## Oturum sırasında

- Oturum boyunca ekranda ne yapıldığını görebilir ve RustDesk penceresinden istediğiniz an bağlantıyı kesebilirsiniz.
- Biri sizden pencereyi küçültmenizi, bilgisayarın başından kalkmanızı ya da internet bankacılığı veya ödeme uygulamalarını açmanızı isterse **bağlantıyı hemen kesin**.
- Hesap parolanızın girilmesi gerektiğinde kendiniz yazın; destek ekibine sesli okumayın.

## Sonrasında erişimi geri almak

1. RustDesk penceresinde bağlantıyı kes'e tıklayın ve karşı tarafın çevrim dışı olduğunu doğrulayın.
2. Tek kullanımlık parolayı yenileyin; az önce gönderdiğiniz parola geçersiz olsun.
3. RustDesk'ten çıkın. Artık ihtiyacınız yoksa kaldırıp bir dahaki sefere yeniden indirebilirsiniz.

## Router'lar: sizin yapmanız gereken

Bu sitenin yazılımını çalıştıran bir router için ne router'a ne de bilgisayara uzaktan erişim yazılımı kurmanız gerekir; router'ın yönetim parolasını destek ekibine göndermeniz de gerekmez. Yapmanız gereken tek şey:

- Router'ı açık, ağ kablosunu takılı ve hesabı router'da giriş yapmış durumda tutun.
- Resmî grupta destek ekibine hesabınızı, router modelini ve belirtileri iletin; gerisini destek ekibi halleder.
- Destek ekibi sizden istemedikçe üzerinde çalışılırken fişini tekrar tekrar çekip yeniden başlatmayın.

## SSS

**Destek ekibi bana kendiliğinden özelden yazıp uzaktan erişim yazılımı kurmamı söyler mi?** Hayır. Biri size kendiliğinden yaklaştığında her zaman önce resmî grupta kimliğini doğrulayın.

**İçe aktarırken "failed to lookup address" hatası mı?** Büyük olasılıkla yapılandırma giriş kutularına yapıştırılmıştır. O kutuları temizleyin, "ID/Relay sunucusu" penceresine dönün ve sağ üstteki pano simgesine tıklayarak içe aktarın.

**macOS'ta bağlandı ama ekran siyah ya da görülüyor ama kontrol edilemiyor mu?** İzinler eksik. Hem "Ekran Kaydı"nı hem "Erişilebilirlik"i işaretleyin, sonra tamamen kapatıp yeniden açın.

**Oturum bittikten sonra başka ne yapmam gerekiyor?** Bağlantıyı kesin, tek kullanımlık parolayı yenileyin, programdan çıkın. Bu üç adım tamamlanınca karşı taraf bir daha asla bağlanamaz.

## Devamı için

- [RustDesk uzaktan yardım nasıl kullanılır (site rehberi)](https://www.leotun.com/tr/guides/rustdesk-certificate?utm_source=github&utm_content=troubleshooting-09)
- [Mac uygulamanın "hasarlı" olduğunu söylediğinde ne yapmalı](https://www.leotun.com/tr/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-09)
- [İletişim sayfası: destek grupları, insan destek ve e-posta](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-09)
- [05 · Bize nasıl ulaşırsınız, bağlantıyı nasıl koparmazsınız](05-how-to-reach-us.md)
- [01 · Bağlanmıyor, yavaş, kopuyor: kontrol listesi](01-cannot-connect-slow-drops.md)

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=troubleshooting-09) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-09) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
