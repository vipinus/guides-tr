# 01 · Yazılımı yüklü router ile ilk adımlar

## Kutudan çıkınca üç adım

1. **Güç ve ağ kablosunu takın**: Router'ın WAN portunu mevcut modeminize ya da üstteki router'a bağlayın ve gösterge ışığının sabitlenmesini bekleyin, yaklaşık bir dakika.
2. **Wi-Fi'ye bağlanın**: Varsayılan Wi-Fi adı ve parolası bilgi kartında yazılıdır (ikisinin de fabrika değeri sitenin alan adıdır). Bağlandıktan sonra bir tarayıcı açın ve yönetim adresine gidin: `http://192.168.11.1`.
3. **Hesabınıza giriş yapın**: Yönetim sayfasında hesap e-postanızı ve parolanızı girip kaydedin (Bireysel, Aile ve Kurumsal hesapların hepsi router kullanabilir). Bundan sonra bu Wi-Fi'ye bağlanan her cihaz otomatik olarak VPN'den geçer.

## Varsayılan parolaları değiştirin

Fabrika yönetim parolası ve Wi-Fi parolası herkesin bildiği değerlerdir; giriş yaptıktan sonra ilk iş bunları değiştirin: yönetim sayfası → System (Sistem) → Administration (Yönetim); Wireless (Kablosuz) → Interfaces (Arayüzler) → Wireless Security (Kablosuz güvenlik).

## Bölünmüş yönlendirme modu

Varsayılan mod bölünmüş yönlendirmedir: Listedeki Çin alan adları VPN'den geçer, geri kalan her şey doğrudan bağlanır. Yurt dışında Çin videosu izliyorsanız ya da TV'yi yaşlı aile büyükleri kullanıyorsa en uygun mod budur. Çin'deyken yurt dışı bir bölge seçtiğinizde yön otomatik olarak döner: Varsayılan olarak yalnızca engellenen siteler ve hizmetler VPN'den geçer; Çin siteleri ve Çin'den zaten sorunsuz açılan yabancı siteler doğrudan bağlanır; bkz. [03 · Router'da bölünmüş yönlendirme nedir](03-router-split-routing.md). Geçici olarak her şeyin VPN'den geçmesi gerektiğinde "Global"e (tam) geçin, işiniz bitince geri dönün.

## SSS

- **Gösterge ışığı normal ama bağlı cihazlarda internet yok**: Yönetim sayfasında hesap durumunu kontrol edin; süresi dolmuş hesap da yanlış parola da orada gösterilir.
- **Başka bir router'a geçmek istiyorsunuz**: Önce sitede eskisinin eşleştirmesini kaldırın; bkz. [MAC bağlama ve router değiştirme](05-mac-binding-and-replacing.md).

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=router-01) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=router-01) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 15'er puan (Bireysel planda yaklaşık 15 gün) kazanırsınız, süresiz geçerli bir kampanya
