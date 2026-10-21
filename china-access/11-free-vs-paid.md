# 11 · Çin'e giden VPN: ücretsiz mi, ücretli mi

Önce hesabı yapalım: Çin'e giden bir hattın en pahalı kalemi, Çin anakarasındaki çıkışın bant genişliğidir; Çin'deki bulut sağlayıcıları bunu trafiğe göre ücretlendirir ve hiç de ucuz değildir. Ücretsiz bir seçenek mucize yaratamaz, üç yoldan birini seçmek zorundadır: çok sayıda kişiyi tek makineye sıkıştırmak, trafiğe ve süreye sınır koymak ya da parayı verilerinizden ve reklamlardan çıkarmak. Bu, ücretsizin hiç kullanılamayacağı anlamına gelmez; ara sıra bir şeye bakmak için yeterlidir. Ama dizi takip etmek, internet bankacılığı yapmak ya da aileniz için kurulum yapmak söz konusuysa ücretli bir hattın aylığı genellikle bir fincan kahveden ucuzdur ve kazandırdığı zaman bunun çok üstündedir.

## Ücretsiz düğümlerin sürekli kopmasının üç nedeni

- Kalabalık: Yüzlerce, binlerce kişi tek bir makineyi ve tek bir sınır ötesi hattı paylaşır. Gündüz sorun yoktur, Pekin saatiyle 20:00–23:00 arası herkesin ekranında yükleme simgesi döner.
- Sınırlı: Trafik bitince kesilir, süre bitince kesilir, hızı 1080p'nin altında tutar ve yarı yolda ödeme isteyen bir pencere açar. Bunlar aslında bunu söylemeyen ücretli ürünlerin deneme sürümleridir.
- Satılan: Reklam enjekte ederek, tarama geçmişini toplayarak ya da cihazınızı başkasının çıkış noktası olarak kullanarak ayakta kalır. Bu özellikle ücretsiz "Çin'e giden" tarayıcı eklentilerinde yaygındır.

## Ücretsiz seçeneklerin göremediğiniz iki tuzağı daha

Birincisi, çıkış Çin anakarasında olmayabilir. Ücretsiz "Çin'e giden" düğümlerin azımsanmayacak bir kısmı aslında Hong Kong, Tayvan ya da Japonya adresidir. Çin web sayfalarını açabilirler, ama Tencent Video ve iQIYI yine telif kısıtlaması gösterir, internet bankacılığı da sizi yurt dışında sayar. Bağlandıktan sonra IP'nin nerede kayıtlı olduğuna bir kez bakın, anlarsınız.

İkincisi, IPv6 ve DNS ele alınmaz. Ücretsiz seçenekler tünel içinde IPv6'yı neredeyse hiç reddetmez; cihazınızda IPv6 varsa video sitesi hâlâ yurt dışı bir adres görür. "Bağlı olduğu belli ama yine de izleyemiyorum" durumunun en yaygın nedeni budur; "Tencent Video yurt dışında telif kısıtlaması uyarısı verdiğinde ne yapmalı" yazısına bakın.

## Ücretsiz ne zaman yeter, ne zaman ödemelisiniz

Yeter: Ara sıra bir şeye bakmak ya da haber okumak için bir Çin web sayfası açıyorsanız, hız ve istikrar beklentiniz yoksa ve üzerinden hiçbir hesaba giriş yapmıyorsanız.

Ödeme zamanı: Dizi izlemek ve müzik dinlemek, internet bankacılığına ya da Alipay'e giriş yapmak, evdeki TV ve yaşlılar için kurulum yapmak ya da belli bir saatte bilet kapmak istiyorsanız. Bu durumların ihtiyacı "her seferinde çalışması"dır ve ücretsiz bir seçenek bunu veremez.

Basit bir test: Koptuğunda canınız sıkılacaksa, ödeme zamanı gelmiştir.

## Ne kadar harcamalı

LeoTun'un Bireysel planı ayda 4 ABD dolarıdır ve 24 bölgeyi, aynı anda çevrim içi 2 cihazı ve tüm bağlantı yöntemlerini — AnyConnect / OpenVPN / Hiddify / Web Proxy — kapsar; router ile de kullanılabilir. Aile ve Kurumsal planlar Bireysel planın sırasıyla 2 ve 4 katıdır. Bölgeler, hatlar ve bağlantı yöntemleri üç planda da tamamen aynıdır; tek fark aynı anda çevrim içi olabilen cihaz sayısıdır (4 ve 8).

