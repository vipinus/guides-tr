# 02 · Yazılımı kendiniz yükleyin: orijinal yazılımdan bizimkine adım adım (videolu)

> Video anlatım (yaklaşık iki buçuk dakika, İngilizce ya da Çince anlatım): https://www.leotun.com/tr/video/router-flash?utm_source=github&utm_content=router-02
>
> Sitedeki sürüm: https://www.leotun.com/tr/guides/router-flash?utm_source=github&utm_content=router-02

Bu yazı, modeli desteklenenler listesinde olan bir router'ı zaten elinde bulunduranlar içindir. Router'ınız hâlâ orijinal sistemiyle çalışıyor; siteyi açmaktan bütün evin bağlanmasına kadar gidiyoruz — her adımda nereye tıklayacağınız, ne göreceğiniz ve insanların nerede hata yaptığı. Gösterimde bir GL.iNet GL-MT3000 kullanılıyor. Diğer modeller de aynı adımları izler; yalnızca orijinal yönetim panelinin görünüşü farklıdır. Bunu kendiniz yapmak istemiyorsanız yazılımı yüklenmiş bir router daha az uğraştırır: bkz. [01](01-plug-and-play-router.md). Hangi modeli seçeceğiniz için bkz. [07](07-which-router-to-buy.md).

## Başlamadan önce

- **Modelinizin desteklendiğini kontrol edin.** Giriş yapın, **Router** bölümünü açın ve modelinizi markaya göre bulun. Model adından sonraki donanım revizyonunun (v1, v2 vb.) da eşleşmesi gerekir.
- **Hesabınız etkin olmalı.** Bireysel, Aile ve Kurumsal planların hepsi router kullanabilir.
- **Bir ağ kablosu hazırlayın.** Router'ın WAN portu modeminize ya da üstteki router'a gider. Yükleme sırasında bilgisayarınızı da router'a kabloyla bağlamanız en iyisidir; Wi-Fi'den daha sağlamdır.
- **Orijinal yazılımın bir kopyasını saklayın.** Bir gün geri dönmek isterseniz diye modelinizin orijinal yazılımını üreticinin sitesinden indirin.

## 1. adım: Yazılımı sitede oluşturun

1. Giriş yapın ve gezinme çubuğunda **Router**'a tıklayın.
2. Modelinizi bulup **Firmware**'e tıklayın ya da aşağıya, "Firmware Derle" bölümüne kaydırıp modeli marka listesinden seçin.
3. **Derlemeyi Başlat**'a tıklayın.

Önceden bilmeniz gereken birkaç şey:

- **Bir derleme 3 ila 5 dakika sürer.** Yazılım hesabınız için o anda oluşturulur, hazır bir dosya değildir. Yoğun saatlerde derleme bir kuyrukta bekleyebilir. Bu olduğunda sayfa size söyler — sadece bekleyin, yeniden tıklamanıza gerek yok.
- **Hazır olunca bir e-posta alırsınız.** "Son Derlemeler" altındaki kayıt "Tamamlandı" olur ve gelen kutunuza bir bildirim düşer.
- **Yazılımın arayüz dili sitenin diline göre belirlenir.** Örneğin siteyi Türkçe kullanıyorsanız router'ın yönetim sayfaları da Türkçe olur. Başka bir dil için önce sitenin dilini değiştirin, sonra derleyin.
- **İndirme bağlantısı bir gün geçerlidir.** Süresi dolarsa yeniden derlemeniz yeterli.

## 2. adım: İndirin ve arşivden çıkarın

1. "Son Derlemeler" altında **İndir**'e tıklayın. Bir zip dosyası inecek.
2. İndirilenler klasörünüzü açın ve dosyayı **arşivden çıkarın**.
3. Çıkan klasörde yazılım dosyası bulunur.

Hangi dosyayı kullanmalı:

| Router'ınızda şu an çalışan | Kullanılacak dosya |
|---|---|
| GL.iNet orijinal sistemi (videodaki durum) | sonu `sysupgrade.bin` ile biten |
| Başka bir markanın orijinal sistemi | adında `factory` geçen |
| Zaten bizim yazılımımız, güncelleme yapıyorsunuz | adında `sysupgrade` geçen |

Zip'te yalnızca bir dosya varsa kullanacağınız odur.

> ⚠️ **Bu yazılım yalnızca size özeldir.** Router'ın yüklemeden sonra kendi kendine giriş yapabilmesi için hesap bilgilerinizi içerir. Dosyayı başkasına göndermeyin ya da herkese açık paylaşmayın.

## 3. adım: Orijinal yönetim panelinden yükleyin

Örnek olarak GL.iNet:

1. Bilgisayarınızı router'a bağlayın, tarayıcıda orijinal yönetim panelini açın (GL.iNet'te `http://192.168.8.1`) ve yönetici parolasıyla giriş yapın.
2. Soldaki menüde **System** → **Upgrade**'i (Sistem → Yükseltme) açın.
3. **Firmware Local Upgrade** (yerel yazılım yükseltme) sekmesine geçin.
4. Yükleme alanına tıklayıp arşivden çıkardığınız yazılım dosyasını seçin.
5. Doğrulama **Pass** (geçti) gösterene kadar bekleyin.
6. **"Keep Settings"i (ayarları koru) kapatın.** İnsanların en sık atladığı adım budur. İki sistem aynı yapılandırma biçimini kullanmaz ve eski ayarları korumak her türlü tuhaf soruna yol açar.
7. **Install**'a (yükle) tıklayın.

Sayfa bir ilerleme halkasıyla "Upgrading and rebooting…" (yükseltiliyor ve yeniden başlatılıyor) olur. **İki üç dakika sürer. Bu sırada router'ın fişini çekmeyin ve sayfayı kapatmayın.** İlerleme bittikten sonra sayfanın yüklenmemesi normaldir — router artık farklı bir sistemle çalışıyor ve hem adresi hem de Wi-Fi'si değişti. Bir sonraki adıma bakın.

Diğer markalar: Orijinal yönetim panelinde "Firmware Upgrade", "System Upgrade" ya da "Local Upgrade" gibi bir seçenek arayın, dosyayı yükleyin ve yine ayarları korumayın.

## 4. adım: Yeni Wi-Fi'ye bağlanın

Yüklemeden sonra eski Wi-Fi adı kaybolur ve yenisi görünür:

- **Wi-Fi adı: `www.anyfq.com`**
- **Wi-Fi parolası: `www.anyfq.com`** (adıyla aynı)

Bilgisayarların ve telefonların internete çıkabilmesi ya da router'ın yönetim sayfasını açabilmesi için **bu Wi-Fi'ye geçmeleri** gerekir. Router'a kabloyla bağlı bir bilgisayarın geçiş yapmasına gerek yoktur.

Yeni yönetim adresi `http://192.168.11.1` (baştaki `http://` kısmını kendiniz yazın).

## 5. adım: Kendi kendine bağlanmasını bekleyin

Giriş yok, bölge seçimi yok. **Hesabınız etkin olduğu sürece router 10 dakika içinde kendi kendine bağlanır.** Bağlandıktan sonra bu Wi-Fi'deki her cihaz — televizyonlar, TV kutuları ve oyun konsolları dahil — otomatik olarak hizmetten geçer.

Bağlandığını doğrulamak için router'a bağlı bir cihazdan normalde ulaşamadığınız bir siteyi açın ya da yönetim sayfasındaki duruma bakın.

## Sonrasında yapmaya değer iki şey

1. **Varsayılan parolaları değiştirin.** Wi-Fi parolası ve yönetim parolası kutudan çıktığı hâliyle herkesin bildiği varsayılanlardır. İkisini de yönetim sayfasından değiştirin.
2. **Yüklemeden hemen sonra Wi-Fi sinyalinin zayıf olması normaldir.** Router'ın kablosuz gücü bulunduğu yerde izin verilen seviyeye çıkarmadan önce bir kez internete çıkıp hangi bölgede olduğunu belirlemesi gerekir. Ağ kablosunu takın ve önce internete çıkmasına izin verin.

## Eski router'ı yenisiyle değiştirmek

Bir hesap aynı anda tek bir router'a bağlanır. Hesabınız daha önce başka bir router'da kullanıldıysa:

1. Giriş yapın, **Router** bölümünü açın; "Firmware Derle" başlığının altında **Eşleştirildi** durumundaki modeli ve yanında **Eşleştirmeyi kaldır**'ı göreceksiniz.
2. Eşleştirmeyi kaldır'a tıklayın. Eski router bozuk ya da elinizde olmasa bile bunu yapabilirsiniz.
3. Yeni router'da yapacak bir şey yok: **Otomatik olarak bağlanır** ve hesabınızla eşleştirilir.

Eşleştirmeyi kaldırmadan yeni router'a yazılımı yüklediyseniz o da sorun değil. Yeni router beklemeye devam eder ve siz eşleştirmeyi kaldırınca kendi kendine bağlanır.

Kuralların ayrıntısı için [05 · MAC bağlama ve router değiştirme](05-mac-binding-and-replacing.md).

## Hesabımın süresi dolarsa ne olur

Süre dolduktan sonra router trafiği hizmet üzerinden geçirmeyi bırakır, ev ağınız ise her zamanki gibi çalışmaya devam eder. **Yenilediğinizde router kendiliğinden toparlanır — yeniden giriş yapmanıza da, yazılımı yeniden yüklemenize de gerek yok.**

## Kendi kendine bağlanmadı — nasıl kontrol edilir

On dakika kadar sonra hâlâ çalışmıyorsa şunları sırayla kontrol edin:

1. **Genişbant bağlantısının kendisi çalışıyor mu?** Router'a bağlı bir cihazdan sıradan herhangi bir siteyi açın. Açılmıyorsa sorun kabloda ya da modemdedir: WAN portundaki kablonun yerine tam oturduğunu kontrol edin.
2. **Hesabın süresi dolmuş mu?** Siteye giriş yapıp bitiş tarihine bakın. Yeniledikten sonra birkaç dakika bekleyin.
3. **Hesap hâlâ eski router'a mı bağlı?** Router bölümünde eşleştirilmiş modele bakın. Bu router değilse Eşleştirmeyi kaldır'a tıklayın.
4. **Router'ı bir kez yeniden başlatın.** Fişini çekin, on saniye bekleyin, geri takın ve ona iki üç dakika verin.
5. **Elle giriş yapın.** `http://192.168.11.1` adresini açın ve router'a kullanıcı adı `root`, parola `www.anyfq.com` ile giriş yapın. Ardından **Services** → **VPN**'e (Hizmetler → VPN) gidin, hesabınızın e-postasını ve parolasını girip kaydedin.

Hâlâ olmuyor mu? Grupta sorun; bize router modelini ve yukarıdaki listede nereye kadar geldiğinizi söyleyin.

## Kendiniz yüklemenin iyi bir fikir olmadığı durumlar

Model listede yok, donanım revizyonu eşleşmiyor ya da kurtarma modu olmayan eski bir router. Bu üç durumda yazılımı yüklenmiş bir router daha az uğraştırır.

## Yükleme ters giderse

Çoğu router'ın bir kurtarma modu vardır: Fişi çekin, reset düğmesine basılı tutarak geri takın, birkaç saniye daha basılı tutun, sonra bilgisayarı kabloyla bağlayıp üreticinin talimatlarına göre orijinal yazılımı yükleyin. GL.iNet için belgelerinde "uboot" diye arayın. Önceden sakladığınız orijinal yazılım bu iş içindir.

## Sık sorulan sorular

**Yazılım yüklemek garantiyi bozar mı?** Bu üreticiye bağlıdır. GL.iNet router'lar zaten açık kaynaklı bir sistem üzerine kuruludur ve orijinal yazılıma geri döndürülebilir.

**Orijinal yazılıma geri dönebilir miyim?** Evet. "Yükleme ters giderse" bölümünde anlatılan kurtarma modunu kullanarak orijinal yazılımı yükleyin.

**Bir yazılım dosyası iki router'da kullanılabilir mi?** Hayır. Yazılım hesap başına derlenir ve bir hesap aynı anda tek bir router'a bağlanır.

**Hesap değiştirirsem yeni bir derleme gerekir mi?** Hayır. Yönetim sayfasında çıkış yapıp yeni hesapla giriş yapın.

**Gelecekteki güncellemeler yeniden yükleme gerektirir mi?** Olağan güncellemeleri router kendisi alır; sizin bir şey yapmanız gerekmez. Yalnızca büyük bir sürüm yeni bir derleme ve sysupgrade dosyasının bir kez yüklenmesini gerektirir; bu olduğunda site duyurur.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-02) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-02) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerlidir
