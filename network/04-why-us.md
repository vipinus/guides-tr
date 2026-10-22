# 04 · Diğer VPN'lerden farkımız

Piyasadaki VPN'ler kabaca üç gruba ayrılır: dünya genelinde kullanıcılara hitap eden büyük uluslararası markalar, Çince konuşulan çevrelerde "jichang" diye bilinen proxy hattı sağlayıcıları (abonelik bağlantısıyla satılan, çoğu zaman yeniden satılmış proxy hatları) ve her türden ücretsiz yazılım. LeoTun 2006'dan beri kendi sunucularını işletiyor ve tek bir işe odaklanıyor: Çin anakarasındaki kullanıcılar ve yurt dışında yaşayan Çinliler için iki yönde de bağlantıyı istikrarlı tutmak. Bu yazı bizi bu üç ürün türüyle madde madde yan yana koyuyor; hangisinin kime uygun olduğunu ve bizim işleri nasıl yaptığımızı gösteriyor, böylece ödeme yapmadan önce resmi net görürsünüz.

## Tek cümleyle konumumuz

Biz **özellikle Çin anakarasının ağ ortamı için optimize edilmiş** bir hizmetiz, uluslararası hatların bayisi değiliz. China Telecom, China Unicom ve China Mobile'ın uluslararası çıkışlarının kalitesi birbirinden çok farklıdır; her operatör için ayrı ayar yapar ve farklı bölge önerileri veririz. Çin içinde kendi iniş noktalarımız var; böylece genişbandı vasat olan kullanıcıların da sağlam bir giriş noktası olur. Port ve protokolleri Çin'deki ağ ortamı değiştikçe sürekli uyarlarız; bir kez kurup kendi hâline bırakmayız.

Ters yönde, yurt dışındaki biri Çin'deki hizmetlere ulaşmak istediğinde aynı hesapla yalnızca Çin bölgesini seçer: Çin siteleri Çin IP'siyle açılır, Çin dışındaki siteler ise yine Çin dışından çıkar. Yurt dışından Çin'e erişim ile Çin'den yurt dışı hizmetlere erişim, aynı işin iki yönüdür.

## Büyük uluslararası markalarla karşılaştırma

- Güçlü yanları: dünya çapında onlarca ülke, binlerce sunucu, olgun uygulamalar, bağımsız denetimden geçmiş kayıt tutmama beyanları. Avrupa'da ya da Amerika'daysanız ve yalnızca halka açık Wi‑Fi'de şifreleme ya da başka bir ülkenin yayın platformlarını izlemek istiyorsanız iyi bir seçimdir.
- Zayıf yanları: ürün Çin ağı düşünülerek tasarlanmamıştır. Kendilerine özgü protokolün izi sabittir; Çin'de bir kez tanındığında uygulamanın tamamı çalışmaz hâle gelir. Çin içinde iniş noktaları yoktur; bu yüzden yurt dışından Çin videosu izlemek için ya bu özellik hiç yoktur ya da Hong Kong veya Tayvan IP'leri kullanılır, Tencent Video ve iQIYI bunları da aynı şekilde engeller.
- Bizim yaptığımız: yalnızca standart protokoller (AnyConnect, OpenVPN, Hiddify, Tailscale, HTTPS web proxy) ve üreticilerden ya da açık kaynak topluluğundan gelen istemciler. Engellenen ancak belirli bir adres olabilir, adresi değiştirmek yeter; istemci devre dışı kalmaz.
- Neyi neye tercih ettik: 24 bölge, her birinin arkasında birkaç makine; bağlanırken en az yüklü olan otomatik seçilir. İstemciler üreticilerin ve açık kaynak topluluğunun resmî sürümleridir, QR kod okutarak ya da tek tıkla içe aktararak kurulur. Üçüncü taraf denetim raporumuz yok; neyi kaydettiğimizi ve neyi kaydetmediğimizi Hakkımızda sayfasına yazdık. Bir onay mührüne değil, her şeyi açıkça yazmaya güveniyoruz.

## Proxy hattı sağlayıcılarıyla karşılaştırma

