# 03 · Özel ağ (Tailscale) VPN'den nasıl farklıdır, ne zaman kullanılır

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/tailscale-mesh?utm_source=github&utm_content=network-03

Özel ağ bölümü Tailscale kullanır: WireGuard tabanlı bir ağ kurma aracı. Kontrol sunucusunu LeoTun kendisi işletir, siz de bu sitedeki hesabınızla giriş yaparsınız. AnyConnect ve OpenVPN gibi "bağlantı türü" VPN'lerle aynı şey değildir.

## Üç fark

| | Bağlantı türü VPN (AnyConnect / OpenVPN / Hiddify) | Özel ağ (Tailscale) |
|---|---|---|
| Bağlantı | Her seferinde bağlan düğmesine basarsınız, kopunca yeniden bağlanırsınız | Bir kez giriş yaparsınız ve çevrim içi kalır; ağ değiştirdiğinizde kendiliğinden toparlanır |
| Çıkış | Bağlandıktan sonra tüm trafik çıkıştan geçer | Çıkış isteğe bağlıdır: Hiçbiri seçili değilken genel internet trafiği yerelden çıkar ve yalnızca özel ağ içindeki cihazlar arasındaki trafik şifrelenir; ancak bir bölgenin çıkışını seçtiğinizde VPN'e eşdeğer olur |
| Cihazdan cihaza erişim | Yok | Aynı hesaptaki telefonlar, bilgisayarlar ve NAS'lar port yönlendirme ya da genel IP olmadan birbirine doğrudan ulaşabilir |

## Ne zaman kullanmalısınız

- Birden çok cihazınız var ve bir kez ayarlayıp hep çevrim içi kalmak istiyorsunuz.
- Evde dışarıdan ulaşmak istediğiniz bir NAS, bilgisayar ya da kamera var: İki tarafta da Özel ağa giriş yapın ve aynı yerel ağdaymış gibi cihaz adıyla doğrudan bağlanın.
- Uzun süre bağlı kalması gereken cihazlar: Oturum zaman aşımı yoktur.

## Ne zaman başka bir yöntem daha uygundur

- Yalnızca bir kez, geçici olarak kullanmak istiyorsunuz: Hiddify'ı QR kodla içe aktarmak ya da AnyConnect kurmak daha hızlıdır.
- Cihazda zaten bir şirket VPN'i ya da başka bir ağ yazılımı çalışıyor: İkisi DNS ve yönlendirme için çatışır; belirtisi Çin videosu izlerken telif uyarıları ve şirket intranetinin açılmamasıdır. Web Proxy gibi yalnızca tarayıcıyı etkileyen bir yöntem kullanın.
- UDP'yi kısıtlayan kampüs / şirket ağları: WireGuard UDP üzerinden çalışır ve yalnızca yavaş olan aracı sunuculara dayanabilir; AnyConnect'e geçin.

## Süre dolması ve cihaz sayısı

Bir cihazın giriş geçerliliği hesabın bitiş tarihini izler; süre dolduktan birkaç dakika sonra çevrim dışı olur, yeniledikten sonra yeniden giriş yapmanız yeterlidir. Aynı anda çevrim içi cihaz sayısı plana bağlıdır (Bireysel 2 cihaz, Aile 4 cihaz, Kurumsal 8 cihaz) ve kota diğer bağlantı yöntemleriyle ortaktır; aynı anda çevrim içi sayısı planın sınırını aştığında hesap türünü geçici olarak yükseltebilir (kalan süre fiyata göre eşdeğer değerde dönüştürülür), işiniz bitince geri dönebilirsiniz.

Kurulum ve giriş adımları için bkz. [İstemci rehberi 05](../client/05-tailscale-private-network.md).

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=network-03) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=network-03) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
