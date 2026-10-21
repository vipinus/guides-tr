# 08 · Yazılım yüklendikten sonra: kendi başına yaptıkları ve bilmeniz gereken birkaç anahtar

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/router-firmware?utm_source=github&utm_content=router-08

Bu sitenin yazılımını yükledikten ya da yazılımı yüklenmiş bir cihaz satın aldıktan sonra tek yapmanız gereken yönetim sayfasında hesabınıza giriş yapmaktır. Bu yazı, yazılımın **kendi başına yaptığı** işleri ve dokunmanız gerekebilecek birkaç anahtarı anlatıyor. İlk adımlar için [01](01-plug-and-play-router.md), bölünmüş yönlendirme için [03](03-router-split-routing.md), router bağlama ve değiştirme için [05](05-mac-binding-and-replacing.md) yazısına bakın.

## Kendi başına yaptıkları

| Ne | Nasıl çalışır | Sizin yapmanız gereken |
|---|---|---|
| Bileşen ve bölünmüş yönlendirme listesi güncellemeleri | Açılışta kontrol eder ve varsa güncellemeyi indirir, güncelleme **bir sonraki açılışta devreye girer**; Çin'den yurt dışı hizmetlere erişimde kullanılan engelli siteler listesi de her gün otomatik güncellenir | Hiçbir şey; değişen hat adresleri ve listeye eklenen siteler otomatik olarak alınır |
| Wi‑Fi ülke kodu | İnternete çıkınca bulunduğu ülkeyi algılar ve kablosuz gücü ile kanalları otomatik ayarlar | Yazılımı yükledikten hemen sonra **önce ağ kablosunu takın** ki bir kez internete çıksın; internete çıkmadan önce sinyalin zayıf olması normaldir |
| Süre dolması | Hesabın süresi dolunca VPN'den geçmeyi bırakır; yerel ağ her zamanki gibi çalışır | Yenileyince kendiliğinden toparlanır, yeniden giriş yapmanız gerekmez |
| Router bağlama | İlk giriş bu router'ı hesaba kaydeder | Router değiştirmeden önce sitede bağı kaldırın |

Yalnızca yazılımın tamamının büyük sürüm yükseltmesi sysupgrade dosyasını yüklemeyi gerektirir. Bu yılda yalnızca birkaç kez olur ve site sizi bilgilendirir.

## Dokunmanız gerekebilecekler

