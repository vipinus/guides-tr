# 10 · Router'ın arkasındaki NAS, yazıcı ve kameralar etkilenir mi?

VPN router'ı eve girdiğinde ilk endişe genellikle evin geri kalanıdır: NAS, yazıcı ve kameralar çalışmaya devam edecek mi, NAS bütün trafiğini VPN'den mi geçirecek?

## Kısa cevap

Hayır. Bölünmüş yönlendirme varsayılan olarak açıktır: **Evdeki cihazlar arasındaki trafik ve Çin içindeki hizmetlere giden trafik tünele hiç girmez. Yalnızca VPN gerektiren siteler tünelden geçer.**

## Üç tür trafik, üç yol

| Trafik | Yol | Örnekler |
|---|---|---|
| Evdeki cihazlar arasında | Yerel ağda kalır, tünele hiç dokunmaz | NAS'a dosya kopyalamak, TV'ye yansıtmak, yazdırmak |
| Çin içindeki hizmetlere | Doğrudan, kendi genişbant bağlantınız üzerinden | NAS'ın bir Çin bulut diskine eşitlemesi, kameraların Çin bulutuna yükleme yapması, yurt içi indirmeler |
| Engellenen sitelere | Tünelden | YouTube, arama, yapay zekâ araçları |

Yani evde NAS'a dosya kopyalamak tam yerel ağ hızında çalışır; Çin bulut depolamasına yaptığı yedeklemeler de VPN'e dokunmadan genişbant hattınızın tamamını kullanır.

Yurt dışındayken Çin rotası kullanıyorsanız yön tersine döner: Listedeki Çin siteleri tünelden geçer, geri kalan her şey doğrudan gider. Bkz. [03 · Bölünmüş yönlendirme nedir](03-router-split-routing.md).

## Sık karşılaşılan üç durum

**NAS'a dışarıdan erişmek (uzaktan dosyalar, telefon fotoğraflarının yedeği)**
İki yol var:
- Özel ağı (Tailscale) kullanın: NAS'ı ve telefonunuzu aynı hesapla oturum açtırın, NAS'a her yerden cihaz adıyla ulaşın. Genel IP'ye de port yönlendirmeye de gerek yok. Bkz. [Özel ağ ile VPN karşılaştırması](../network/03-private-network-vs-vpn.md).
- Önceden ne yapıyorsanız onu yapmaya devam edin (üreticinin uzaktan erişimi, port yönlendirme). Router bunu engellemez.

**NAS üzerinde çalışan indirmeler**
Çin kaynaklarından yapılan indirmeler doğrudan gider ve etkilenmez. Çin'den zaten sorunsuz açılan yurt dışı sitelerden yapılan indirmeler de (örneğin Apple ve Microsoft indirmeleri) varsayılan olarak doğrudan gider; yalnızca engellenen sitelerden yapılan indirmeler tünelden geçer ve tünel hızında çalışır. İndirmelerin tüneli kullanmasını istemiyorsanız NAS'ı üstteki router'a ya da modeme takın; bu router'ı tamamen atlar.

**Şirket VPN'i gereken iş bilgisayarı**
Onu bu router'dan ayrı olarak üstteki router'ın ya da modemin Wi-Fi'sine bağlayın. Üst üste binen iki VPN genellikle şirket ağına erişimi bozar.

## Bir cihaz uyumsuzluk çıkarırsa

- Cihazda "Özel DNS" (Private DNS) ya da "Güvenli DNS" açıktır. Bu durumda adları router'ı atlayarak kendisi çözümler ve bölünmüş yönlendirme bunu göremez. O ayarı kapatın.
- Hangi Wi-Fi'ye bağlı olduğuna bakın. Modemin Wi-Fi'sindeyse bu router'dan hiç geçmemiştir.

## SSS

**NAS hesabımda bir cihaz hakkı kaplar mı?** Hayır. Router bir hak kaplar, arkasındaki hiçbir şey ayrıca sayılmaz.

**Bütün ev bağlanınca verim biter mi?** Hesaplarda veri sınırsızdır; yurt içi trafik zaten tünele hiç girmez.

**Bir cihazı kalıcı olarak VPN dışında tutabilir miyim?** Evet, onu üstteki router'a ya da modeme bağlayın. Yönetim sayfasından bütün router'ı "Direct" (Doğrudan) moduna da alabilirsiniz, ama bu herkese aynı anda uygulanır.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-10) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-10) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerlidir
