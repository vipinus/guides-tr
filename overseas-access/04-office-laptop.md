# 04 · Şirket bilgisayarı kullanmak: yönetici yetkisi yok, şirket VPN'i zaten açık

Şirket bilgisayarının üç kısıtı vardır: onaylanmamış yazılım kuramazsınız, yönetici yetkiniz yoktur ve çoğu zaman şirket VPN'ine zaten bağlıdır. Burada tüm cihazı kapsayan bir VPN ya kurulamaz ya da şirket VPN'iyle çatışır. Doğru araç Web Proxy'dir: Yalnızca bu tarayıcının isteklerini hattan geçiren bir tarayıcı eklentisi; şirket intraneti, e-posta istemcisi ve şirket VPN'i olduğu gibi kalır, yönetici yetkisi de gerekmez. Bu yazı nasıl kurulacağını, neler yapabildiğini, nelerden kaçınmanız gerektiğini ve şirketin BT politikasıyla nasıl uyum içinde kalacağınızı anlatıyor.

## Neden Web Proxy

- Kurulacak istemci yok: Yalnızca bir tarayıcı eklentisidir; çoğu şirket yazılıma değil ama eklentilere izin verir.
- Yönetici yetkisi gerekmez: Eklenti kullanıcı alanında çalışır, sistemin ağ ayarlarını değiştirmez.
- Şirket VPN'iyle bir arada çalışır: Şirket VPN'i sistem yönlendirmelerini devralır, Web Proxy ise yalnızca tarayıcı katmanında durur; ikisi birbirine karışmaz, şirket intraneti sayfaları şirket VPN'inden geçmeye devam eder.
- Tasarımı gereği kopacak bağlantı yok: Proxy her istek için ayrı çalışır, sürekli açık bir bağlantı yoktur; şirket ağındaki dalgalanmayı da hissetmezsiniz.

## İki adımda kurulum

1. Tarayıcıya ZeroOmega eklentisini (SwitchyOmega'nın devamı) kurun; bu sitenin Web Proxy sayfasında her tarayıcı için kurulum bağlantısı var.
2. Bu siteye giriş yapın ve Web Proxy sayfasında eklenti geri yükleme bağlantısını kopyala düğmesine tıklayın, ardından bağlantıyı eklentide "Import/Export" (içe/dışa aktar) → "Restore from online" (çevrim içi kaynaktan geri yükle) alanına yapıştırın. Bölgeler ve adresler tek seferde içe aktarılır; sonra eklenti simgesine tıklayıp bir bölge seçin ve tarayıcının gösterdiği giriş kutusuna bu sitedeki hesabınızı ve parolanızı girin.
3. Proxy'ye özel ayrı bir tarayıcı profili (ya da başka bir tarayıcı) kullanmanızı, iş tarayıcısını ise yerelde tutmanızı öneririz; böylece ikisi birbirine karışmaz.

## Neye uygun, hangi durumlar başka yöntem ister

- Uygun: Bilgi aramak; Google, GitHub, Stack Overflow, yurt dışı dokümantasyon siteleri, ChatGPT'nin web sürümü ve web tabanlı e-posta açmak.
- Başka yöntem kullanın: Video uygulamaları, masaüstü yazılımları ve komut satırı araçları varsayılan olarak tarayıcının proxy ayarlarını kullanmaz (komut satırı için proxy adresini http_proxy ortam değişkenine yazabilirsiniz; Linux yazısına bakın).
- Başka yöntem kullanın: Çin video sitelerini izlemek (yurt dışındaki kullanıcılar için) — video siteleri IPv6 ve DNS'i de kontrol eder, Web Proxy bunları kapsamaz; bu durum tüm cihazı kapsayan bir VPN gerektirir.

## BT politikasıyla uyum

Şirket bilgisayarındaki her şey şirket tarafından denetlenebilir, eklentiler de istisna değildir. Önce şirketin kabul edilebilir kullanım politikasını okuyun: Çoğu şirketin yasakladığı, onaylanmamış yazılım ve güvenlik politikasını atlatmaktır; dış sitelere erişen bir tarayıcı eklentisi genellikle gri bir alandadır. Emin değilseniz BT ekibine sorun.

Şirket politikasını aşmak için şirket bilgisayarına tüm cihazı kapsayan bir VPN (Cisco, Özel ağ, Hiddify) kurmayın: Bunlar sistem yönlendirmelerini değiştirir, bu da uç nokta yönetim yazılımında alarmları tetikler ve şirket intraneti trafiğini de dışarı taşır. Web Proxy yalnızca tek bir tarayıcıyı etkiler ve en düşük riski taşır.

İş hesaplarını ve kişisel hesapları ayrı tutun: Proxy kullanan tarayıcıda şirket hesaplarına, şirket tarayıcısında kişisel hesaplara giriş yapmayın.

## SSS

**Şirket eklenti kurmayı yasaklıyorsa ne olacak?** O zaman kendi telefonunuzu ya da kişisel bilgisayarınızı kullanın. Kısıtlamaları aşmak için kaynağı belirsiz taşınabilir yazılımlar kullanmayın.

**Eklenti şirket intraneti trafiğimi görür mü?** Hayır. Bölünmüş yönlendirme kurallarında şirket intraneti alan adları doğrudan bağlanır, proxy'den geçmez; global modda yalnızca proxy sunucusuna gidip geri döner ve proxy'nin gördüğü içerik değil, alan adıdır. Güvenli olmak için proxy'ye kendi tarayıcı profilini verin.

**Şirket VPN'i açıkken proxy çalışır mı?** Evet, ikisi çakışmaz. Çok az sayıda şirket VPN'i tüm trafiği şirket çıkışından geçmeye zorlar ve proxy ayarlarını devre dışı bırakır; bu durumda eklenti bağlanamadığını bildirir ve tek seçenek şirket VPN'ini kapatmaktır.

**Şirketin Mac'inde de aynı mı?** Aynı; Chrome, Edge ve Firefox eklentilerinin hepsinin Mac sürümü var. Safari'de bu eklenti yok, başka bir tarayıcı kullanın.

## Devamı için

- [Web Proxy kurulum sayfası: eklenti kurulumu ve geri yükleme bağlantısı](https://www.leotun.com/tr/httpproxy?utm_source=github&utm_content=overseas-access-04)
- [Web Proxy nedir, ne zaman kullanılır](https://www.leotun.com/tr/guides/web-proxy?utm_source=github&utm_content=overseas-access-04)
- [Bir Linux sunucuyu ve komut satırı araçlarını hattan nasıl geçirirsiniz](https://www.leotun.com/tr/guides/linux-server?utm_source=github&utm_content=overseas-access-04)
- [Hangi bağlantı yöntemi hangi duruma uygun](https://www.leotun.com/tr/guides/choose-connection?utm_source=github&utm_content=overseas-access-04)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/office-laptop?utm_source=github&utm_content=overseas-access-04

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=overseas-access-04) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=overseas-access-04) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
