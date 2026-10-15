# 01 · Hangi hizmetler yurt dışı IP'si ister ve hat nasıl çalışır

Ölçüt, yurt dışından Çin'e erişimin tam tersidir: Hizmet, kaynak IP'nizin Çin anakarasında olduğunu gördüğünde ya da sunucularına hiç ulaşamadığınızda açılmaz, kısıtlı çalışır veya aşırı yavaşlar. Aşağıdaki tablo kullanım amacına göre düzenlenmiştir.

| Kategori | Örnekler | Hat olmadan ne olur | IP dışında ne gerekir |
|---|---|---|---|
| İş | Google Workspace, Slack, Zoom, Teams, Notion | Açılmaz ya da sürekli kopar | Şirket hesabı |
| Yazılım geliştirme | GitHub, npm, Docker Hub, aynalar dışındaki PyPI kaynakları, Stack Overflow | Zaman aşımına uğrayacak kadar yavaş | Hiçbir şey |
| Yapay zekâ | ChatGPT, Claude, Gemini | Açılmaz | Hesabın kayıtlı olduğu ülke, telefon numarası |
| Akademik araştırma | Google Scholar, makale veri tabanları, üniversite e-postası | Açılmaz ya da aşırı yavaş | Üniversite hesabı |
| Oyun | Steam'in yurt dışı bölgeleri, PSN, Switch eShop, yurt dışı sunucular | Mağaza açılmaz, gecikme yüksek | O bölgenin sunucularına ait bir hesap |
| Video ve müzik | YouTube, Netflix, Disney+, Spotify | Açılmaz | Ücretli hesap; hesabın bölgesi IP ile uyuşmalı |
| Sosyal medya | X, Instagram, Telegram, Discord, WhatsApp | Açılmaz | Telefon numarası |

## Önemli bir ayrım

**"Yurt dışı IP'si gerekmesi" ile "yurt dışı hesabı gerekmesi" iki ayrı şeydir.** GitHub ve YouTube için IP'yi değiştirmek yeterlidir; Netflix bölgesi uyuşan ücretli bir hesap ister; ChatGPT'ye kaydolmak için doğrulama kodu alabilen yurt dışı bir telefon numarası gerekir. Hat "açılıyor mu" sorununu çözer; hesap sizin işinizdir.

## Hat nasıl çalışır

Trafiğiniz önce şifrelenip yurt dışındaki bir sunucuya gönderilir, o sunucu da hedefe bağlanır. Hedefin gördüğü, o sunucunun IP'sidir. Bunun üç yolu var: bir istemci, Web Proxy ve bir router. Nasıl seçeceğiniz için [Hangi bağlantı yöntemi hangi duruma uygun](../network/02-choose-your-connection-method.md) yazısına bakın.

## Sık yapılan üç yanlış

- **DNS'i değiştirmek işe yaramaz.** Bağlanamamak bir yol sorunudur, ad çözümleme sorunu değil.
- **Hız, iki nokta arasındaki hatta bağlıdır.** Çin'den dışarı çıkarken darboğaz sınır ötesi bağlantı ve operatörünüzün çıkışıdır; bu yüzden bölge seçimi sunucunun donanımından daha önemlidir. Bkz. [03](03-which-region-is-fastest.md).
- **Çin uygulamalarını kullanırken her şeyin hattan geçmesi gerekmez.** Bölünmüş yönlendirmeyi açın: Varsayılan olarak yalnızca engellenen siteler hattan geçer; Çin siteleri ve Çin'den zaten sorunsuz açılan yurt dışı siteler doğrudan bağlanır, böylece hiçbiri dolambaçlı yola girmez. Bkz. [Router'da bölünmüş yönlendirme](../router/03-router-split-routing.md).

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=overseas-access-01) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=overseas-access-01) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerlidir
