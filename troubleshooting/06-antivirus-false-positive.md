# 06 · Mac uygulamanın "hasarlı" olduğunu söylediğinde ne yapmalı

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/antivirus-false-positive?utm_source=github&utm_content=troubleshooting-06

Önce sonuç: Dosya bozuk değil ve kimse onunla oynamadı. Mac'te Hiddify'a çift tıkladığınızda "hasarlı ve açılamıyor" ya da "geliştirici doğrulanamıyor" uyarısı çıkıyorsa onu engelleyen sistemin Gatekeeper'ıdır; izin vermek için aşağıdaki adımları izleyin.

Windows'ta Hiddify kurulumu güncel testlerimizde artık virüs uyarısı vermiyor. Kurduğunuz antivirüs yazılımı yine de işaretlerse burada da aynı sırayı izleyin: önce doğrulayın, sonra izin verin.

## Neden engelleniyor

**Bir web sayfasından indirilen dosyalara karantina işareti eklenir.** macOS'taki Gatekeeper bu işareti görünce uygulamayı engeller. Mesaj bazen "hasarlı", bazen "geliştirici doğrulanamıyor" der; neden aynıdır.

Bizim yaptığımız: Masaüstü istemcisi, kaynak açık projenin yayımladığı paketin **değiştirilmemiş bir kopyasıdır**. Onu değiştirmiyor, yeniden paketlemiyor, içine bir şey eklemiyoruz; yalnızca indirmeyi kolaylaştırmak için kendi indirme sitemizde barındırıyoruz.

## Önce kendiniz doğrulayın; körü körüne izin vermeyin

Bir uygulamaya izin vermek, sistemin onu denetlemeyi bırakması demektir; bu yüzden sıra önce doğrulamak, sonra izin vermektir.

**İkinci bir kontrol için VirusTotal'a yükleyin.** Kurulum dosyasını [virustotal.com](https://virustotal.com/gui/home/upload) sayfasına sürükleyin. Birkaç sezgisel motorun işaretlemesi, ana akım üreticilerin ise hepsinin temiz bulması, hatalı alarmın tipik görüntüsüdür. Ana akım motorların çoğu işaretliyorsa **kurmayın**, doğrudan bize gelin.

Ancak kontrolden geçtikten sonra devam edin. Emin değilseniz önce destekle iletişime geçin, indirme sitesini kontrol edelim.

## En dardan en genişe, izin vermenin üç yolu

Çift tıkladıktan sonra ""İstemci adı" hasarlı ve açılamıyor. Çöp Sepeti'ne taşımanız gerekir." ya da "geliştirici doğrulanamadığı için açılamıyor" mesajını görebilirsiniz. Aşağıdaki üç adım en dardan en genişe doğru gider; **ilk adım işe yarıyorsa üçüncüyü kullanmayın**.

1. Finder'da "Uygulamalar" altında bulun, simgeye Control tuşuyla tıklayın (ya da sağ tıklayın), "Aç"ı seçin ve açılan pencerede bir kez daha "Aç"a tıklayın. Bu, yalnızca bu uygulama için tek seferlik bir izindir.
2. Sağ tık menüsünde kullanılabilir bir "Aç" yoksa "Sistem Ayarları" → "Gizlilik ve Güvenlik"e gidin ve Güvenlik bölümüne kadar aşağı kaydırın. ""İstemci adı" tanınmış bir geliştiriciden olmadığı için kullanımı engellendi" gibi bir mesaj görürsünüz. Sağdaki "Yine de Aç"a tıklayın ve onaylamak için parolanızı girin.
3. Mesaj "hasarlı" diyorsa ilk iki adım genellikle işe yaramaz. "Terminal"i açın ve `sudo xattr -dr com.apple.quarantine` komutunu, ardından uygulamanın yolunu (genellikle `/Applications/` altındaki bir `.app`) yazarak çalıştırın; Return'e basın, giriş parolanızı girin ve uygulamayı yeniden açın. Bu komutun yaptığı, indirme kaynağını işaretleyen karantina işaretini kaldırmaktır.

İlk açılışta sistem bir ağ uzantısının kurulmasına izin vermek için de parolanızı ister. Uygulama trafiği ancak siz onayladıktan sonra devralabilir.

Birkaç hatırlatma:

- `xattr` komutunu **yalnızca kaynağını zaten doğruladığınız dosyalarda** kullanın; nasıl doğrulanacağı için önceki bölüme bakın.
- Gatekeeper'ı tamamen kapatmak için `sudo spctl --master-disable` **kullanmayın**. Bu tüm bilgisayarın korumasını kapatır; sağ tık → Aç ise yalnızca tek bir uygulamayı etkiler.
- macOS 15'ten beri Apple sağ tık → Aç yolunu sıkılaştırdı ve çoğu durumda "Sistem Ayarları" adımından geçmeniz gerekiyor. Bu, sistem davranışındaki bir değişikliktir, paketimizle ilgili bir sorun değil.
- Şirketin verdiği Mac'ler çoğu zaman bir MDM profiliyle yönetilir ve yukarıdaki üç adımın hepsi devre dışı olabilir. Zorlamayın; aşağıdaki üç seçenekten birini kullanın.

## İzin vermek istemiyor musunuz? Bu üçünden birini kullanın

Bunların istemcileri **macOS'ta çift tıklayınca çalışır** ve yukarıdaki mesajların hiçbirini göstermez. Hesap aynıdır, ek ödeme yoktur:

- **Özel ağ (resmî Tailscale istemcisi)**: Kurulur kurulmaz çalışır, uzun süre açık bırakmaya uygundur
- **OpenVPN Connect**: OpenVPN'in kendi kurulum dosyası; yalnızca yapılandırmayı içe aktarın
- **Cisco Secure Client**: Kurumsal düzeyde bir istemci; pek çok şirket bilgisayarında zaten kurulu

## SSS

**Programınızda gerçekten virüs var mı?**
Hayır. Kaynak açık projenin resmî yayın paketinin değiştirilmemiş bir kopyasıdır. Ama yalnızca bizim sözümüze güvenmemelisiniz; kendiniz kontrol etmenin yolu yukarıda: VirusTotal'a yükleyip motorların kararlarının nasıl dağıldığına bakın.

**Windows'ta yine işaretlenir mi?**
Şu an testlerimizde Windows'un yerleşik güvenlik merkezi Hiddify kurulumunu artık işaretlemiyor. Kurduğunuz antivirüs yazılımı yine de işaretlerse önce ikinci bir kontrol için VirusTotal'a yükleyin; temiz çıkarsa antivirüs yazılımında Hiddify'ın kurulum klasörünü güvenilir olarak ayarlayın. Kurabilmek için gerçek zamanlı korumayı kapatmayın.

**Mac'e kurduktan sonra açılmıyor. İndirme mi bozuldu?**
Hayır. Gatekeeper engellediği için açılmıyor. Yukarıdaki üç izin yoluyla halledin.

**Mac'e bunun için antivirüs yazılımı kurmalı mıyım?**
Hayır. macOS'ta sizi engelleyen antivirüs yazılımı değil, sistemin yerleşik Gatekeeper'ıdır. Üçüncü taraf bir antivirüs kurmak bu mesajı ortadan kaldırmaz, üstelik yeni engeller ekleyebilir.

**Bu sorun telefonlarda da olur mu?**
iOS'ta App Store'dan kurulduğu için bu sorun yoktur. Android ara sıra bilinmeyen kaynaklar konusunda uyarır; izin vermeniz yeterlidir.

---

[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=troubleshooting-06) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-06) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
