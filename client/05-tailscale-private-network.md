# 05 · Özel ağ (Tailscale): kurulum, bu sitenin kontrol sunucusuna giriş, çıkış noktası seçimi

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/tailscale-mesh?utm_source=github&utm_content=client-05

Özel ağ bölümü Tailscale'i (WireGuard üzerine kurulu bir ağ aracı) kullanır. LeoTun kendi kontrol sunucusunu işletir ve **bu sitedeki hesabınızla** giriş yaparsınız; bunun resmî bir Tailscale hesabıyla ilgisi yoktur. Bir kez giriş yapın, çevrim içi kalırsınız; çıkış bölgesini menüden istediğiniz an değiştirebilirsiniz. VPN'den farkı ve kime uygun olduğu için [Ağ rehberi 03](../network/03-private-network-vs-vpn.md) yazısına bakın.

## Kurulum

| Platform | Nereden alınır |
|---|---|
| Windows / macOS / Linux / Android | [Sitedeki Özel ağ sayfasının](https://www.leotun.com/tr/mesh?utm_source=github&utm_content=client-05) indirme alanı (doğrudan bu siteden sunulur, resmî siteye gitmeye gerek yok) |
| iPhone / iPad | App Store; Çin dışı bölgeye ait bir Apple kimliği gerekir (bkz. [İstemci 06](06-ios-app-store.md)) |

## Giriş

1. **Önce resmî hesaptan çıkış yapın** (daha önce giriş yaptıysanız): Telefonda profil resminize dokunun → Log Out (çıkış yap); bilgisayarda `tailscale logout` komutunu çalıştırın. Tamamen çıkış yapmadıkça bir sonraki adımda gereken seçenek görünmez.
2. **Girişi bu siteye yönlendirin**:
   - Telefon: Çıkış yapılmış ekranda sağ üstteki "⋯" simgesine dokunun → Use custom server (bazı sürümlerde Use an alternate server; özel sunucu kullan), sitedeki Özel ağ sayfasında verilen adresi girin ve Log in'e (giriş yap) dokunun.
   - Windows / Linux: Sitedeki sayfadan `tailscale up --login-server=…` komutunu kopyalayıp PowerShell'de / bir terminalde çalıştırın.
   - macOS: **Log in'e tıklamayın.** Tailscale penceresinde hesap satırındaki oka tıklayın → Account Settings… → Accounts → "Add Account…" yanındaki küçük ok → Add Account Using Alternate Server (alternatif sunucuyla hesap ekle); adresi yapıştırıp Add Account…'a tıklayın.
3. Tarayıcı bu sitenin giriş sayfasını otomatik olarak açar; bu sitedeki hesabınızla onaylayın. İstemciye döndüğünüzde zaten çevrim içidir.

## Çıkış noktası seçimi

- Telefon: menü → Exit Node (çıkış noktası), bir bölge seçin; hemen devreye girer.
- Bilgisayar: sistem tepsisi / menü çubuğu simgesi → Exit Node alt menüsü; ya da `tailscale set --exit-node=<region-name>` (`tailscale exit-node list` kullanılabilecekleri gösterir).
- Çıkış kullanmak istemiyorsanız None'ı (yok) seçin (komut satırında eşittir işaretinden sonrasını boş bırakın). Aynı anda yalnızca bir çıkış kullanılabilir.

## Süre dolması ve cihaz sayısı

- Bir cihazın giriş geçerliliği hesabın bitiş tarihine bağlıdır ve süre dolduktan birkaç dakika sonra çevrim dışı olur; yeniledikten sonra bir kez daha giriş yapmanız yeterlidir. Yeniden kurulum gerekmez.
- Aynı anda çevrim içi cihaz sayısı planınıza bağlıdır (Bireysel 2, Aile 4, Kurumsal 8) ve kota diğer bağlantı yöntemleriyle ortaktır; planınızın sınırını aştığınızda hesap türünü geçici olarak yükseltebilir (kalan süre fiyata göre eşdeğer değerde dönüştürülür), işiniz bitince geri dönebilirsiniz.

## Başka bir yöntemin daha uygun olduğu iki durum

- Aynı cihazda başka bir VPN çalışıyorsa (şirketin AnyConnect'i, başka mesh ağ yazılımları): DNS ve yönlendirmeler için çakışırlar. Çin videosu izlerken çıkan telif uyarılarının ve açılmayan şirket intranetlerinin nedeni budur.
- UDP'yi kısıtlayan bir kampüs / şirket ağında: WireGuard UDP üzerinden çalışır, bu yüzden yalnızca Tailscale'in aktarma sunucularından (relay) geçebilir ve bu çok yavaştır; AnyConnect'e geçin.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-05) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-05) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
