# 01 · Hangi hizmetler Çin IP'si ister

Tek bir ölçüt var: Hizmet, kaynak IP'nizin Çin anakarasında olmadığını gördüğünde sizi reddeder ya da kısıtlı hizmet verir. Aşağıdaki tablo, engellemenin ne kadar katı olduğuna göre sıralanmıştır.

| Kategori | Örnekler | Çin IP'si yoksa ne olur | IP dışında neye bakılır |
|---|---|---|---|
| Video | iQIYI, Tencent Video, Youku, Mango TV, Bilibili'deki bazı anime dizileri | Yalnızca anakarada izlenebildiği söylenir ya da sadece ücretsiz içerik açılır | Uygulama mağazası bölgesi, hesabın kaydedildiği yer |
| Müzik | NetEase Cloud Music, QQ Music, Kugou | Çok sayıda şarkı gri görünür ve çalınamaz | Hiçbir şey |
| Devlet hizmetleri | Ulusal e-devlet platformu, il e-devlet siteleri, vergi, sosyal sigorta, konut fonu | Sayfa açılmaz ya da doğrulama kodu hiç gelmez | Telefon numarası, yüz tanıma |
| Eğitim | CHSI, akademik derece sitesi, üniversitelerin öğrenci işleri sistemleri | Açılmaz ya da aşırı yavaştır | Hiçbir şey |
| Seyahat | 12306, havayolu siteleri | Açılmaz, ödeme başarısız olur | Telefon numarası, ödeme |
| Finans | İnternet bankacılığı, mobil bankacılık, Alipay, WeChat Pay | Giriş risk kontrolüne takılır, havaleler başarısız olur | SIM kart, cihaz parmak izi, yüz |
| Oyunlar | Çin sunucusundaki PC ve mobil oyunlar | Giriş yapabilirsiniz ama gecikme yüksektir ve bağlantı kopar | Gerçek ad doğrulaması |
| Günlük yaşam | Meituan, Ele.me, DiDi, Taobao'nun bazı özellikleri | Konum hataları, siparişler başarısız olur | Konum, telefon numarası |
| Canlı yayın | Douyin, Kuaishou, Douyu | Bazı bölgelerde izlenemez | Hiçbir şey |

## Önemli bir ayrım

**"Çin IP'si gerekmesi" ile "Çin telefon numarası gerekmesi" iki ayrı şeydir.** Video ve müzik yalnızca IP'ye bakar, IP'yi değiştirmek yeterlidir. Devlet hizmetleri, bankacılık ve bilet alma ise IP'nin yanında SMS doğrulama kodu almanızı ve yüz tanımadan geçmenizi de ister. IP "sayfa açılır mı" sorununu çözer; sonraki doğrulama kendi Çin telefon numaranıza ve kimlik belgelerinize bağlıdır.

## IP sorununu çözmenin yolları

Trafiği önce anakaradaki bir sunucuya gönderin, o da hedefe bağlansın. Bunun üç yolu var: bir istemci, Web Proxy ya da bir router. Nasıl seçeceğiniz için kardeş depodaki [Hangi bağlantı yöntemi hangi duruma uygun](../network/02-choose-your-connection-method.md) yazısına bakın.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-01) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-01) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerlidir
