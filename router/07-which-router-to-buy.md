# 07 · Router almalı mısınız, dört model arasından nasıl seçilir

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/router?utm_source=github&utm_content=router-07

Router çözümü "cihaz çok, bazılarına istemci de kurulamıyor" sorununu çözer: VPN router'da bir kez kurulur; TV, oyun konsolu, akıllı hoparlör ve yaşlı aile büyüğünüzün telefonu hiçbir şey kurmadan otomatik olarak ondan geçer. Tek gereken, yazılım yüklenebilen bir router ve on dakikalık bir yükleme işlemidir. **Altı ücretli planın hepsi router kullanabilir; plana göre 1 ile 6 arası router eşleştirilebilir.**

## Ne zaman kullanmalı, ne zaman gerek yok

| Kullanın | Gerek yok |
|---|---|
| Evde istemci kurulamayan cihazlar var: TV kutusu, oyun konsolu, Apple TV, akıllı hoparlör gibi | Yalnızca bir telefonunuz ve bir bilgisayarınız var ve çoğunlukla iş seyahatindesiniz — istemci kurmak daha zahmetsiz |
| Aile kalabalık ve herkese cihaz cihaz anlatmak istemiyorsunuz | Yurtta ya da paylaşımlı bir evde kalıyorsunuz ve ağ sizin kontrolünüzde değil |
| Günün 24 saati bağlı kalması gereken cihazlarınız var (NAS, kamera yüklemesi) | Ana router'ınız operatörün kilitli modemi ve arkasına ikinci bir router bağlayamıyorsunuz — orta yol olarak taşınabilir bir router kullanın |
| Çin'deki bir ofis ya da bütün bir aile yurt dışı hizmetlere istikrarlı biçimde erişecek; bölünmüş yönlendirme router'da, cihazlar hiçbir şey fark etmiyor | |

## Yazılımı kendiniz yükleyin ya da hazır cihaz alın

İki yol da sonunda aynı yazılımı çalıştırır. Fark, yüklemeyi kimin yaptığı ve bir sorun çıktığında sorumluluğun kimde olduğudur.

- **Kendiniz yükleyin**: Elinizde OpenWrt'nin desteklediği bir router zaten var (1000'den fazla model). Yazılım sitede çevrim içi derlenir ve bağlantı 3 ila 5 dakika içinde e-postanıza gelir; ardından [02 · Yazılımı kendiniz yükleyin](02-flash-firmware-yourself.md) yazısını adım adım izleyin (videosu var). Teknik kurulumu kendi yapmaktan çekinmeyen ve cihaz parasından tasarruf etmek isteyenler için uygundur.
- **Hazır cihaz alın**: Yazılımı önceden yüklenmiş bir GL.iNet gönderiyoruz; kutudan çıkınca yapılacak üç adım için [01](01-plug-and-play-router.md) yazısına bakın. Uğraşmak istemeyenler ya da teknikten anlamayan aile üyeleri için uygundur.

Hangi yolu seçerseniz seçin yazılım bileşenlerini kendisi günceller, yeniden yükleme gerekmez; hat adresleri değiştiğinde de yapılandırmayı değiştirmeniz gerekmez.

## Dört router, kullanım şeklinize göre

| Model | Tür | Fiyat | Dahil | Nedir | En uygun olduğu kullanım |
|---|---|---|---|---|---|
| **GL-MT3000** | Taşınabilir | 250 $ | 2 yıl Temel plan hizmeti | Çift bantlı Wi‑Fi 6 ve 2.5G port, avuç içinden biraz büyük | Küçük bir hanenin ana router'ı — TV, yayın kutusu, birkaç telefon ve bilgisayar — ve sırt çantasına sığacak kadar küçük |
| GL-AXT1800 | Taşınabilir | 300 $ | 2 yıl Temel plan hizmeti | Çift bantlı Wi‑Fi 6, bir gigabit WAN ve iki gigabit LAN portu, boyutu GL-MT3000 kadar | Yolda Wi‑Fi'ın yanında iki cihazı aynı anda kabloyla bağlamak gerektiğinde; örneğin dizüstü ve yayın kutusu |
| GL-MT3600BE | Taşınabilir | 350 $ | 2 yıl Temel plan hizmeti | Çift bantlı Wi‑Fi 7 ve iki 2.5G port, boyutu GL-MT3000 kadar | Telefonu ve dizüstüsü zaten Wi‑Fi 7 destekleyen, taşınabilir bir cihazda daha hızlı kablosuz isteyenler |
| GL-MT6000 | Masaüstü | 400 $ | 2 yıl Temel plan hizmeti | İki 2.5G ve dört gigabit port, harici antenler, en yüksek işlem gücü | Büyük evler, çok sayıda cihaz (bir düzine ve üzeri), gigabitin üzerinde genişbant, 4K ve konsol oyunları ya da küçük bir ofis. Tek router olarak sabit bir yerde durur |

Dahil olan süre Temel plana göredir; Standart planda 12 ay, Pro'da 6 ay, Elit'te 3 ay, Kurumsal'da 1 ay verilir, Zirve'de ayrıca süre verilmez; değer her durumda aynıdır. Dünya geneline ücretsiz kargo, genellikle 3–14 gün. Altı ay garantilidir; router için ücret iadesi yapılmaz.

### Duruma göre hızlı seçim

