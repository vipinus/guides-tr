# 02 · Cisco AnyConnect Çin'de çalışır mı

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/anyconnect-china?utm_source=github&utm_content=overseas-access-02

Evet. AnyConnect, Cisco'nun kurumsal VPN protokolüdür. Dünyanın her yerinde şirketler uzaktan çalışma için ona güvenir, yabancı şirketlerin Çin şubeleri de her gün kullanır; bu yüzden onu topyekûn yasaklamanın bedeli çok yüksektir. **Gerçekte engellenen protokol değil, belirli bir sunucu adresidir.** Dolayısıyla "çalışır mı" sorusunun cevabı, sağlayıcının yeterince adresi olup olmadığına ve bunları yeterince hızlı değiştirip değiştirmediğine bağlıdır.

## Kendine özgü VPN uygulamalarından neden engellemeye daha dayanıklı

| | AnyConnect | Kendine özgü VPN uygulaması |
|---|---|---|
| Trafik izi | Standart TLS, bir HTTPS siteyi ziyaret etmekle aynı | Kendi protokolü, izi sabit |
| Bir kez tanındığında | Yalnızca o adres bağlanmaz olur | Uygulamanın tamamı çalışmaz olur |
| İstemci | Cisco yayımlar; açık kaynaklı alternatifi OpenConnect her platformda var | Uygulama mağazasından kaldırıldığında ortadan kalkar |

LeoTun 24 bölgede kendi makinelerini işletir. Bir adres işaretlendiğinde yenisiyle değiştirilir, alan adı otomatik olarak yeniden yönlendirilir; istemcinizde kayıtlı adresi değiştirmeniz gerekmez.

## Nasıl kurulur

1. Sitenin Cisco sayfasından sisteminize uygun kurulum dosyasını indirin. Windows 10 ve üzeri, macOS, iOS, Android ve Linux'un hepsi var; Windows 7/8 yalnızca onları destekleyen son sürüm olan 4.9'u kullanabilir.
2. İstemciyi açın ve adres alanına sunucu adresini girin — sitede bir bölgenin bayrağına tıklayarak kopyalayın.
3. Hesabınızı ve parolanızı girip bağlanın. Sertifika dosyası da yapılandırma içe aktarma da gerekmez.
4. "Connected" (bağlı) yazısını gördüğünüzde çıkış IP'nizi kontrol edin.

## Bağlanmıyorsa bu sırayla ilerleyin

1. **Başka bir bölgeye geçin.** Başka bir bölge bağlanıyorsa yalnızca o sunucuya geçici olarak ulaşılamıyordur.
2. **Ağ değiştirin.** Genişbant olmuyorsa mobil veriye geçin, tersi de geçerli; farklı operatörlerdeki engellemeler aynı anda olmaz.
3. **Hatayı okuyun.** `Login failed` hesap ya da parola veya süre dolması demektir; `Untrusted server certificate` büyük olasılıkla sistem saatinin yanlış olması ya da bulunduğunuz ağın TLS'yi araya girerek incelemesidir, ağ değiştirin; yalnızca `Connection attempt has failed` adrese ulaşılamadığı anlamına gelir.
4. **İstemciyi güncelleyin.** Bu özellikle büyük bir sistem yükseltmesinden sonra önemlidir.
5. **Bağlantı yöntemini değiştirin.** Aynı hesapla OpenVPN ya da Hiddify kullanarak aynı sunuculara bağlanabilirsiniz; üç protokole yönelik engellemeler birbirinden bağımsızdır. Bkz. [02 · Hangi bağlantı yöntemi hangi duruma uygun](../network/02-choose-your-connection-method.md).

## Cisco AnyConnect'i güncellemek

Cisco adını Cisco Secure Client olarak değiştirdi; kullanımı aynı. Önce kaldırmanıza gerek yok: Yeni sürümü eskisinin üzerine kurun, kayıtlı adresler korunur. Telefonlarda App Store / Google Play'den güncelleyin; mağaza aramasında bulunamıyorsa aynı protokolü ve aynı hesabı kullanan açık kaynaklı OpenConnect'i kullanın (iOS mağaza bölgesini değiştirmek için bkz. [İstemci 06](../client/06-ios-app-store.md)).

## SSS

**Yavaşlık bir kısıtlama işareti mi?** Önce bölge değiştirin: Sitedeki bölge listesindeki kırmızı, sarı ve yeşil ışıklara bakın ve yeşil olanı seçin. Hâlâ yavaşsa genellikle neden yerel genişbanttır: site ya da apartman genelinde paylaşılan toplu genişbant ya da birbirine uymayan operatör ve bölge (kuzeyde China Unicom: Japonya ya da Kore; güneyde China Telecom: Güneydoğu Asya ya da Avustralya; diğer sağlayıcılar: Çin giriş noktaları).

**Aynı adres neden bazen iyi bazen kötü?** Adres bir alan adıdır ve arkasındaki makineler engellemelere ve yüke göre otomatik değiştirilir. Bir iki dakika bekleyip yeniden denemek genellikle işe yarar; büyük olasılıkla tam geçiş anına denk gelmişsinizdir.

**Uzun süre bağlı kalınca kendiliğinden kopar mı?** Süreden dolayı kopmaz. Hesabın süresi dolduğunda sunucu bağlantınızı keser; yenileyip yeniden bağlanın.

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=overseas-access-02) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=overseas-access-02) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
