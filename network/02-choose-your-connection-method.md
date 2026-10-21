# 02 · Hangi bağlantı yöntemi hangi duruma uygun

Bir LeoTun hesabında altı bağlantı yöntemi vardır: Özel ağ (Tailscale), Cisco (AnyConnect), OpenVPN, Web Proxy, Hiddify ve Router. Her yöntemin en uygun olduğu durumlar vardır; bu yazı yanıtları duruma göre veriyor: önce kullandığınız cihaza, sonra bağlı olduğunuz ağa, en son da ne yapmak istediğinize göre. Her durum için bir öneri, gerekçesi ve bir alternatif var. Tek bir şeyi aklınızda tutun: Tek hesapta altı yöntem var; ağınıza uyan biri mutlaka çıkar.

## Cihaza göre: internete neyle giriyorsunuz

- Tek telefon, iş seyahati ve gezi: Cisco ya da Hiddify. Cisco, resmî uygulamaya adresi girer girmez bağlanır ve en istikrarlısıdır; Hiddify QR kodu taranarak içe aktarılır ve paket kaybı yüksekken daha hızlıdır. Alternatif: Özel ağ.
- Kendi bilgisayarınız (Windows, Mac): Hiddify ya da Özel ağ. Hiddify hızlıdır ve yerleşik bir bölünmüş yönlendirme anahtarı vardır; Özel ağ tek bir girişten sonra çevrim içi kalır. Alternatif: Cisco.
- Şirketin verdiği, yönetici yetkisi olmayan bilgisayar: Web Proxy. Yalnızca bir tarayıcı eklentisi kurarsınız; yönetici yetkisi gerekmez ve şirketin ağ ayarlarına dokunmaz.
- iPhone, eski cihazlar: Cisco. Sistemin yerleşik VPN'iyle ya da resmî istemciyle bağlanır, yapılandırma içe aktarmak gerekmez ve uyumluluğu en iyisidir.
- NAS (Synology, QNAP), Linux sunucular: OpenVPN. Tek bir .ovpn dosyasını içe aktarın, açılışta otomatik bağlanır; bu cihazların çoğunda istemci yerleşik gelir.
- TV'ler, set üstü kutular, oyun konsolları, yaşlı bir yakının telefonu: Router. Wi‑Fi'ye bağlanan her şey hattan geçer, cihaza hiçbir şey kurmak gerekmez. Üç hesap planı da kullanabilir.
- Bütün bir ailenin ya da ofisin çok sayıda cihazı: Router; bir kez ayarlanır, hepsinde geçerli olur. Dışarıdan evdeki NAS'a da ulaşmak istiyorsanız Özel ağ ekleyin.

## Ağ ortamına göre: hangi ağdasınız

- UDP'yi kısıtlayan yurt ya da kampüs ağları, şirket ağları: Cisco. Bir HTTPS sitesi açmakla aynı şekilde TLS üzerinden çalışır ve kısıtlı ağlarda en istikrarlısıdır; Hiddify, Özel ağ ve OpenVPN UDP üzerinden çalışır, yavaşlar ya da kopar.
- Sık kopan genişbant, zayıf Wi‑Fi sinyali: Web Proxy. İstek bazında çalışır, sürekli açık bir bağlantısı yoktur; yani tasarımı gereği kopacak bir bağlantı da yoktur.
- Eski yerleşim sitelerindeki genişbant, mobil veri, yüksek paket kaybı: Hiddify. Protokolü paket kaybına dayanacak şekilde tasarlanmıştır ve bu tür ağlarda en iyi hızı verir.
- Bilgisayar zaten bir şirket VPN'ine bağlı: Web Proxy. Tüm cihazı kapsayan iki VPN birlikte çalışınca ağ ayarları için çakışır; Web Proxy yalnızca tarayıcıyla ilgilenir, bu yüzden birbirlerine karışmazlar.
- China Mobile, Great Wall ve diğer genişbantlar ya da sürekli istikrarsız sınır ötesi bağlantılar: Herhangi bir yöntem, Çin bölgesindeki bir giriş noktasıyla. Bu ağlarda genellikle en kararlı seçenektir.

## Amaca göre: ne yapmak istiyorsunuz

- Yurt dışındasınız ve Çin videoları izlemek istiyorsunuz: Çin bölgesi seçili herhangi bir tüm cihaz yöntemi (Cisco, Hiddify, Özel ağ, OpenVPN, Router); evdeki TV için Router kullanın. Video için Web Proxy kullanmayın: Cihazın kendi ağ kanalına ulaşamaz, bu yüzden video sitesi sizi yine yurt dışında görebilir.
- Oyunlar, sesli ve görüntülü görüşmeler: Hiddify, Özel ağ ya da Router; gecikmesi en düşük bölgeyi seçin. Web Proxy yalnızca tarayıcıyla ilgilenir; oyunlar ve görüşme uygulamaları ondan geçmez.
- Ofis işi ve bilgi arama, yalnızca tarayıcı: En az uğraştıran Web Proxy'dir. Şirketin iç sistemlerine bağlanmanız gerekiyorsa önce şirket VPN'inin bizimkiyle birlikte çalışıp çalışamayacağını doğrulayın; çalışamıyorsa Web Proxy kullanın.
- Sunucular, betikler, komut satırı: OpenVPN; masaüstü Linux'ta Özel ağ ya da Hiddify de kullanabilirsiniz.
- Dışarıdan evdeki NAS'a ya da kameralara ulaşmak: Özel ağ. Aynı hesaptaki cihazlar birbirine ulaşabilir, router'da port açmaya gerek yoktur.

## Altı yönteme hızlı bakış: en uygun olduğu / uygun olmadığı

- Özel ağ (Tailscale) — en uygun: çok cihaz, bir kez giriş yapıp unutmak, dışarıdan evdeki cihazlara ulaşmak. Uygun değil: UDP'yi kısıtlayan ağlar (yalnızca Tailscale'in yavaş aktarma sunucularına (relay) dayanabilir), başka bir VPN'le birlikte çalışmak.
- Cisco AnyConnect — en uygun: kısıtlı ağlar, şirket bilgisayarları, iPhone, eski cihazlar; uyumluluğu en iyisi. Uygun değil: Çin'de olup tüm trafiğin hattan geçmesini istemeyenler (ayrı bir bölünmüş yönlendirme betiği çalıştırmak gerekir).
- OpenVPN — en uygun: NAS, Linux sunucular, OpenWrt router'lar; tek dosya içe aktarılır, açılışta otomatik bağlanır. Uygun değil: telefon ve bilgisayarda günlük kullanım (Cisco ve Hiddify kadar pratik değil); UDP'yi kısıtlayan ağlar.
- Web Proxy — en uygun: yönetici yetkisi yok, zaten şirket VPN'ine bağlı, sık kopan genişbant. Uygun değil: video uygulamaları, oyunlar, görüşmeler; yalnızca tarayıcıyla ilgilenir.
- Hiddify — en uygun: hız isteyenler, paket kaybı yüksek ağlar; QR kodu taranarak içe aktarılır, beş platformda aynı uygulama, yerleşik bölünmüş yönlendirme. Uygun değil: UDP'yi kısıtlayan ağlar.
- Router — en uygun: bütün bir aile, bir ofis, istemci kurulamayan cihazlar; yazılımında bölünmüş yönlendirme yerleşiktir ve otomatik güncellenir. Uygun değil: tek cihazı olan ve sık dışarıda olanlar (dışarı çıkınca yine istemci kurmanız gerekir).

## Genişbandınıza göre bölge seçimi

Aynı yöntem bölgeler arasında birkaç kat hız farkı gösterebilir; nedeni sunucuda değil, operatörünüzün o bölgeye giden dış hattındadır. Kuzeyde China Unicom: önce Japonya ve Kore'yi deneyin. Güneyde China Telecom: önce Güneydoğu Asya'yı (Singapur, Malezya, Tayland, Filipinler, Endonezya) ya da Avustralya'yı deneyin. Diğer genişbantlar (China Mobile, Great Wall vb.): önce Çin bölgesindeki giriş noktasını deneyin.

Bölge listesindeki kırmızı, sarı ve yeşil ışıklar her bölgenin anlık yükünü gösterir; birkaç Japonya girişi arasından yeşil ışıklı olanı seçin. Akşam 20:00–23:00 ülke genelinde yoğun saattir; bu aralıkta yeşil ışıklı bir bölge seçin ya da bağlantı yöntemini değiştirin. Hâlâ yavaşsa genellikle neden yerel genişbanttır (site ya da apartman genelinde paylaşılan toplu genişbant ya da birbirine uymayan operatör ve bölge).

