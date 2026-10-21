# 03 · Router'da bölünmüş yönlendirme nedir

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/router-firmware?utm_source=github&utm_content=router-03

## Tek cümleyle

VPN'i router'a kurun; evdeki her cihaz Wi-Fi'ye bağlanır bağlanmaz otomatik olarak VPN'den geçer. TV kutuları, oyun konsolları ve yazıcılar gibi istemci kurulamayan cihazlar da yararlanır.

## Bölünmüş yönlendirme hangi sorunu çözer

Tüm trafik VPN'den geçerse iki sorunla karşılaşırsınız: Yerel siteler yavaşlar (dolambaçlı yoldan giderler) ve evdeki cihazlara ulaşılamaz (yazıcı, NAS ve router'ın yönetim sayfası yerel ağdadır ama trafik dışarı gönderilmiştir).

Bölünmüş yönlendirme, router'a bir liste vererek çalışır: Listedeki alan adları VPN'den geçer, geri kalan her şey doğrudan bağlanır. Yönün hangisi olacağı nerede olduğunuza ve hangi tarafa ulaşmak istediğinize bağlıdır ve seçtiğiniz bölgeye göre otomatik belirlenir:

- **Yurt dışındasınız ve Çin bölgesini seçtiniz (Çin'e erişim)**: Çin siteleri ve uygulamaları VPN'den geçer, geri kalan her şey doğrudan bağlanır.
- **Çin'desiniz ve yurt dışı bir bölge seçtiniz (yurt dışı hizmetlere erişim)**: Varsayılan olarak yalnızca engellenen siteler ve hizmetler VPN'den geçer; Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler (yabancı şirket siteleri, Apple ve Microsoft indirmeleri, oyun platformları vb.) dolambaçsız doğrudan bağlanır, router yokmuş gibi hızlıdır.

## Üç mod

| Mod | Trafik nereye gider | Ne zaman kullanılır |
|---|---|---|
| Global (tam) | Her şey VPN'den geçer | Geçici olarak, sorun giderirken |
| Split routing (bölünmüş) | Listedeki alan adları VPN'den, geri kalanı doğrudan | Günlük kullanımda |
| Direct (doğrudan) | Hiçbir şey VPN'den geçmez | Bir süre ihtiyacınız olmadığında |

## Çin'den yurt dışı hizmetlere erişim: yalnızca engellenen siteler

14 Ekim 2026'dan beri Çin'den yurt dışı hizmetlere erişim yönündeki bölünmüş yönlendirme, varsayılan olarak yalnızca engellenen siteleri ve hizmetleri VPN'den geçiriyor. Her gün otomatik güncellenen bir engelli siteler listesine, ayrıca Telegram gibi site adı sorgulamadan sabit adreslere bağlanan hizmetlere dayanır. Çin'den zaten sorunsuz açılan siteler, Çin'e ait olsun yabancı olsun, doğrudan bağlanır.

Anahtar, router yönetim sayfasında "VPN settings" (VPN ayarları) altında, akıllı bölünmüş yönlendirme kısmındadır: varsayılan olarak işaretli "Blocked sites only" (yalnızca engellenen siteler hattan geçer) onay kutusu. İşareti kaldırırsanız önceki davranışa dönülür: Çin siteleri doğrudan, geri kalan her şey VPN'den.

Ekim 2026'dan önce yüklenen yazılımlarda bu kutu henüz görünmez; yeni varsayılan bu router'lara otomatik güncellemelerle zaten uygulanır. Değiştirmek için müşteri hizmetleriyle iletişime geçin, uzaktan yapabilirler.

Yurt dışından Çin'e erişim yönü değişmedi.

## Tuzaklar

- **Bölünmüş yönlendirmede bir site açılmıyor**: Önce listede olup olmadığına bakın. Listede olmayan siteler doğrudan bağlanır; o site zaten baştan açılamıyorsa bölünmüş yönlendirme işe yaramaz. Doğrulamak için geçici olarak "Global"e (tam) geçin.
- **Çin'deyken bir yabancı site açılmıyor**: Akıllı bölünmüş yönlendirme kısmında "Blocked sites only" işaretini kaldırın (ya da geçici olarak "Global"e geçin) ve yeniden deneyin. O zaman açılıyorsa site engelli ama henüz listede değildir; adresi müşteri hizmetlerine gönderin.
- **Engellenen siteler açılmıyor ama geri kalan her şey çalışıyor**: Cihazda büyük olasılıkla şifreli bir DNS ayarı açıktır (Android'de "Özel DNS", tarayıcıda "Güvenli DNS"); router hangi siteyi sorguladığını göremez. Bu ayarı kapatın.
- **Bağlandıktan sonra yazıcıya ya da NAS'a ulaşılamıyor**: Bu, yerel ağ adreslerinin de dışarı gönderildiği anlamına gelir. Bölünmüş yönlendirme kurallarının 192.168.x.x gibi özel adres aralıklarını hariç tutup tutmadığını kontrol edin.
- **Router'ın performansı** tavanı belirler. Eski bir router'ın işlemcisi şifreli trafikte tam yüke çıkar; bu da tüm evin yavaşlaması olarak görülür. Bu durumda sorun VPN hattında değildir.

## Bir hesap, bir router

Çoğu hizmet router'ı hesaba (MAC adresiyle) bağlar. Bir hesap bir router'a bağlanır; router değiştirirken önce bağlantıyı kaldırırsınız. Böylece hesap yalnızca size ait kalır.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-03) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-03) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
