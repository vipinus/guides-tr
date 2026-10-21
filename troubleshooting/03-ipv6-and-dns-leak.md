# 03 · Bağlısınız ama video sitesi hâlâ telif uyarısı veriyor: sızıntı IPv6 ve DNS'ten

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/overseas-video?utm_source=github&utm_content=troubleshooting-03

[02 · Çin'e bağlandım ama hâlâ izleyemiyorum](02-still-blocked-after-connecting.md) yazısının 1. adımını geçtiniz — çıkış IP'si Çin anakarası görünüyor — ama site hâlâ "telif kısıtlamaları nedeniyle oynatılamıyor" diyor. On durumdan dokuzunda cihazda VPN'den geçmeyen bir yol daha vardır: **IPv6** ya da **DNS**. Video sitesi nerede olduğunuza gördüğü adrese bakarak karar verir; tek bir yol bile dışarı sızdığı sürece gördüğü hâlâ yurt dışıdır.

## Sızıntı neden olur

- Günümüz cihazlarının hem IPv4 hem IPv6 adresi vardır ve tarayıcılar IPv6'yı tercih eder. VPN yalnızca IPv4'ü devralıyorsa IPv6 istekleri doğrudan ev genişbant bağlantınızdan çıkar.
- Tarayıcının yerleşik "Güvenli DNS"i, Android'in "Özel DNS"i ya da çalışan başka bir mesh ağ aracı (Tailscale ve benzerleri) ad çözümlemeyi VPN'den önce devralır.

"Bağlandı" yalnızca tünelin kurulduğu anlamına gelir. Bütün trafiğin tünelden geçtiği anlamına gelmez.

## Beş adımda kontrol

1. **IPv6'yı kontrol edin.** Bağlandıktan sonra "test ipv6" diye arayıp bir test sayfası açın. IPv6 alanında bulunduğunuz ülkeye ait bir adres görünüyorsa → sorun burada, 2. adıma geçin. İki alan da Çin anakarasını gösteriyorsa ya da IPv6 kullanılamıyorsa → 3. adıma geçin.
2. **IPv6'yı kapatın ya da IPv6'yı engelleyen bir istemciye geçin.** Windows: Ağ bağdaştırıcısının özelliklerinde "İnternet Protokolü Sürüm 6 (TCP/IPv6)" işaretini kaldırın. macOS: Ağ ayarları → TCP/IP → IPv6'yı "Yalnızca bağlantı-yerel" (Link-local only) yapın. Telefon: Wi‑Fi'yi kapatıp bir kez mobil veriyle deneyin; ev genişbant bağlantısında genellikle IPv6 vardır, operatörün mobil verisinde çoğu zaman yoktur.
3. **DNS'i kontrol edin.** Chrome Ayarlar → Gizlilik ve güvenlik → "Güvenli DNS kullan"ı kapatın; Android'de "Özel DNS"i kapatın; diğer VPN'lerden, mesh ağ araçlarından ve proxy eklentilerinden çıkın.
4. **Uygulamayı tamamen kapatıp yeniden açın; web sürümünde site verilerini temizleyin.** Platformlar bir önceki bölge kontrolünü önbellekte tutar.
5. **Başka bir giriş noktasına geçip yeniden deneyin.** Belirli bir çıkışın adresi platform tarafından yeni işaretlenmiş olabilir.

## LeoTun bunu nasıl ele alıyor

Eylül 2026'dan beri LeoTun'un üç bağlantı yöntemi de (Hiddify, Cisco AnyConnect, OpenVPN) IPv6'yı tünelin içinde doğrudan reddediyor ve ad çözümlemeyi tünelin içinde yapmaya zorlayan DNS ayarlarını gönderiyor — cihazınızda hiçbir ayarı değiştirmeniz gerekmez. **Eylül'den önce içe aktarılan Hiddify yapılandırmalarında bu kural yok. Onları silin ve QR kodunu tarayarak yeniden içe aktarın.**

Router seçeneğinde ise sızıntı baştan olmaz: Bütün yerel ağ router üzerinden çıkar, bu yüzden cihazların IPv6 ve DNS trafiği dışarıya hiç ulaşmaz.

## Uyarının yine de çıktığı durumlar

| Durum | Belirti | Çözüm |
|---|---|---|
| Çıkış Çin anakarası değil | IP sorgusu Hong Kong / Tayvan / Japonya gösteriyor | Bir Çin giriş noktasına geçin; Hong Kong ve Tayvan adresleri de Tencent ve iQIYI için yurt dışı sayılır |
| Özel yönlendirme kuralları video alan adlarını "direct" (doğrudan) yapmış | Web sayfaları açılıyor ama videolar oynamıyor | Çin alan adlarını düğümden geçecek şekilde değiştirin; yurt dışındaki kullanıcılar "Çin için doğrudan" seçeneğini açmamalı |
| Web Proxy kullanıyorsunuz | Tarayıcıda çalışıyor, uygulamalarda çalışmıyor | Video izlemek için cihazın tamamını kapsayan bir tünel gerekir; Web Proxy yalnızca tarayıcıyı kapsar |

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=troubleshooting-03) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=troubleshooting-03) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerlidir
