# 08 · Çin'e giden hat nasıl seçilir: Çin IP'si nereden gelir, ücretsiz olanlar nerede çuvallar

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/choose-china-vpn?utm_source=github&utm_content=china-access-08

Çin'e giden bir hat tek bir iş yapar: Yurt dışından gönderdiğiniz isteklerin Tencent Video'ya, NetEase Cloud Music'e ya da internet bankanıza **Çin anakarasından** bir IP ile ulaşmasını sağlar. Bu yüzden önce iki noktaya bakın: Çıkış gerçekten anakara IP'si mi ve cihazdaki trafikten herhangi biri hattın yanından geçiyor mu. Hız, fiyat ve istemci bunlardan sonra gelir.

## Çin IP'si nereden gelir

Sağlayıcının anakarada kendi sunucuları olmalıdır. Çin'deki bulut sağlayıcıları bir makine açmak için gerçek kimlikle kayıt ister ve bant genişliğini kullanıma göre ücretlendirir; bu yüzden maliyet yurt dışı makinelerden çok daha yüksektir. Çin'e giden meşru hizmetlerin neredeyse hepsinin ücretli olmasının ve Çin çıkışlarının sayısının sınırlı olmasının nedeni budur.

Yaygın bir ikame, Hong Kong, Tayvan ya da Japonya'daki makineleri "Çin'e giden hat" diye sunmaktır. Bu adresler Bilibili'nin Hong Kong, Makao ve Tayvan bölümlerinin bir kısmında işe yarar, ama Tencent Video, iQIYI ve Youku yine telif kısıtlaması gösterir; internet bankacılığı ve 12306 da sizi yurt dışında sayar. **Nasıl anlaşılır: Bağlandıktan sonra IP'nin nereye kayıtlı olduğuna bakın; yalnızca "Çin · bir eyalet" yazıyorsa geçerlidir.**

## Seçmeden önce kontrol edilecek beş madde

| Madde | Nasıl kontrol edilir | Başarısızlık neye benzer |
|---|---|---|
| Çıkış bölgesi | Bağlandıktan sonra IP'nin nereye kayıtlı olduğuna bakın | Hong Kong, Tayvan, Japonya ya da Kore adresleri |
| IPv6 ve DNS | "test ipv6" diye aratıp bir test sayfası açın | IPv6 alanı bulunduğunuz ülkeyi gösteriyor → video siteleri sizi yine engeller, bkz. [Sorun giderme 03](../troubleshooting/03-ipv6-and-dns-leak.md) |
| İstemci | Standart bir protokol mü (AnyConnect, OpenVPN, Hiddify) | Tek bir özel uygulama var; o kaldırılırsa kullanacak hiçbir şeyiniz kalmaz |
| Bant genişliği | Pekin saatiyle 20:00–23:00 arasında 1080p oynatın | Gündüz hızlı, akşam sürekli yükleniyor |
| Çoklu cihaz ve router | Hesap başına kaç cihaz, router ile tüm ev bağlanabiliyor mu | Her cihaz için ayrı satın almak gerekiyor |

## Ücretsiz Çin hatları neden sürekli kopar

Sorun "ücretsiz" olması değil, maliyet yapısıdır. Anakara çıkış bant genişliği kullanıma göre ödenir ve ücretsiz bir hizmet üç yoldan yalnızca birini seçebilir: Tek makineye birkaç bin kişiyi doldurur, herkes yoğun saatlerde takılır; trafiği ve süreyi sınırlar, yarı yolda ödeme uyarısı çıkar; ya da başka yoldan para kazanır: reklam enjekte eder, tarama geçmişini toplar ya da cihazınızı başkasının çıkışı olarak kullanır.

Ücretsiz "Çin'e giden" tarayıcı eklentilerinin bir kör noktası daha vardır: Yalnızca tarayıcının web isteklerini proxy'den geçirirler; video oynatıcı, uygulamalar ve sistem DNS'i onlardan geçmez. "Web sayfası açılıyor ama video oynamıyor" durumunun bu kadar yaygın olmasının nedeni budur.

Arada bir bir şeye bakmak için ücretsiz yeterlidir. Dizi takip etmek, müzik dinlemek ve internet bankacılığı için istikrarlı, ücretli bir hattın kazandırdığı zaman abonelik ücretinden çok daha değerlidir. Önce 4 saatlik denemeyi alın, bir kez akşam yoğun saatinde deneyin, sonra karar verin.

## Yurt dışındaki öğrenciler, gezginler ve aileler nasıl kurmalı

- **Yurt dışındaki öğrenciler**: Yurt ağlarında çoğunlukla IPv6 vardır; IPv6'yı engelleyen bir istemci kullanın. İnternet bankacılığı, CHSI ve 12306 için Çin hattına yalnızca gerektiğinde bağlanın ve işiniz bitince bağlantıyı kesin; böylece hesap risk denetimine daha az takılırsınız.
- **Kısa geziler**: Telefonunuza Cisco ya da Hiddify istemcisi kurun ve QR kodunu tarayarak içe aktarın; indiğiniz anda çalışır.
- **Uzun süre yurt dışında yaşayan bütün bir aile**: Yazılımı yüklenmiş tek bir router'ı hatta bağlayın; TV, set üstü kutu ve yaşlı yakınların telefonları hiçbir ayar gerektirmez; bkz. [Router ile Çin video sitelerinin engelini kaldırmak](../router/06-unlock-chinese-video-with-router.md).

## 5 dakikalık kendi kendine test

1. Çin hattına bağlanın; IP sorgusu Çin anakarasında bir eyalet gösteriyor.
2. IPv6 test sayfası IPv6'yı kullanılamaz ya da yine anakara adresi olarak gösteriyor.
3. Tencent Video'da yalnızca Çin'de yayınlanan herhangi bir diziyi açın; oynuyor.
4. Pekin saatiyle 20:00'den sonra bir kez daha 1080p oynatın; tekrar tekrar yüklenmiyor.
5. Başka bir Çin çıkışına geçip ilk üç adımı tekrarlayın.

## SSS

**Çin'e giden VPN ile Çin'e giden hızlandırıcı arasında fark var mı?** Özünde fark yoktur. "Hızlandırıcı" genellikle bir oyun ya da video şirketinin özelleştirdiği, yalnızca belirli uygulamaları kapsayan bir uygulamadır; VPN ise tüm cihazı kapsayan bir tüneldir.

**Hong Kong düğümüyle Tencent Video izleyebilir miyim?** Hayır, lisans yalnızca anakarayı kapsar.

**Hesap başına kaç cihaz?** LeoTun'da aynı anda bağlantı sayısı plana bağlıdır: Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz. Bir router tek cihaz sayılır, arkasındaki cihazlar ayrıca sayılmaz. Aynı anda çevrim içi sayısı planınızın sınırını aşarsa hesap türünü geçici olarak yükseltebilir (kalan süre fiyata göre eşdeğer değerde dönüştürülür), sonra geri dönebilirsiniz.

**Clash kullanabilir miyim?** Evet. LeoTun bir sing-box aboneliği, bir Clash aboneliği ve bir hysteria2 paylaşım bağlantısı sunar. Clash Meta, Clash Verge, FlClash, Stash ve benzerlerinde "Clash aboneliği" düğmesine tıklayıp adresi istemcinin abonelik listesine yapıştırın; abonelik dönüştürücüye gerek yoktur, paylaşım bağlantısını da kullanmayın. Orijinal Clash ve Clash for Windows kullanılamaz, çünkü çekirdeklerinde hysteria2 yoktur. Bu abonelik varsayılan olarak yerel ağınız dışındaki her şeyi düğümden geçirir; Çin videoları için hiçbir şeyi değiştirmeniz gerekmez. Kendi kurallarınızı eklerseniz Çin alan adlarını "direct" (doğrudan) yapmayın.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-08) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-08) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
