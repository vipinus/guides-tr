# 06 · iOS bir uygulamayı yüklemenize izin vermiyorsa

iPhone'unuzda Hiddify, Tailscale ya da Telegram'ı bulamıyorsanız veya "Bu uygulama şu anda ülkenizde ya da bölgenizde mevcut değil" uyarısını görüyorsanız uygulama ortadan kalkmış değildir: App Store, Apple kimliğinizin bölgesine göre ayrı mağazalara bölünmüştür ve Çin mağazası ağ uygulamalarının çoğunu listelemez. iOS'ta bunları Çin dışı bölgeye ait bir Apple kimliğiyle App Store'dan kurarsınız; adımlar bu sayfada. Mevcut hesabınızın bölgesini değiştirmek yerine yeni bir hesap açmanızı öneririz. Aşağıda adımlar, ödeme yöntemi olarak "Yok"u seçmenin püf noktası ve başkasının paylaştığı bir hesabı neden asla kullanmamanız gerektiği var.

## Bu neden oluyor

App Store, Apple kimliğinizin bölgesine göre mağazalara bölünmüştür ve farklı bölgelerde farklı uygulamalar listelenir. Çin mağazasında ne Hiddify ne de Tailscale var; Telegram ve Discord ise bir var bir yok. Cisco Secure Client ve OpenVPN Connect çoğu bölgede mevcut. Bu bir listeleme farkıdır, uygulamalarla ilgili bir sorun değil; başka bir bölgedeki hesap bunları kurabilir.

iPhone'da bu sitenin hem Hiddify'ı hem de Özel ağı (Tailscale) App Store'dan kurulur; başka bir bölgedeki Apple kimliğine geçmek için aşağıdaki adımları izlemeniz yeterli. Android, Windows ve macOS kurulum dosyaları doğrudan bu siteden verilir ve bundan etkilenmez.

## 1. seçenek (önerilen): Çin dışı bölgede yeni bir Apple kimliği açın

1. Mevcut App Store hesabından çıkış yapın: Ayarlar → en üstteki profiliniz → Ortam ve Satın Alınanlar → Çıkış Yap. Bu yalnızca App Store'dan çıkış yapar, iCloud'dan değil; fotoğraflarınız, yedekleriniz ve kişileriniz etkilenmez.
2. App Store'da ücretsiz bir uygulama bulun, "Al"a dokunun ve istendiğinde "Yeni Apple Kimliği Oluştur"u seçin. Bölge olarak ABD, Hong Kong, Japonya ya da Singapur'dan birini, ödeme yöntemi olarak "Yok"u seçin. Bu "Yok" seçeneği yalnızca ücretsiz bir uygulamayı indirirken kaydolduğunuz yolda çıkar; doğrudan web üzerinden kaydolurken çoğu zaman sunulmaz.
3. Yeni hesapla App Store'a giriş yapın, ardından Hiddify, Tailscale ve Telegram'ı arayıp indirin.
4. Kurulduktan sonra eski hesabınıza geri dönebilirsiniz; kurulu uygulamalar her zamanki gibi çalışmaya ve güncellenmeye devam eder. Yeni bir uygulama kurmanız gerektiğinde yeniden geçiş yapın.

## 2. seçenek: Mevcut hesabınızın bölgesini değiştirin

account.apple.com adresinde oturum açıp ülkeyi ya da bölgeyi değiştirin. Önce tüm abonelikleri iptal etmeniz ve bakiyenizi bitirmeniz gerekir; bazı durumlarda yerel bir ödeme yöntemi de eklemeniz gerekir ve geri değiştirmek de bir o kadar zahmetlidir. Zaten uzun vadede bölge değiştirmeyi düşünmüyorsanız önerilmez.

## Asla yapmamanız gerekenler

- Gruplarda ya da internette dolaşan "paylaşılan hesaplar" da dahil olmak üzere başkasının paylaştığı bir Apple kimliğini kullanmayın. Hesap sahibi cihazınızı uzaktan kilitleyebilir ve kilitlenen bir iPhone'u yalnızca o açabilir; iki faktörlü kimlik doğrulama bir kez açılınca kapatılamaz, risk ve olası anlaşmazlıklar size kalır. Bu sitenin destek ekibi de hiçbir paylaşılan hesap vermez.
- Kaynağı belirsiz yapılandırma profillerini ya da "kurumsal sertifikayla imzalanmış" kurulum dosyalarını kurmayın. Bunlar mağazayı atlatmanın yaygın yollarıdır ve aynı zamanda sertifika yerleştirip trafiği ele geçirmek için bir kapıdır.

## Kurduktan sonra

Hiddify: Bu sitenin Hiddify sayfasına dönüp kodu tarayın ya da "sing-box subscription" düğmesine dokunarak kopyalayın, sonra Hiddify'a geçip ekleyin. Tailscale: Önce resmî hesaptan çıkış yapın, ardından Özel ağ sayfasındaki adımları izleyerek bu sitenin kontrol sunucusu adresini girin. Telegram, Discord: Bu sitenin İletişim sayfasına gidip kodu tarayarak gruba katılın.

## SSS

**Başka bir bölgede kaydolmak için kredi kartı gerekir mi?** Hayır. 1. seçenekteki yolda (ücretsiz bir uygulamayı indirirken kaydolmak) ödeme yöntemi olarak "Yok"u seçebilirsiniz.

**Yeni hesap iCloud'umu ve fotoğraflarımı etkiler mi?** Hayır. Hesabı yalnızca App Store'da değiştirirsiniz; iCloud eski hesabınızda kalır.

**iPad'de de aynı mı?** Evet, iPadOS aynı App Store kurallarına uyar.

**Android telefonlarda da bu sorun var mı?** Hayır. Android, Windows, macOS ve Linux kurulum dosyaları doğrudan bu siteden dağıtılır ve bir uygulama mağazasına bağlı değildir.

## Devamı için

- [İletişim sayfası: istemci indirme kartları ve üç grup](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-06)
- [Hiddify: kodu tarayarak içe aktarma](https://www.leotun.com/tr/singbox?utm_source=github&utm_content=client-06)
- [Özel ağ (Tailscale): giriş adımları](https://www.leotun.com/tr/mesh?utm_source=github&utm_content=client-06)
- [Bize nasıl ulaşılır, bağlantıyı nasıl koparmazsınız](https://www.leotun.com/tr/guides/stay-in-touch?utm_source=github&utm_content=client-06)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/ios-app-store?utm_source=github&utm_content=client-06

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-06) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-06) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
