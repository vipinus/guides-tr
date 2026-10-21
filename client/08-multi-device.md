# 08 · Çok cihazı tek seferde kurun, telefon değiştirince baştan başlamayın

Çok cihazı olanlar için en can sıkıcı kısım her birini tek tek ayarlamak, telefon değiştirince hepsini yeniden yapmak ve dışarıdayken her cihazda bağlan düğmesine basmaktır. Özel ağ bunların hepsini ortadan kaldırır: Her cihaz bu sitedeki hesabınızla bir kez giriş yapar ve sonra çevrim içi kalır; yeniden başlatma ya da Wi‑Fi değişikliğinden sonra hiçbir şey yapmanız gerekmez. Her cihaz kendi çıkış bölgesini seçer; dizüstü bilgisayar Japonya'yı, telefon Çin bölgesini birbirini etkilemeden kullanabilir. Aynı hesaptaki cihazlar birbirine ulaşabilir; evden uzaktaki bir dizüstü bilgisayar evdeki NAS'ın paylaşımlarını doğrudan açabilir. Yeni bir telefonun yalnızca giriş yapması yeterlidir. Bu yazı bir evin tüm cihazlarını nasıl ekleyeceğinizi, kotanın nasıl sayıldığını ve süre dolması ile cihaz değişikliğinin nasıl ele alınacağını anlatıyor.

## Her cihazda yalnızca bir kez yaptıklarınız

1. Tailscale istemcisini kurun (Android, Windows, macOS ve Linux için bu sitenin Özel ağ sayfasındaki indirme alanından; iPhone / iPad için App Store'dan, bu da Çin dışı bölgeye ait bir Apple kimliği gerektirir).
2. Resmî bir Tailscale hesabına giriş yaptıysanız önce çıkış yapın, sonra girişi bu sitenin kontrol sunucusuna yönlendirin (telefon: çıkış yapılmış ekranda "⋯" → Use custom server; bilgisayar: komutu sayfadan kopyalayın; macOS: Account Settings → Accounts → "Add Account…" yanındaki ok → Add Account Using Alternate Server).
3. Tarayıcıda bu sitedeki hesabınızla onaylayın. Bundan sonra cihaz özel ağdadır ve başka bir ilgi gerektirmez.
4. Bir çıkış seçin: Her cihaz kendi menüsünden, diğerlerinden bağımsız olarak seçer. Çıkış kullanmak istemiyorsanız None'ı (yok) seçin; yalnızca cihazdan cihaza erişim kalır.

## Aynı anda bağlı cihazlar nasıl sayılır

Bir hesap istediğiniz kadar cihaza kurulabilir; tek sınır aynı anda kaç cihazın çevrim içi olduğudur: Bireysel 2, Aile 4, Kurumsal 8. Bu kota Cisco, Hiddify ve diğer yöntemlerle ortaktır. Planınızın sınırını aştığınızda hesap türünü geçici olarak yükseltebilir (kalan süre fiyata göre eşdeğer değerde dönüştürülür), işiniz bitince geri dönebilirsiniz.

Bir router tek cihaz sayılır, arkasındaki cihazlar sayılmaz. Evde bir router ya da NAS, üstüne yanınızda taşıdığınız telefon ve dizüstü bilgisayar genellikle yeterlidir.

## Cihazlar birbirine ulaşabilir

- Aynı hesaptaki her cihazın bir özel ağ adresi vardır ve cihaz adıyla da ulaşılabilir; genel IP'ye ya da port yönlendirmeye gerek yoktur.
- Evden uzaktaki dizüstü bilgisayardan evdeki NAS'ın paylaşılan klasörünü açmak, telefondan evdeki kayıt cihazını izlemek ya da evdeki bilgisayara uzak masaüstüyle bağlanmak özel ağ adresleriyle doğrudan bağlanır.
- Bu sitenin yazılımını çalıştıran bir ev router'ı tüm yerel ağı özel ağa açabilir; böylece yazıcı ve TV gibi istemci çalıştıramayan cihazlara da dışarıdan ulaşılabilir.
- Diğer müşterilerin cihazları sizin özel ağınızda hiç yer almaz; mesele yalnızca onları göremiyor olmanız değildir.

## Süre dolması, cihaz değiştirme, kaldırma

- Hesabın süresi dolarsa: Tüm cihazlar birkaç dakika içinde çevrim dışı olur; yeniledikten sonra her birinde bir kez daha giriş yapın, çıkış ayarları korunur.
- Telefon değiştirme: Yeni telefonda yukarıdaki adımlarla giriş yapın; sınıra ulaşıldığını söylerse eski telefonda çıkış yapın ya da hesap türünü geçici olarak yükseltip işiniz bitince geri dönün.
- Bir cihazın özel ağda kalmasını istemiyorsanız: İstemcide çıkış yapın; bir cihazı zorla çevrim dışı bırakmak için destekle iletişime geçin.
- Aynı cihazda aynı anda başka bir VPN çalıştırmayın (şirketin Cisco istemcisi, başka mesh ağ yazılımları); DNS ve yönlendirmeler için birbirleriyle çakışırlar.

## SSS

**Her cihaz farklı bir çıkış bölgesi seçebilir mi?** Evet, her cihaz kendi çıkışını seçer. Dizüstü bilgisayar video için Japonya'yı, telefon internet bankacılığı için Çin bölgesini birbirini etkilemeden kullanabilir.

**Özel ağı sürekli açık bırakmak pili bitirir mi?** Çıkış seçili değilken neredeyse hiç trafik olmaz; yalnızca özel ağdaki cihazlarla iletişim kurarken kullanılır. Pil tüketimi sistem VPN'iyle kıyaslanabilir düzeydedir.

**Evdeki NAS'a nasıl kurarım?** Synology ve QNAP'ın Tailscale paketi var, Linux sistemlerde resmî kurulum betiği kullanılır; giriş yaparken aynı şekilde bu sitenin kontrol sunucusuna yönlendirin. Bu sitenin yazılımını çalıştıran router'a kurmaya gerek yok: Hesabınıza giriş yapın, özel ağa katılır.

**Neden her cihaza Cisco kurmuyoruz?** Kurabilirsiniz, ama Cisco'da her seferinde bağlan düğmesine basmanız, kopunca yeniden bağlanmanız ve çıkış değiştirmek için adresi değiştirmeniz gerekir; çok cihazla özel ağ çok daha az uğraştırır. UDP'yi kısıtlayan bir kampüs ağındaki cihaz istisnadır; onda Cisco kullanın.

## Devamı için

- [Özel ağ sayfası: indirme ve giriş adımları](https://www.leotun.com/tr/mesh?utm_source=github&utm_content=client-08)
- [Özel ağ (Tailscale) nedir](https://www.leotun.com/tr/guides/tailscale-mesh?utm_source=github&utm_content=client-08)
- [Çin'deki ev kameralarınızı ve NAS'ınızı yurt dışından izlemek](https://www.leotun.com/tr/guides/home-camera?utm_source=github&utm_content=client-08)
- [Router yazılımı neler yapabilir](https://www.leotun.com/tr/guides/router-firmware?utm_source=github&utm_content=client-08)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/multi-device?utm_source=github&utm_content=client-08

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-08) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-08) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
