# 03 · Web proxy: ZeroOmega eklentisini iki adımda kurun

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/web-proxy?utm_source=github&utm_content=client-03

Web Proxy yalnızca **bu tarayıcıyı** hattan geçirir; sistemdeki diğer programlara dokunmaz. Kurulacak bir istemci yok, yönetici yetkisi gerekmez ve "bağlı" diye bir durum da yoktur; yani tasarımı gereği kopacak bir bağlantı da yoktur. Şirket bilgisayarı, zaten bir şirket VPN'ine bağlı bir makine ya da yalnızca tek bir tarayıcının hattı kullanmasını istediğiniz durumlar için uygundur. Ne zaman bunu, ne zaman VPN kullanmanız gerektiği için [Ağ rehberi 02](../network/02-choose-your-connection-method.md) yazısına bakın.

## İki adım

1. **Eklentiyi kurun**: Chrome / Edge / Firefox'a ZeroOmega'yı (SwitchyOmega'nın devamı) kurun. [Sitedeki Web Proxy sayfasında](https://www.leotun.com/tr/httpproxy?utm_source=github&utm_content=client-03) her tarayıcı için kurulum bağlantısı var.
2. **İçe aktarın**: Siteye giriş yapın ve Web Proxy sayfasında istediğiniz bölgenin bayrağına tıklayın (ya da tüm bölgeleri tek seferde almak için "Copy import link for all regions" (tüm bölgeler için içe aktarma bağlantısını kopyala) düğmesine tıklayın); ayar bağlantısı panoya kopyalanır. Eklentide "Import/Export" (içe/dışa aktar) bölümünü açın, bağlantıyı "Restore from online" (çevrim içi kaynaktan geri yükle) alanına yapıştırın ve "Restore"a (geri yükle) tıklayın. Bölgeler, adresler ve şifreleme yöntemi tek seferde içe aktarılır; elle yazılacak bir şey yok.

Sonra eklenti simgesine tıklayıp bir bölge seçin ve tarayıcının gösterdiği giriş kutusuna bu sitedeki hesabınızı ve parolanızı girin. Bölge değiştirmek için simge menüsünden başka bir bölgeye tıklayın; yerel ağdan doğrudan bağlantıya dönmek için "Direct"e (doğrudan) geçin.

## Şu durumlarda tüm cihazı kapsayan bir yöntem kullanın

- Video ve müzik uygulamaları ve oynatıcılar: Çoğu tarayıcının proxy ayarını kullanmaz; sonuç "sayfalar açılıyor ama videolar oynamıyor" olur.
- Telefon uygulamaları, oyunlar ve masaüstü yazılımları. Dropbox gibi yazılımların proxy ayarları yalnızca şifresiz HTTP / SOCKS5 kabul eder; oysa pratikte bir proxy'nin şifreli olması gerekir, bu yüzden bu sitenin Web Proxy'si oraya girilemez. Bunun yerine bilgisayarın tamamını Hiddify'a devredin; bkz. [10](10-app-proxy.md).
- Tencent Video ya da iQIYI'yi yurt dışından izlemek: Video siteleri IPv6 ve DNS'i de kontrol eder, Web Proxy bunları kapsamaz; tüm cihazı kapsayan bir VPN kullanın.

## SSS

| Belirti | Neden |
|---|---|
| Giriş kutusu sürekli açılıyor | Hesabın süresi dolmuş ya da parola yanlış |
| Bazı siteler açılmıyor, diğerleri sorunsuz | Eklentideki "auto switch" (otomatik geçiş) kuralları onları doğrudan bağlantıya göndermiş; bir kez genel proxy moduyla deneyin |
| Çin'de yalnızca HTTPS siteleri açılıyor | Düz HTTP yolda değiştirilir, yalnızca şifreli bağlantılar geçer; bugün sitelerin neredeyse tamamı HTTPS |
| Yavaş | Bölge değiştirin; proxy ile VPN aynı sunucu grubunu kullanır |

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-03) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-03) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
