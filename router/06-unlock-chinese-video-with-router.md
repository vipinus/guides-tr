# 06 · Router ile Çin video sitelerinin engelini yurt dışından kaldırmak

## Neden her cihaza istemci kurmak yerine router

- TV'lere, TV kutularına, projektörlere ve oyun konsollarına istemci kurulamaz; tek yol router'dır.
- Evde çok kişi varsa herkesin her cihazını tek tek ayarlamak gerçekçi değildir; router'ı bir kez ayarlayın, cihaz Wi-Fi'ye bağlanır bağlanmaz devreye girer.
- Bölünmüş yönlendirme router'da yapılır; yerel siteler ve evdeki cihazlar doğrudan bağlanmaya devam eder, yalnızca Çin video alan adları Çin'e erişim hattından geçer ve hız etkilenmez.

## Neye ihtiyacınız var

| Ne | Notlar |
|---|---|
| Desteklenen bir router | Yazılımı yüklü olan kutudan çıktığı gibi çalışır; kendiniz yükleyecekseniz bkz. [Yazılım nasıl yüklenir](02-flash-firmware-yourself.md) |
| Bir hesap | Bireysel, Aile ve Kurumsal hesapların hepsi router özelliğini destekler. Kaydolduktan sonra tüm süreci doğrulamak için önce ücretsiz denemeyi alın: Yeni hesap Bireysel plandadır ve 4 saatlik deneme verilir |
| Üstte bir ağ | Evde zaten olan modem ya da router; yeni router onun arkasına bağlanır |

## Beş adımda tamam

1. Yeni router'ın WAN portunu üstteki ağa bağlayın, güç kablosunu takın ve bir dakika bekleyin.
2. Telefonunuzu yeni router'ın Wi-Fi'sine bağlayın, `http://192.168.11.1` yönetim adresini açın ve hesabınıza giriş yapın.
3. Mod olarak **Split routing**'i (bölünmüş yönlendirme) seçin. Çin video alan adları listededir ve otomatik olarak Çin'e erişim hattından geçer.
4. TV'yi ve TV kutusunu bu Wi-Fi'ye geçirin ya da kabloyla yeni router'ın bir LAN portuna bağlayın.
5. iQIYI, Tencent Video ya da Yangshipin'i (CCTV) açın; normal oynatıyorsa işlem tamamdır.

## Liste herkese açık

Bölünmüş yönlendirme listesindeki video alan adları herkese açık bir depoda tutulur: <https://github.com/vipinus/openwrt-2026-video-domains>. Bir platform oynatmıyorsa alan adının listede olup olmadığına bakabilir, yoksa ekleme önerisi gönderebilirsiniz.

## Görüntü kalitesi ve bant genişliği

1080p için istikrarlı 5 Mbps, 4K için 25 Mbps ya da daha fazlası gerekir. Akşam yoğun saatlerinde görüntü takılıyorsa yeşil ışıklı bir bölge seçin; yine takılıyorsa neden genellikle yerel genişbanttır. Giriş bölgesi olarak size yakın ve Çin anakarasına iyi güzergâhı olan birini seçin; birkaçını deneyin ve oynatmanın takılıp takılmadığına göre karar verin.

## SSS

- **Telefonda oynuyor ama TV'de oynamıyor**: TV hâlâ eski Wi-Fi'ye bağlı ya da TV'deki uygulama uluslararası sürüm.
- **Bazı platformlar oynuyor, bazıları oynamıyor**: O platformun alan adı bölünmüş yönlendirme listesinde yok. Doğrulamak için geçici olarak "Global"e (tam) geçin, sonra alan adını liste deposuna gönderin.
- **Eski bir router'da tüm evin interneti yavaşlıyor**: İşlemci şifreli trafiğe yetişemiyor; daha güçlü bir modele geçin, bkz. [Yazılımı yüklü router ile ilk adımlar](01-plug-and-play-router.md).

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-06) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-06) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