- Proxy hattı sağlayıcılarının güçlü yanları: ucuzdur, çok sayıda düğüm sunar, abonelik bağlantısını yapıştırır yapıştırmaz kullanılır; istemcilerle uğraşmayı sevenler de bu özgürlükten hoşlanır.
- Proxy hattı sağlayıcılarının zayıf yanları: çoğu, yurt dışında makine kiralayıp trafik satan bireyler ya da küçük ekiplerdir; Çin'de kendilerine ait iniş noktaları yoktur ve çıkış kalitesi kiralanan hatlara göre değişir. Parayı alıp ortadan kaybolmak, ad değiştirmek ve kapanmak sık görülür; bir yıllık ödeme yapmanız bir yıl boyunca kullanabileceğiniz anlamına gelmez. İstemcileri çözmek neredeyse tamamen kullanıcıya kalır, bir şey ters gittiğinde sorumluluğu üstlenen olmaz.
- Bizim yaptığımız: makineler kendimizindir; Çin çıkışları, Çin anakarasındaki bulut sağlayıcılarında gerçek kimlikle kayıtlı kendi makinelerimizdir. Tek hesapta altı bağlantı yöntemi vardır; tüm cihazları kapsayan router çözümü ve 7/24 destek grubu proxy hattı sağlayıcılarında bulunmaz. 2006'dan bugüne hizmet veriyoruz; isim değişikliğinden önce ve sonra hesaplar, geçerlilik süreleri ve fiyatlar değişmedi.
- Fiyatımız: Bireysel plan ayda 5 $, Aile planı 10 $, Kurumsal plan 20 $; buna kendi makinelerimiz, altı bağlantı yöntemi ve 7/24 destek grubu dahildir. Siz yalnızca bölgeyi seçersiniz, her bölgenin arkasında sistem en az yüklü makineyi seçer; hız testi yapıp düğüm seçmenize gerek kalmaz.

## Ücretsiz yazılımlarla karşılaştırma

- Ücretsizin güçlü yanları: hiçbir şey ödemezsiniz, ara sıra bir şeye bakmak için yeterlidir.
- Ücretsizin zayıf yanları: Çin anakarasında çıkış bant genişliği kullanıma göre ücretlendirilir; bu yüzden ücretsiz bir hizmet ancak kullanıcıları üst üste yığarak, hızı kısarak ya da veri satarak ayakta kalabilir. Tarayıcı eklentisi türündekiler yalnızca web isteklerini taşır; video, uygulamalar ve sistem DNS'i onlardan geçmez. Kaynağı belirsiz kurulum dosyaları başlı başına bir risktir; "Riskli VPN yazılımları nasıl anlaşılır" yazısına bakın.
- Bizim yaptığımız: 4 saatlik ücretsiz deneme kredi kartı istemez ve malı görmeniz içindir; günlük ödeme (puanla) ara sıra kullananlar içindir; davet ettiğiniz bir arkadaşınız ödeme yaptığında ikiniz de 15'er puan kazanırsınız (Bireysel planda yaklaşık 15 gün), bu da uzun vadeli bir ücretsiz süre kaynağıdır.
- Nasıl düzenledik: Ücretsiz süre 4 saatlik denemeden ve davet ödüllerinden gelir; uzun süreli kullanım için aylık, yıllık ya da günlük ödersiniz.

## Altı bağlantı yöntemi, tek hesap

Özel ağ (Tailscale): Bir kez giriş yapın, hep çevrim içi kalsın; bölgeyi menüden değiştirin. Cisco AnyConnect: En iyi uyumluluk; sistemde yerleşik ya da resmî istemciyle. OpenVPN: Router, NAS ve Linux için. Web Proxy: Yalnızca tarayıcı ondan geçer, tasarımı gereği kopacak bir bağlantı yoktur. Hiddify: Paket kaybına dayanıklıdır, en iyi hızı verir. Router: TV, TV kutusu ve yaşlı yakınlarınızın cihazları dahil tüm cihazlara erişim.

Her ağın kendisine en uygun bir yöntemi vardır, bu yüzden altısını birden alırsınız: Aynı hesapla istediğiniz an geçiş yaparsınız; kampüs ağı UDP'yi kısıtlıyorsa Hiddify'dan AnyConnect'e, genişbant dalgalanıyorsa Web Proxy'ye. Nasıl seçeceğiniz için "Hangi bağlantı yöntemi hangi duruma uygun" yazısına bakın.

## Hesap kuralları

