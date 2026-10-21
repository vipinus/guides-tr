# 08 · Gerçekten bağlı olduğunuzu ve hangi bölgeden çıktığınızı nasıl doğrularsınız

İstemcinin "Connected" (bağlı) göstermesi, ziyaret ettiğiniz sitelerin VPN'in adresini gördüğü anlamına gelmez. Kontrolün en kolay yolu bu sitenin üst çubuğunda: "Mevcut ağ" alanı **bu sitenin sizi şu an nasıl gördüğünü** gösterir; hangi ülkeden, hangi eyalet/il ve hangi ağdan çıktığınızı. Bu yazı bu alanın nasıl okunacağını, bağlanmadan önce ve sonra nasıl karşılaştırma yapılacağını, altı bağlantı yönteminin her birinde bağlı olup olmadığınızı nasıl anlayacağınızı, bölge listesindeki kırmızı, sarı ve yeşil ışıkların ne anlama geldiğini ve "bağlı ama hâlâ yerel görünüyor" durumunda kendinizin kontrol edebileceği birkaç şeyi anlatıyor.

## Üst çubuktaki "Mevcut ağ" ne gösterir

| Konum | İçerik |
|---|---|
| Başta | Çıkışın bulunduğu ülkenin bayrağı; ülke belirlenemezse yerine bir Wi‑Fi simgesi |
| Ortada | Eyalet/il adı, arayüz dilinde gösterilir (ABD, Kanada, Avustralya vb. CA, ON, NSW gibi yaygın kısaltmalarla); Hong Kong, Makao ve Singapur doğrudan bölge adıyla gösterilir |
| Sonda | Ağ adı: Çin'in üç büyük operatörü, eğitim ağı vb. Çince arayüzde 电信 (China Telecom), 移动 (China Mobile), 联通 (China Unicom) ve 教育网 (eğitim ağı) gibi kısa adlarla gösterilir; geri kalanlar İngilizce marka adlarıyla (ör. Comcast, Bell) görünür |

- **Eyalet/il bulunamazsa yalnızca "bayrak · ağ adı" gösterilir.** Boşluğu doldurmak için ülke adı kullanılmaz; ülkeyi bayrak söyler.
- Bilgisayarda fareyi bu alanın üzerine getirdiğinizde tam kuruluş adı, eyalet/il, ülke kodu ve **çıkış IP'si** açılır. Bu IP yalnızca size gösterilir ve destekle iletişime geçerken elinizde olması en işe yarayan bilgidir.
- Windows'taki Chrome / Edge'de bayrak yazı tipi yoktur; bayrak iki harf olarak görünür (ör. JP, US). Anlamı aynıdır.
- Bilgisayarda üst çubukta ancak giriş yaptıktan sonra görünür; telefonda giriş yapmadan da gösterilir.

## Bağlanmadan önce ve sonra karşılaştırın, bir bakışta anlayın

1. **VPN kapalıyken** bu siteyi açıp bakın: Ev genişbandınızın ya da mobil verinizin operatörü olmalı, bayrak da bulunduğunuz ülkeyi göstermeli.
2. **VPN'e bağlanıp** tarayıcıya dönün: Bayrak seçtiğiniz bölgeye döner; ağ adı da genellikle ev operatörünüz yerine bir veri merkezinin ya da bulut sağlayıcısının adına dönüşür.
3. İkisi aynıysa bu tarayıcı bu siteyi ziyaret ederken VPN'den geçmiyordur. Aşağıdaki "Bağlı ama hâlâ yerel görünüyor" bölümüne bakın.

**Sayfayı sürekli yenilemenize gerek yok.** Bu alan, tarayıcı penceresine döndüğünüzde kendiliğinden yeniden kontrol eder, ağ değişikliği algılayınca birkaç saniye içinde birkaç kez daha bakar ve sayfa açıkken de on ila yirmi saniyede bir güncellenir. Bağlandıktan hemen sonra hâlâ eski değeri görüyorsanız on ila yirmi saniye bekleyin ya da pencere değiştirin; yine değişmediyse elle yenileyin.

**Çin'deyken bir "Çin giriş noktası" seçtiyseniz** üst çubuğun bir yabancı ülke göstermesi normaldir: Çin giriş noktaları bölünmüş yönlendirme kullanır; Çin siteleri Çin'in içinden çıkar, yabancı siteler ise yurt dışı tarafından çıkar. Bu site yurt dışında olduğu için doğal olarak yurt dışı uç gösterilir.

## Her bağlantı yönteminde bağlı olup olmadığınızı nasıl anlarsınız

| Yöntem | İstemcide neye bakılır | Bu sitenin üst çubuğu değişir mi |
|---|---|---|
| Cisco (AnyConnect) | İstemci "Connected" (bağlı) gösterir | Evet. Cisco bağlanınca tüm trafik VPN'den geçer |
| Hiddify | İstemci bağlı gösterir | Global modda değişir; "auto routing" (otomatik yönlendirme) altında listeye bağlıdır |
| OpenVPN | İstemci bağlı gösterir | Evet. Varsayılan olarak tüm trafik VPN'den geçer |
| Özel ağ (Tailscale) | İstemci çevrim içidir **ve** Exit Node (çıkış noktası) olarak bir bölge seçilidir | Yalnızca bir çıkış seçiliyken değişir; None (yok) seçiliyken cihazlar yalnızca birbirine ulaşır, trafik VPN'den geçmez |
| Web Proxy | "Bağlı" diye bir durum yoktur; eklenti simgesinde hangi bölge modunun seçili olduğuna bakın | Yalnızca eklentinin kurulu olduğu tarayıcı değişir; "auto switch" (otomatik geçiş) kuralları bu sitenin doğrudan bağlanmasına yol açabilir |
| Router | Yönetim sayfasında hesap durumu normaldir ve bitiş tarihi görünür | Bu router'ın Wi‑Fi'sine bağlı bir cihazdan bakın; bölünmüş yönlendirme modunda listeye bağlıdır |

Bölünmüş yönlendirme, listedeki sitelerin VPN'den geçmesi, geri kalan her şeyin doğrudan bağlanması demektir. Bölünmüş yönlendirme açıkken üst çubuk yerel gösteriyorsa bu, bağlı olmadığınız anlamına gelmeyebilir: **Geçici olarak "global"e (tam) geçip yeniden bakın.** Değişiyorsa VPN çalışıyordur, bu site yalnızca listede değildir.

## Bölge listesindeki kırmızı, sarı ve yeşil ışıklar

Cisco, Hiddify, Web Proxy ve OpenVPN sayfalarında her bölgenin bayrağının altında küçük bir ışık vardır; aynı ışık Özel ağ istemcisindeki çıkış adlarının önünde de görünür. Işık, o bölgedeki her sunucunun anlık ortalama bant genişliğine göre otomatik derecelendirilir ve yaklaşık dakikada bir güncellenir:

| Işık | Anlamı |
|---|---|
| Yeşil (sabit) | Boşta |
| Sarı (yanıp sönen) | Kullanımda |
| Kırmızı (yanıp sönen) | Yoğun |
| Işık yok | O an veri alınamadı; sunucunun çöktüğü anlamına gelmez |

Bilgisayarda fareyi ışığın üzerine getirerek bölgenin ortalama yükünü görebilirsiniz.

**Kırmızı ışık görünce ne yapmalı:**

- Kırmızı bozuk demek değildir; yalnızca o an çok kişi olduğu anlamına gelir. Zaten bağlıysanız ve hız yeterliyse dokunmayın.
- Yavaş geliyorsa yeşil ışıklı bir bölgeye geçin. Cisco'da yeni adresi kopyalamak için web sayfasında başka bir bayrağa tıklayın; Hiddify'da başka bir bölgenin yapılandırmasını içe aktarın; Özel ağda Exit Node'dan değiştirin; Web Proxy'de eklenti simgesinden başka bir bölgeye tıklayın.
- Bir bölgenin arkasında birkaç makine vardır ve bağlanırken en az yoğun olanı otomatik seçilir. Makineyi kendiniz seçmenize gerek yok.
- Akşam 20:00–23:00 yoğun saattir. Bu aralıkta yeşil ışıklı bir bölge seçin ya da bağlantı yöntemini değiştirin; hâlâ yavaşsa genellikle neden yerel genişbanttır (site ya da apartman genelinde paylaşılan toplu genişbant ya da birbirine uymayan operatör ve bölge). Operatöre göre bölge seçimi için Devamı için bölümüne bakın.

## Bağlı ama hâlâ yerel görünüyor

Sıklık sırasına göre:

1. **Yönlendirme kuralları bu siteyi doğrudan bağlıyor.** Hiddify'ın otomatik yönlendirmesi, Web Proxy eklentisinin "auto switch"i ve router'ın bölünmüş yönlendirme modu bu siteyi VPN dışında bırakabilir. Doğrulamak için geçici olarak global'e geçin; Web Proxy kullananlar bu siteyi kurallara da ekleyebilir.
2. **Web Proxy yalnızca o tek tarayıcıyı kapsar.** Başka bir tarayıcıdan ya da telefon uygulamasından bakarsanız doğal olarak yine yerel görünür.
3. **Özel ağda çıkış seçilmemiş.** Çevrim içi olmak ≠ VPN'den geçmek; Exit Node None iken cihazlar yalnızca birbirine ulaşabilir.
4. **Yanlış cihazdan bakıyorsunuz.** Router seçeneğinde, modemin Wi‑Fi'sine bağlı ya da mobil veri kullanan bir telefondan değil, o router'ın Wi‑Fi'sine bağlı bir cihazdan bakmanız gerekir.
5. **Aynı anda başka bir VPN ya da mesh ağ aracı açık.** Şirket VPN'i ya da başka bir sağlayıcının hızlandırıcısı yönlendirmeler için çakışır. Yalnızca birini açık tutun.
6. **Henüz yenilenmedi.** On ila yirmi saniye bekleyin, pencere değiştirin ya da bir kez elle yenileyin.

## Üst çubuk IP'yi kontrol eder; IPv6 ve DNS'i ayrıca kontrol edin

Üst çubuk, bu sitenin aldığı bağlantının IPv4 adresine bakar. Doğru şeyi gösteriyorsa bu yalnızca bu tarayıcının bu siteyi ziyaret ederken VPN'den geçtiği anlamına gelir:

- **IPv6 ve DNS buradan görülemez.** Tarayıcı bu siteyi IPv6 üzerinden ziyaret ettiğinde alan hiç gösterilmez; yanlış bir ağı doğruymuş gibi göstermez. Bir video sitesi hâlâ telif kısıtlaması uyarısı veriyorsa büyük olasılıkla IPv6 ya da DNS VPN'in yanından geçiyordur; bkz. [03 · Sızıntı IPv6 ve DNS'ten](03-ipv6-and-dns-leak.md).
- **Uygulamalar bölge kontrollerini önbellekte tutar.** Üst çubuk her seferinde yeniden sorgulanır ve önbellekten etkilenmez; ama video ve müzik uygulamaları önceki bölgeyi hatırlar. Tamamen kapatıp yeniden açın; bkz. [02 · Çin'e bağlandım ama hâlâ izleyemiyorum](02-still-blocked-after-connecting.md).

## SSS

**Üst çubuktaki "Mevcut ağ" alanı kayboldu mu?** Bilgisayarda önce giriş yapın. Giriş yaptıktan sonra da görünmüyorsa büyük olasılıkla bu bağlantı IPv6 üzerinden gitmiştir ya da o an sorgulanamıyordur; on ila yirmi saniye bekleyin ya da yenileyin. Yanlış bir şey göstermektense hiçbir şey göstermemeyi tercih eder.

**Aynı bölge, ama iki bağlantıda farklı IP?** Normaldir. Bir bölgenin arkasında birkaç makine vardır ve her bağlantı o an en az yoğun olanı seçer. Kurulmuş bir bağlantı yarı yolda başka yere taşınmaz.

**Gösterilen eyalet beklediğim değil mi?** Üst çubuk, çıkış IP'sinin bulunduğu eyaleti/ili gösterir ve yalnızca o düzeyde doğrudur. Bayrak tutuyorsa çıkış seçtiğiniz ülke ya da bölgededir.

**Destekle iletişime geçerken neyi bildirmeliyim?** Fareyi üst çubuktaki o alanın üzerine getirin ve açılan bilgiyi (çıkış IP'si dahil) bağlantı yöntemi, seçtiğiniz bölge ve sorunun yaşandığı saatle birlikte gönderin.

## Devamı için

- [Bağlanmıyor, yavaş, kopuyor: nasıl sorun giderilir](https://www.leotun.com/tr/guides/connect-issues?utm_source=github&utm_content=troubleshooting-08)
- [Çin'in içinden hangi bölge en hızlı](https://www.leotun.com/tr/guides/pick-region?utm_source=github&utm_content=troubleshooting-08)
- [Hangi bağlantı yöntemi hangi duruma uygun](https://www.leotun.com/tr/guides/choose-connection?utm_source=github&utm_content=troubleshooting-08)
- [Web Proxy nedir, ne zaman kullanılır](https://www.leotun.com/tr/guides/web-proxy?utm_source=github&utm_content=troubleshooting-08)
- [Router yazılımı neler yapabilir](https://www.leotun.com/tr/guides/router-firmware?utm_source=github&utm_content=troubleshooting-08)
- [Tencent Video yurt dışında telif kısıtlaması uyarısı verdiğinde ne yapmalı](https://www.leotun.com/tr/guides/overseas-video?utm_source=github&utm_content=troubleshooting-08)

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=troubleshooting-08) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-08) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