- TV'si ve yayın kutusu Çin ya da yurt dışı video izlemesi gereken bir daire ya da küçük hane → GL-MT3000
- Çoğunlukla evde, ama ara sıra seyahate de götürmek istiyorsunuz → GL-MT3000
- Taşınabilir olsun, iki cihaz aynı anda kabloyla bağlansın → GL-AXT1800
- Yeni telefon ve dizüstüler Wi‑Fi 7 destekliyor, taşınabilir bir cihazda en hızlı kablosuzu istiyorsunuz → GL-MT3600BE
- Büyük ev, çok cihaz, gigabitin üzerinde genişbant ya da ortak ofis → GL-MT6000
- Teknikten anlamayan anne babanız için kurulum → GL-MT3000, yazılımı yüklü olarak alın: fişe takın, çalışsın

## Neden ilk önerimiz GL-MT3000

- **Tek cihaz, iki görev.** Küçük bir hanenin ana router'ı olacak kadar güçlü, yanınızda taşıyacak kadar küçük. Dördü arasında ikisini birden yapabilen tek model bu.
- **Çabuk eskimez.** Wi‑Fi 6 ve 2.5G port, çoğu ev genişbandına göre pay bırakır.
- **Fiyatı en düşük.** 2 yıl Temel plan hizmetiyle 250 $; dördünün en ucuzu, GL-AXT1800'den 50 $ daha ucuz, üstelik 2.5G portlu.
- **En iyi tanıdığımız model.** Kendi test cihazımız bu modeldir, yeni yazılım önce onda denenir ve [yazılım yükleme video anlatımı](02-flash-firmware-yourself.md) da onunla çekildi. Bir sorunla karşılaştığınızda karşılaştırmak için aynı cihaz masamızda durur.

Ne zaman seçmemeli: İki kablo portlu taşınabilir bir cihaz için GL-AXT1800; Wi‑Fi 7 destekleyen cihazlar için GL-MT3600BE; büyük ev, çok sayıda cihaz ya da gigabitin üzerinde genişbant için doğrudan GL-MT6000'e gidin.

## Kurulumdan sonra en sık görülen üç sorun

- **Wi‑Fi sinyali zayıf, yalnızca 20 dBm**: Yazılım kablosuz gücü bulunduğunuz ülkenin düzenlemelerine göre otomatik ayarlar ve router bir kez internete çıktıktan sonra ancak ülkenizin seviyesine geçer. Yazılımı yükledikten hemen sonra önce ağ kablosunu takın.
- **Çin siteleri yavaşladı** (Çin'deyken): Bölünmüş yönlendirme kapalı ve her şey hattan geçiyor. Modu yeniden bölünmüş yönlendirmeye alın: Çin'den yurt dışı hizmetlere erişirken varsayılan olarak yalnızca engellenen siteler hattı kullanır; Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler doğrudan bağlanır.
- **Çin'deyken bir yabancı site açılmıyor**: "VPN settings" (VPN ayarları) altında, akıllı bölünmüş yönlendirme kısmında "Blocked sites only" (yalnızca engellenen siteler hattan geçer) işaretini kaldırın (ya da geçici olarak "Global"e (tam) geçin) ve yeniden deneyin; o zaman açılıyorsa site engelli ama henüz listede değildir, adresi müşteri hizmetlerine gönderin.
- **Yurt dışındasınız ve Çin içeriği istiyorsunuz**: Reverse Split'i (ters bölünmüş yönlendirme) seçin. Ters bölünmüş yönlendirme yönü çevirir — yalnızca Çin anakarası IP'leri Çin'e giden hattan geçer, diğer tüm siteler doğrudan yerel genişbandınızı kullanır. Çin videoları, müzik ve uygulamalar Çin adresi görür; yerel siteler ve yayın platformları dolambaçsız açılır. Yazılım yönü router'ın bulunduğu yere göre kendisi seçer, bu yüzden nadiren değiştirmeniz gerekir. Bkz. [03 · Router'da bölünmüş yönlendirme](03-router-split-routing.md).
- **Bir cihaz VPN'den geçmiyor ya da her şey çalışırken yalnızca engellenen siteler açılmıyor**: O cihazda kendi özel DNS'i ayarlıdır (Android'de "Özel DNS", tarayıcıda Güvenli DNS); bu yüzden router hangi siteyi sorguladığını göremez. Kapatın.

## SSS

**Router bir cihaz mı sayılır?** Her router hesapta bir yer kaplar (plana göre aynı anda çevrim içi: Temel 2, Standart 4, Pro 8, Elit 16, Kurumsal 32, Zirve 64 cihaz); arkasındaki cihazlar ayrıca sayılmaz.

**Yurt dışındayken Çin videosu izlemek için kullanılabilir mi?** Evet, hat için Çin bölgesini seçin. Router tüm yerel ağı VPN'e alır ve cihazların IPv6'sı ile DNS'i dışarıya ulaşamaz; bu yüzden "telif kısıtlaması" uyarıları, telefonun tek başına bağlandığı duruma göre daha seyrek çıkar. Bkz. [06](06-unlock-chinese-video-with-router.md).

**Yazılımda arka kapı var mı?** OpenWrt'den derlenir; üzerine yalnızca VPN'e bağlanan bileşen ve bölünmüş yönlendirme kuralları eklenmiştir. VPN faturalandırma için yalnızca bağlantı süresini ve toplam trafiği kaydeder, neleri ziyaret ettiğinizi kaydetmez.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-07) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-07) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 30 dakika ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Temel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