Aylık almak istemiyorsanız iki yol var: Önce 4 saatlik ücretsiz denemeyi alın (kredi kartı gerekmez, her hesap için bir kez) ve akşam yoğun saatinde bir kez deneyin; ya da günlük ödeyin. Puan yükledikten sonra Bireysel plan günde 1 puandır, 25 puan 8 ABD dolarıdır; bu da günde yaklaşık 0,32 ABD dolarına gelir. Çin'e yapacağınız bir seyahatten önce yalnızca birkaç gün almak için çok uygundur.

Davet ettiğiniz bir arkadaşınız kaydolup ilk ödemesini yaptığında hem sizin hem de arkadaşınızın geçerlilik süresi 20 gün uzatılır (Bireysel plan esasıyla), kişi sayısında sınır yoktur. Bu, uzun vadeli bir ücretsiz süre kaynağıdır.

## Ödemeden önce malı nasıl kontrol edersiniz

1. Denemeyi alın, Çin hattına bağlanın ve IP'nin Çin anakarasında kayıtlı olup olmadığına bakın.
2. Bir IPv6 test sayfası açın ve IPv6'nın kullanılamadığını ya da onun da Çin anakarası adresi olduğunu doğrulayın.
3. Pekin saatiyle 20:00'den sonra bir bölümü 1080p oynatın ve tekrar tekrar arabelleğe alıp almadığına bakın.
4. Başka bir Çin çıkışına geçip bir kez daha deneyin; şans eseri olmadığını doğrulayın.
5. Standart protokoller (AnyConnect, OpenVPN, Hiddify) kullanıp kullanmadığına bakın: İstemciler üreticiden ya da açık kaynak topluluğundan gelir, sağlayıcı kapanırsa yapılandırma başka yerde de kullanılabilir; kendine özgü bir uygulama ise bir kez kaldırıldığında elinizde hiçbir şey kalmaz.

## SSS

**Gerçekten ücretsiz ve aynı zamanda istikrarlı bir Çin VPN'i var mı?** Uzun vadede istikrarlı olanı yok; bunu maliyet yapısı belirler. İstikrarlı ve ücretsiz olan yalnızca ücretli bir ürünün deneme süresidir. Malı kontrol etmek için kullanmak doğrudur; uzun süreli kullanım için ona güvenmek gerçekçi değildir.

**Ücretsiz bir VPN parolalarımı çalar mı?** Tünel içindeki HTTPS içeriğini göremez, ama hangi alan adlarını ziyaret ettiğinizi görebilir ve şifresiz sayfalara içerik enjekte edebilir. Tarayıcı eklentisi türündeki ücretsiz proxy'lerin izinleri daha da geniştir. Ücretsiz bir hatta internet bankacılığına giriş yapmayın.

**Günlük mü aylık mı daha avantajlı?** Ayda 12 gün ya da daha fazla kullanıyorsanız aylık daha avantajlıdır; ara sıra birkaç gün kullanıyorsanız günlük. Puanların süresi dolmaz, bir yükleme uzun süre yeter.

**Deneme için kredi kartı gerekiyor mu?** Hayır. Kaydolduktan sonra ana sayfadan alın: tüm özelliklerle 4 saat, her hesap için bir kez.

**Ödeme yaptım ama hâlâ kopuyor. Ne yapmalıyım?** Önce bölge değiştirin, sonra bağlantı yöntemi değiştirin (aynı hesapta üç protokol de kullanılabilir); yine olmuyorsa sorun giderme rehberini okuyun ya da destekle iletişime geçin. Ödemenin anlamlarından biri de sorumluluğu üstlenen birinin olmasıdır.

## Devamı için

- [Fiyatlar ve ücretsiz deneme](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-11)
- [Çin'e giden VPN nasıl seçilir](https://www.leotun.com/tr/guides/choose-china-vpn?utm_source=github&utm_content=china-access-11)
- [Tencent Video yurt dışında telif kısıtlaması uyarısı verdiğinde ne yapmalı](https://www.leotun.com/tr/guides/overseas-video?utm_source=github&utm_content=china-access-11)
- [Yurt dışındaki öğrenciler Çin'e giden VPN'i nasıl kurmalı](https://www.leotun.com/tr/guides/students?utm_source=github&utm_content=china-access-11)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/free-vs-paid?utm_source=github&utm_content=china-access-11

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-11) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-11) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
