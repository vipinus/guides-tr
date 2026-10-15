# 07 · Router almalı mısınız, dört model arasından nasıl seçilir

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/router?utm_source=github&utm_content=router-07

Router çözümü "cihaz çok, bazılarına istemci de kurulamıyor" sorununu çözer: VPN router'da bir kez kurulur; TV, oyun konsolu, akıllı hoparlör ve yaşlı aile büyüğünüzün telefonu hiçbir şey kurmadan otomatik olarak ondan geçer. Tek gereken, yazılım yüklenebilen bir router ve on dakikalık bir yükleme işlemidir. **Bireysel, Aile ve Kurumsal hesapların hepsi router kullanabilir.**

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
| GL-MT300N-V2 | Mini | 200 $ | 12 ay hizmet | Avuç içi boyutunda, USB ile beslenir (powerbank ile çalışabilir); yalnızca 2,4 GHz Wi‑Fi, 100 Mbps portlar | Tek başına seyahat eden biri: otelin kablolu internetine ya da Wi‑Fi'sine bağlanıp telefon ve dizüstüyle gezinmek, 1080p izlemek. Evde ana router olmaya uygun değil |
| **GL-MT3000** | Taşınabilir | 300 $ | 24 ay hizmet | Çift bantlı Wi‑Fi 6 ve 2.5G port, avuç içinden biraz büyük | Küçük bir hanenin ana router'ı — TV, yayın kutusu, birkaç telefon ve bilgisayar — ve sırt çantasına sığacak kadar küçük |
| GL-MT6000 | Masaüstü | 400 $ | 24 ay hizmet | İki 2.5G ve dört gigabit port, harici antenler, en yüksek işlem gücü | Büyük evler, çok sayıda cihaz (bir düzine ve üzeri), gigabitin üzerinde genişbant, 4K ve konsol oyunları ya da küçük bir ofis. Tek router olarak sabit bir yerde durur |
| GL-XE3000 | Mobil | 400 $ | 24 ay hizmet | Dahili 5G/4G ve batarya; bir SIM kartla kendi başına ağ kurar, kablolu internete de bağlanır | Sabit genişbandın olmadığı yerler: karavan, şantiye, fuar, kısa dönem kiralık ev; ya da ev hattı için yedek |

Dahil olan aylar Bireysel plana göredir; Aile planında yarısı, Kurumsal planda dörtte biri verilir, değer her durumda aynıdır. Dünya geneline ücretsiz kargo, genellikle 3–14 gün; 30 gün içinde iade edilebilir.

### Duruma göre hızlı seçim

- Tek başına seyahat, otelde konaklama, bütçe kısıtlı → GL-MT300N-V2
- TV'si ve yayın kutusu Çin ya da yurt dışı video izlemesi gereken bir daire ya da küçük hane → GL-MT3000
- Çoğunlukla evde, ama ara sıra seyahate de götürmek istiyorsunuz → GL-MT3000
- Büyük ev, çok cihaz, gigabitin üzerinde genişbant ya da ortak ofis → GL-MT6000
- Genişbant yok ya da çoğu zaman yoldasınız → GL-XE3000
- Teknikten anlamayan anne babanız için kurulum → GL-MT3000, yazılımı yüklü olarak alın: fişe takın, çalışsın

## Neden ilk önerimiz GL-MT3000

- **Tek cihaz, iki görev.** Küçük bir hanenin ana router'ı olacak kadar güçlü, yanınızda taşıyacak kadar küçük. Dördü arasında ikisini birden yapabilen tek model bu.
- **Çabuk eskimez.** Wi‑Fi 6 ve 2.5G port, çoğu ev genişbandına göre pay bırakır. Mini modelde yalnızca 2,4 GHz Wi‑Fi ve 100 Mbps portlar var; evde darboğaz olur.
- **Fiyatı hesaplı.** 24 ay Bireysel plan hizmetiyle 300 $; mini model ise 12 ayla 200 $. Dahil olan hizmeti hesaba katınca fazladan verdiğiniz 100 $ hem belirgin biçimde daha iyi bir cihaz hem de bir yıl daha getirir.
- **En iyi tanıdığımız model.** Kendi test cihazımız bu modeldir, yeni yazılım önce onda denenir ve [yazılım yükleme video anlatımı](02-flash-firmware-yourself.md) da onunla çekildi. Bir sorunla karşılaştığınızda karşılaştırmak için aynı cihaz masamızda durur.

Ne zaman seçmemeli: Büyük ev, çok sayıda cihaz ya da gigabitin üzerinde genişbant için doğrudan GL-MT6000'e gidin; sabit genişbant yoksa GL-XE3000; yalnızca tek kişinin seyahatleri içinse ve en önemlisi fiyatsa GL-MT300N-V2 yeterlidir.

## Kurulumdan sonra en sık görülen üç sorun

- **Wi‑Fi sinyali zayıf, yalnızca 20 dBm**: Yazılım kablosuz gücü bulunduğunuz ülkenin düzenlemelerine göre otomatik ayarlar ve router bir kez internete çıktıktan sonra ancak ülkenizin seviyesine geçer. Yazılımı yükledikten hemen sonra önce ağ kablosunu takın.
- **Çin siteleri yavaşladı** (Çin'deyken): Bölünmüş yönlendirme kapalı ve her şey hattan geçiyor. Modu yeniden bölünmüş yönlendirmeye alın: Çin'den yurt dışı hizmetlere erişirken varsayılan olarak yalnızca engellenen siteler hattı kullanır; Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler doğrudan bağlanır.
- **Çin'deyken bir yabancı site açılmıyor**: "VPN settings" (VPN ayarları) altında, akıllı bölünmüş yönlendirme kısmında "Blocked sites only" (yalnızca engellenen siteler hattan geçer) işaretini kaldırın (ya da geçici olarak "Global"e (tam) geçin) ve yeniden deneyin; o zaman açılıyorsa site engelli ama henüz listede değildir, adresi müşteri hizmetlerine gönderin.
- **Yurt dışındasınız ve Çin içeriği istiyorsunuz**: Reverse Split'i (ters bölünmüş yönlendirme) seçin. Ters bölünmüş yönlendirme yönü çevirir — yalnızca Çin anakarası IP'leri Çin'e giden hattan geçer, diğer tüm siteler doğrudan yerel genişbandınızı kullanır. Çin videoları, müzik ve uygulamalar Çin adresi görür; yerel siteler ve yayın platformları dolambaçsız açılır. Yazılım yönü router'ın bulunduğu yere göre kendisi seçer, bu yüzden nadiren değiştirmeniz gerekir. Bkz. [03 · Router'da bölünmüş yönlendirme](03-router-split-routing.md).
- **Bir cihaz VPN'den geçmiyor ya da her şey çalışırken yalnızca engellenen siteler açılmıyor**: O cihazda kendi özel DNS'i ayarlıdır (Android'de "Özel DNS", tarayıcıda Güvenli DNS); bu yüzden router hangi siteyi sorguladığını göremez. Kapatın.

## SSS

**Router bir cihaz mı sayılır?** Hesapta bir yer kaplar (plana göre aynı anda çevrim içi: Bireysel 2, Aile 4, Kurumsal 8 cihaz); arkasındaki cihazlar ayrıca sayılmaz.

**Yurt dışındayken Çin videosu izlemek için kullanılabilir mi?** Evet, hat için Çin bölgesini seçin. Router tüm yerel ağı VPN'e alır ve cihazların IPv6'sı ile DNS'i dışarıya ulaşamaz; bu yüzden "telif kısıtlaması" uyarıları, telefonun tek başına bağlandığı duruma göre daha seyrek çıkar. Bkz. [06](06-unlock-chinese-video-with-router.md).

**Yazılımda arka kapı var mı?** OpenWrt'den derlenir; üzerine yalnızca VPN'e bağlanan bileşen ve bölünmüş yönlendirme kuralları eklenmiştir. VPN faturalandırma için yalnızca bağlantı süresini ve toplam trafiği kaydeder, neleri ziyaret ettiğinizi kaydetmez.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-07) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-07) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
