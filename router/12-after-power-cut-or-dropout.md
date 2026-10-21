# 12 · Elektrik kesintisi ya da kopmadan sonra router kendiliğinden toparlanır mı?

Kendi VPN router'ını kurmuş herkes muhtemelen şunu yaşamıştır: Bir elektrik kesintisi ya da kısa bir internet kesintisi olur, router yeniden açıldığında her şey normal görünür ama tünel bir türlü geri gelmez; ta ki yönetim sayfasına girip yeniden ayarlayana kadar.

## Kısa cevap

Evet, kendiliğinden toparlanır. Elektrik kesintisinden sonra yeniden açılınca, genişbant kopunca ya da tünel kullanım sırasında düşünce yazılım kendi kendine yeniden bağlanır. Yönetim sayfasına girmeniz ya da yeniden oturum açmanız gerekmez.

## Bunu nasıl yapıyor

Yazılımda sürekli çalışan bir denetleyici var ve tüneli yaklaşık yarım dakikada bir kontrol ediyor. Tünelin düştüğünü görünce yeniden bağlanıyor ve bölünmüş yönlendirmeyi yerine koyuyor.

Tünel geri gelene kadar geçen kısa sürede Çin siteleri çalışmaya devam eder. Tünel henüz kalkmadı diye evdekiler internetsiz kalmaz.

Ayarlarınız da hatırlanır: Bölge, bölünmüş yönlendirme modu ve "Automatically pick the fastest line" (en hızlı hattı otomatik seç) anahtarı yeniden başlatmadan ya da yeniden bağlanmadan sonra olduğu gibi kalır. Bölünmüş yönlendirmeyi kapattıysanız kapalı kalır.

## Hangi durumda ne olur

| Ne oldu | Sonrasında |
|---|---|
| Kesintiden sonra elektrik geri geldi | Router açılır ve tünel kendiliğinden yeniden bağlanır |
| Genişbant koptu ve geri geldi | Hat geri gelir gelmez tünel yeniden bağlanır |
| Tünel kullanım sırasında düştü | Denetleyici fark eder ve yeniden bağlar |
| Hesabın süresi doldu | Trafik tünelden geçmeyi bırakır, ev interneti çalışmaya devam eder. Yeniledikten sonra kendiliğinden geri gelir, yeniden oturum açmak gerekmez |
| Bir sunucu adresini değiştirdik | Router değişikliği kendisi takip eder. Yeniden ayarlanacak bir şey yok |

## Birkaç dakika sonra hâlâ geri gelmediyse şunlara bakın

1. **Genişbandın kendisi çalışıyor mu?** Bir Çin sitesi açın. O da açılmıyorsa sorun tünelde değil, hatta ya da modemdedir.
2. **Hesabın süresi doldu mu?** Süre dolduktan sonra tünel bağlanmaz. Siteye giriş yapıp kontrol edin.
3. **Başka bir bölge deneyin.** Yönetim sayfasından bölgeyi değiştirin. Bazen tek bir bölgede geçici bir sorun olur.
4. **Router'ı yeniden başlatın.** Fişini çekin, on saniye bekleyin, yeniden takın.
5. Bunların hiçbiri işe yaramazsa yönetim sayfasında gösterilen durumun ekran görüntüsünü desteğe gönderin.

## Yazılımı yükledikten sonraki ilk açılış

İlk açılış her zamankinden yavaştır: Yazılım bileşen güncellemelerini kontrol eder ve kablosuz gücü ayarlamak için ülkeyi algılar. **Bu ilk açılışta bir ağ kablosu takın.** Bir kez internete çıkmadan önce Wi‑Fi'nin zayıf olması normaldir.

## SSS

**Elektriğin sık kesildiği yerlerde kullanılabilir mi?** Evet. Elektrik her geri geldiğinde yeniden bağlanır.

**Router'ı belirli aralıklarla yeniden başlatmam gerekir mi?** Hayır.

**Bileşen güncellemeleri bağlantımı keser mi?** Hayır. Güncellemeler açılışta kontrol edilip indirilir ve bir sonraki açılışta devreye girer. Router kullanım sırasında birdenbire yeniden başlamaz.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-12) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-12) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