- Hesaplar üç plandan oluşur: Bireysel, Aile ve Kurumsal; aynı anda sırasıyla 2, 4 ve 8 cihaz çevrim içi olabilir. Bölgeler, trafik ve bağlantı yöntemleri üçünde de aynıdır. Kaç cihaza kurduğunuzun bir sınırı yoktur, sınırlanan yalnızca aynı anda bağlı olan sayıdır. Aynı anda çevrim içi sayısı planın sınırını aştığında hesap türünü geçici olarak yükseltebilir (kalan süre fiyata göre eşdeğer değerde dönüştürülür), işiniz bitince geri dönebilirsiniz.
- Üç plan arasında istediğiniz zaman geçiş yapabilirsiniz, kalan süre eşdeğer değerde dönüştürülür (Aile ve Kurumsal, Bireysel fiyatının sırasıyla 2 ve 4 katıdır). Üç plan da router'ı destekler; tek bir kullanıcı için Bireysel plan yeterlidir.
- İadeler kullanılan süreye orantılıdır ve her zaman yapılabilir; elle işlenir, paranın ne zaman hesabınıza geçeceği için kesin bir süre taahhüt edilmez.
- Hız: Genişbandınız iyiyse akşam yoğun saatlerinde bile YouTube'un takılmadan oynayacağını taahhüt ediyoruz: kuzeyde China Unicom ya da güneyde China Telecom. Site ya da apartman genelinde paylaşılan toplu genişbant bunun istisnasıdır. Bir bölge yavaşsa bölgeyi ya da bağlantı yöntemini değiştirin.
- Hiddify ve OpenVPN yapılandırmaları hesabınızı taşır; parolayı değiştirmek eski yapılandırmaları geçersiz kılar. Telefonunuz kaybolursa ya da bir bağlantı sızarsa tek bir parola değişikliği hepsini geri alır, ardından yeniden içe aktarmanız yeterlidir.

## İşleri nasıl yapıyoruz

- Yalnızca faturalandırma için gereken bilgileri tutarız. Neleri ziyaret ettiğinizi kaydetmeyiz, reklam enjekte etmeyiz, veri satmayız.
- Her istemci resmî üreticilerden ve tanınmış açık kaynak kuruluşlarından gelir: Cisco, OpenVPN, Hiddify ve Tailscale; değiştirilmeden olduğu gibi yansılanır. Yapılandırma QR kod okutarak ya da tek tıkla içe aktararak yapılır.
- Çin bölgesi Çin anakarasındaki makinelerde çalışır ve çıkış IP'lerinin hepsi Çin anakarasındadır.

## SSS

**Büyük uluslararası markalardan daha mı güvenlisiniz?** Şifreleme gücü benzerdir, iki taraf da standart protokoller kullanır. Fark güven modelindedir: Büyük markalar denetim raporlarına dayanır; biz yalnızca faturalandırma için gereken bilgileri tutarız ve her istemci resmî üreticilerden ve tanınmış açık kaynak kuruluşlarından gelir.

**Neden proxy hattı sağlayıcıları gibi yüzlerce düğüm sunmuyorsunuz?** Düğüm sayısının fazla olması daha istikrarlı olduğu anlamına gelmez. Her bölgemizin arkasında birkaç makine vardır ve bağlanırken sistem en az yüklü olanı seçer; hız testi yapıp düğüm seçmekle uğraşmazsınız. Bir adres engellendiğinde otomatik olarak değiştirilir, istemcinizdeki adresi değiştirmeniz gerekmez.

**Fiyat daha düşük olabilir mi?** Bireysel plan ayda 5 $'dır ve ne kadar uzun alırsanız indirim o kadar büyür (%5 → %10 → %20 indirim); puanla günlük ödemede günde yaklaşık 0,4 $'dır; davet ettiğiniz bir arkadaşınız ödeme yaptığında ikiniz de 15'er puan kazanırsınız (Bireysel planda yaklaşık 15 gün), kişi sayısında sınır yoktur. Kayıt olurken 4 saatlik ücretsiz deneme de gelir.

**Söylediklerinizi nasıl doğrulayabilirim?** 4 saatlik denemeyi alın; akşam yoğun saatinde Çin bölgesine bağlanıp Tencent Video'da bir bölüm izleyin, yurt dışı bir bölgeye bağlanıp YouTube'u açın, IP'nin kayıtlı konumunu ve bir IPv6 test sayfasını kontrol edin. Kontrol listesi "Çin'e giden VPN nasıl seçilir" yazısında.


## Devamı için

- [Hangi bağlantı yöntemi hangi duruma uygun](https://www.leotun.com/tr/guides/choose-connection?utm_source=github&utm_content=network-04)
- [Riskli VPN yazılımları nasıl anlaşılır](https://www.leotun.com/tr/guides/risky-vpn-apps?utm_source=github&utm_content=network-04)
- [Çin'e giden VPN: ücretsiz mi, ücretli mi](https://www.leotun.com/tr/guides/free-vs-paid?utm_source=github&utm_content=network-04)
- [Hakkımızda: nasıl kurulu ve neleri kaydediyoruz](https://www.leotun.com/tr/about?utm_source=github&utm_content=network-04)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/why-us?utm_source=github&utm_content=network-04

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=network-04) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=network-04) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
