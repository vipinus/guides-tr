# 09 · Router'da bölünmüş yönlendirme nasıl çalışır

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/router-smart-split?utm_source=github&utm_content=router-09

Hepsinin adı "akıllı bölünmüş yönlendirme", ama bazı router'lar kullanırken bir türlü rahat ettirmez. Bölünmüş yönlendirmenin ne olduğu için [03](03-router-split-routing.md) yazısına bakın; bu yazı yalnızca bölünmüş yönlendirmenin ne yapması gerektiğini, bir kısmı eksik olduğunda gördüğünüz belirtileri ve bizim router'ın bunu nasıl yaptığını anlatıyor.

## Tek cümleyle

Bölünmüş yönlendirmenin yapması gereken: Her web sitesi **görselleri, videosu ve girişiyle birlikte**, bulunduğu yere göre ya VPN'den geçer ya da doğrudan bağlanır ve **evdeki her cihaz aynı kurallara uyar**. Bunun yalnızca bir kısmı yapıldığında aşağıdaki belirtileri görürsünüz.

## Belirtilerin karşılaştırması

| Gördüğünüz | Arka planda olan |
|---|---|
| Bölünmüş yönlendirme açıkken Çin siteleri aslında yavaşlıyor | Çin siteleri yurt dışı sanılıyor ve trafik baştan sona yurt dışına gidip geri dönüyor |
| Sayfa açılıyor ama video dönüp duruyor, görseller gelmiyor, giriş takılıyor | Listede yalnızca ana site var; aynı sitenin videosu, görselleri ve girişi başka bir yoldan gidiyor |
| Yurt dışındasınız, Çin'e giden hat açık, ama video uygulaması hâlâ "仅限中国大陆" (yalnızca Çin anakarası) diyor | Trafiğin bir kısmı VPN'e girmedi ve site yurt dışı bir adres gördü |
| Telefonda oynuyor ama TV'de ya da TV kutusunda oynamıyor; bir bilgisayar bir türlü VPN'den geçmiyor | O cihazın kendi ağ ayarları var ve router'ı atlıyor |
| Banka ve ödeme uygulamaları zaman zaman "başka bir konumdan giriş" uyarısı veriyor | Aynı uygulamanın trafiği bir an Çin'den, bir an yurt dışından çıkıyor |
| Bölünmüş yönlendirme kullanırken kayboluyor (yeniden başlatma ya da yeniden bağlanmadan sonra ya her şey VPN'den geçiyor ya da hiçbir şey) | Ayar hatırlanmamış |

Bunların hiçbiri **hata vermez**. Router baştan sona "Connected" (bağlı) gösterir; bu da onları teşhis etmesi en zor sorunlar yapar ve birçok kişi sonunda hattın kötü olduğunu düşünür.

## Bölünmüş yönlendirmenin yapması gerekenler

- Bir site web sayfaları, görselleri, videosu ve girişiyle birlikte tek bir yoldan gider, parçalara bölünmez
- "Çin mi yurt dışı mı" kararını verirken doğru tarafta durur, Çin siteleri dolambaçlı yola girmez
- Evdeki her cihaz aynı kurallara uyar; cihazın kendisinde değiştirilen ağ ayarları bunları aşamaz
- Yön, seçilen bölgeye göre otomatik değişir (yurt dışından Çin'e erişim ile Çin'den yurt dışı hizmetlere erişim birbirinin tersi iki kural takımıdır)
- Liste kendiliğinden güncellenir, yeniden yazılım yüklemek gerekmez
- Ayarlar hatırlanır: Yeniden başlatma ya da yeniden bağlanmadan sonra değişmez; bir kez kapatıldıysa sessizce yeniden açılmaz

## Bizim router'daki akıllı bölünmüş yönlendirme

| | Nasıl yapılıyor |
|---|---|
| Anahtar | Varsayılan olarak açık; Çin'de bir bölge seçmek = yurt dışından Çin'e erişim yönü, yurt dışı bir bölge seçmek = Çin'den yurt dışı hizmetlere erişim yönü, otomatik uygulanır. Çin'den yurt dışı hizmetlere erişim yönünde ayrıca bir "Blocked sites only" (yalnızca engellenen siteler hattan geçer) onay kutusu vardır ("VPN settings" (VPN ayarları) → akıllı bölünmüş yönlendirme), varsayılan olarak işaretlidir; işaretsiz = Çin siteleri doğrudan, geri kalan her şey VPN'den. Ekim 2026'dan önce yüklenen yazılımlarda bu kutu henüz görünmez; uzaktan değiştirilmesi için müşteri hizmetleriyle iletişime geçin |
| Liste | "Sitenin tamamı" esasına göre düzenlenir: Web sayfaları, kullandıkları video, görsel ve giriş kaynaklarıyla birlikte gider |
| Çin'den yurt dışı hizmetlere erişim | Varsayılan olarak yalnızca engellenen siteler ve hizmetler VPN'den geçer (her gün otomatik güncellenen bir engelli siteler listesine ve Telegram gibi sabit adreslere bağlanan hizmetlere dayanarak); Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler (yabancı şirket siteleri, Apple ve Microsoft indirmeleri, oyun platformları) dolambaçsız doğrudan bağlanır, router olmadan nasılsa o hızda |
| Evdeki cihazlar | Topluca devralınır; cihazın kendisinde değiştirilen ağ ayarları da kurallara uyar; router'ın etrafından dolaşan bir "arka kapı" yoktur |
| Güncellemeler | Liste ve kurallar router açılırken otomatik güncellenir; engelli siteler listesi ayrıca her gün otomatik güncellenir |
| Hafıza | Yeniden bağlanma ya da yeniden başlatmadan sonra korunur; kapatıldıysa kapalı kalır |
| Yerel ağ | Yazıcılara, NAS'a ve kameralara her zamanki gibi doğrudan ulaşılır |

**Yardımınızın gereken tek durum**: Bir telefonda ya da tarayıcıda "Özel DNS" veya "Güvenli DNS" gibi şifreli bir ayar açıksa cihaz kendi sorgularını şifreler ve router bunları göremez. Bir cihaz tuhaf davranıyorsa ya da her şey çalışırken engellenen siteler açılmıyorsa önce bu tür ayarları kapatın.

## Kendiniz doğrulayın

1. Çin'desiniz (yurt dışı hizmetlere erişim): Baidu ve Taobao ile Apple ve Microsoft indirmeleri gibi Çin'den zaten sorunsuz açılan yabancı siteler normal hızda; engellenen yurt dışı siteler açılıyor ve video oynuyor.
2. Yurt dışındasınız (Çin'e erişim): Tencent Video'da ya da iQIYI'da rastgele bir bölüm seçin, "仅限中国大陆" (yalnızca Çin anakarası) uyarısı çıkmadan oynuyor; yerel banka ve alışveriş siteleri her zamanki gibi çalışıyor.
3. Her cihazı deneyin, özellikle TV'yi ve TV kutusunu; tuhaf davranan bir cihazda önce "Özel DNS / Güvenli DNS"i kontrol edin, sonra modemin değil bu router'ın Wi‑Fi'sine bağlı olduğunu doğrulayın.
4. Bölünmüş yönlendirmede bir site açılmıyor: Geçici olarak "Global"e (tam) geçin. Global'de açılıp bölünmüş yönlendirmede açılmıyorsa henüz listede değildir; listeye eklenmesi için adresi müşteri hizmetlerine gönderin, otomatik güncellemeyle size ulaşır. Çin'deyken akıllı bölünmüş yönlendirme kısmında "Blocked sites only" işaretini kaldırıp yeniden de deneyebilirsiniz; o zaman açılıyorsa site yine engelli ama henüz listede değildir.

## SSS

**Akıllı bölünmüş yönlendirmeyi kendim mi açmalıyım?** Hayır. Hesabınıza giriş yapıp bir bölge seçtiğiniz anda açıktır.

**Yurt dışından Çin'e erişim ile Çin'den yurt dışı hizmetlere erişim ayrı ayrı mı kurulmalı?** Hayır. Yön, seçilen bölgeye göre otomatik belirlenir.

**Yazıcıları ya da NAS'ı etkiler mi?** Hayır. Ev ağındaki cihazlara her zamanki gibi doğrudan ulaşılır.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-09) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-09) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