## Bölünmüş yönlendirme: Çin içi doğrudan, yurt dışı hattan

Bölünmüş yönlendirmeye yalnızca Çin anakarasındaki kullanıcıların ihtiyacı vardır; yurt dışındaki kullanıcılar global modu kullanır, bölünmüş yönlendirmeyi açmak bazı siteleri aslında uzun yoldan gönderir. Hiddify'da istemcide "Auto split routing"e (otomatik bölünmüş yönlendirme) geçersiniz, Web Proxy'de eklentide "Split routing"e geçersiniz; router ağdaki her cihaz için bölünmüş yönlendirme yapar ve yazılımında bu varsayılan olarak açıktır; Cisco ve OpenVPN'de bağlanınca tüm trafik hattan geçer, "Cisco" bölümündeki bölünmüş yönlendirme betiği de kullanılabilir; Özel ağ tüm cihazı hattan geçirir.

Bölünmüş yönlendirmede bir site açılmıyorsa önce geçici olarak "Global"e (tam) geçip kontrol edin: Global'de açılıyorsa listede değildir; Global'de de açılmıyorsa sorun o sitenin kendisindedir.

## Çalışmadığında nasıl geçiş yapılır

1. Önce bölge değiştirin. Başka bir bölge bağlanıyorsa o sunucuya yalnızca geçici olarak ulaşılamıyordur.
2. Sonra ağ değiştirin. Genişbant çalışmıyorsa mobil veriye geçin, ya da tersi; farklı operatörlerdeki müdahale aynı anda olmaz.
3. Sonra yöntem değiştirin. UDP üzerinden çalışanlar (Hiddify, Özel ağ, OpenVPN) çalışmıyorsa TLS üzerinden çalışan Cisco'ya geçin; tüm cihaz yöntemleri sürekli kopuyorsa Web Proxy'ye geçin. Farklı protokollerin engellenmesi birbirinden bağımsızdır.
4. Hâlâ çalışmıyorsa sorun giderme rehberine bakın ya da destek grubunda sorun; bağlantı yöntemini, bölgeyi, hata mesajının tam metnini ve saati ekleyin.

## SSS

**Altı yöntemden hangisi en hızlı?** Paket kaybı yüksek ağlarda Hiddify en hızlısıdır; temiz ağlarda aralarında pek fark yoktur, darboğaz yöntem değil bölge ve saattir.

**Oyun ve sesli görüşme için hangisi?** Hiddify, Özel ağ ya da Router; gecikmesi en düşük bölgeyi seçin. Web Proxy yalnızca tarayıcıyla ilgilenir; oyunlar ve görüşme uygulamaları ondan geçmez.

**Altı yöntem aynı anda kullanılabilir mi?** Farklı cihazlarda evet; aynı hesaptaki tüm yöntemler aynı anda çevrim içi kotasını paylaşır (Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz). Aynı cihazda tüm cihazı kapsayan iki yöntemi aynı anda çalıştırmayın (örneğin Özel ağ ve Cisco); ağ ayarları için çakışırlar.

**Router ile istemci arasında seçim yapmak zorunda mıyım?** Hayır. Evde router'ı kullanın, dışarı çıkınca telefonunuzda istemciyi açın; her biri bir cihaz sayılır.

**Linux için hangisi?** Özel ağ, OpenVPN ve Hiddify'ın Linux istemcileri var; Linux'ta Cisco için kaynak açık OpenConnect kullanılır; Linux'ta OpenVPN ilk bağlantıda hesap ve parola girmenizi ister. Sunucular ve NAS için en az uğraştıran OpenVPN'dir.

## Devamı için

- [Diğer VPN'lerden farkımız](https://www.leotun.com/tr/guides/why-us?utm_source=github&utm_content=network-02)
- [Özel ağ (Tailscale) nedir](https://www.leotun.com/tr/guides/tailscale-mesh?utm_source=github&utm_content=network-02)
- [OpenVPN nasıl kullanılır, ne zaman seçilir](https://www.leotun.com/tr/guides/openvpn-setup?utm_source=github&utm_content=network-02)
- [Web Proxy nedir, ne zaman kullanılır](https://www.leotun.com/tr/guides/web-proxy?utm_source=github&utm_content=network-02)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/choose-connection?utm_source=github&utm_content=network-02

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=network-02) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=network-02) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