- **Bölünmüş yönlendirme modu**: Split routing (bölünmüş, varsayılan) / Global (tam) / Direct (doğrudan). Bir site açılmıyorsa doğrulamak için önce Global'e geçin: Global'de açılıyorsa listede değildir, eklenmesi için adresi müşteri hizmetlerine iletin; Global'de de açılmıyorsa sorun sitenin kendisindedir.
- **Bölge**: Yönetim sayfasından seçilir. Yurt dışından Çin içeriği izlemek için Çin bölgesini, Çin'den yurt dışı hizmetlere ulaşmak için yurt dışı bir bölgeyi seçin.
- **Blocked sites only** (yalnızca engellenen siteler hattan geçer): "VPN settings" (VPN ayarları) altında, akıllı bölünmüş yönlendirme kısmında bir onay kutusu; varsayılan olarak işaretlidir. Yalnızca Çin'den yurt dışı hizmetlere erişim yönünde geçerlidir (Çin'desiniz ve yurt dışı bir bölge seçtiniz). İşaretliyken yalnızca engellenen siteler ve hizmetler VPN'den geçer (her gün otomatik güncellenen bir engelli siteler listesine ve Telegram gibi sabit adreslere bağlanan hizmetlere dayanarak); Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler (yabancı şirket siteleri, Apple ve Microsoft indirmeleri, oyun platformları vb.) dolambaçsız doğrudan bağlanır. İşareti kaldırırsanız önceki davranışa dönülür: Çin siteleri doğrudan, geri kalan her şey VPN'den. Çin'deyken bir yabancı site açılmıyorsa işareti kaldırıp (ya da geçici olarak Global'e geçip) yeniden deneyin; o zaman açılıyorsa site engelli ama henüz listede değildir, adresi müşteri hizmetlerine gönderin. Ekim 2026'dan önce yüklenen yazılımlarda bu kutu henüz görünmez (yeni varsayılan otomatik güncellemelerle zaten uygulanır); değiştirmek için müşteri hizmetleriyle iletişime geçin, uzaktan yapabilirler. Yurt dışından Çin'e erişim yönü bu anahtardan etkilenmez.
- **Automatically select the fastest line** (en hızlı hattı otomatik seç): Bölgenin altında bulunur, varsayılan olarak kapalıdır; ağ kalitesi kötüyse önerilir.

  | | Kapalı (varsayılan) | Açık |
  |---|---|---|
  | Hangi hat kullanılır | Her zaman seçtiğiniz bölge | Mevcut hatlar arasından gecikmesi en düşük ve paket kaybı az olanı otomatik seçer, sonra düzenli aralıklarla yeniden test eder ve kötüleşirse otomatik geçiş yapar |
  | Çıkış ülkesi | Seçilen bölge | Çin bölgesi seçiliyse: Yalnızca Çin'deki hatlar arasından seçer, çıkış Çin'de kalır; yurt dışı bir bölge seçiliyse: Tüm yurt dışı hatlar arasından seçer ve **çıkış ülkesi seçilen bölgeden farklı olabilir** (örneğin Japonya'yı seçtiniz ama aslında Singapur'dan çıkıyorsunuz) |
  | Kime uygun | Sabit bir ülke gerektiren durumlar: belirli bir ülkenin yayın hizmetlerini izlemek, bölgeye duyarlı bankalar ve hesaplar | Evdeki ağ dengesizse ya da bölge sık sık takılıyorsa; yalnızca hız istiyor, hangi ülkeden çıktığınızı umursamıyorsanız |

  Anahtarı değiştirdiğinizde yönetim sayfası "Switching automatic selection…" (otomatik seçime geçiliyor) gösterir ve geçiş tamamlanana kadar sayfayı kilitler. Bu sırada ağ kısa bir süre kopar, bu normaldir. Yönetim sayfasındaki "Current exit" (geçerli çıkış) hangi hattın gerçekte kullanıldığını gösterir.
- **Yönetim parolası ve Wi‑Fi parolası**: Fabrika değerleri herkesin bildiği varsayılanlardır; giriş yaptıktan sonra ilk iş bunları değiştirin.

## Televizyonlar, TV kutuları ve yaşlı aile büyüklerinin cihazları

- Bu router'ın Wi‑Fi'sine ya da kablolu ağına bağlanmaları yeterli; uygulamaların Çin anakarası sürümü hemen oynar. Uluslararası sürümlerin (iQIYI, WeTV) içerik kataloğu farklıdır, bu yüzden Çin anakarası sürümünü kurun.
- Bir cihaz bağlı ama VPN'den geçmiyor ya da her şey çalışırken yalnızca engellenen siteler açılmıyor: Büyük olasılıkla cihazda kendi özel DNS'i ayarlıdır (Android'de "Özel DNS", tarayıcıda Güvenli DNS); bu yüzden router hangi siteyi sorguladığını göremez. Kapatın.
- Bir cihazın her zaman doğrudan bağlanmasını istiyorsanız (şirket VPN'ine bağlanması gereken bir iş bilgisayarı gibi): Onu üstteki router'ın ya da modemin Wi‑Fi'sine bağlayın.

## SSS

**Bireysel plan router kullanabilir mi?** Evet. Bireysel, Aile ve Kurumsal planların hepsi router'ı destekler, plan değiştirmenize gerek yok.

**Router kaç cihaz hakkı kaplar?** Bir tane; arkasındaki cihazlar sayılmaz.

**Yazılımda arka kapı var mı?** OpenWrt'den derlenmiştir; yalnızca VPN'e bağlanan bileşen ve bölünmüş yönlendirme kuralları eklenmiştir. VPN, faturalandırma için yalnızca bağlantı süresini ve toplam trafiği kaydeder.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-08) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-08) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerlidir
