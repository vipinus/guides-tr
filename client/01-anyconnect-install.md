# 01 · Cisco AnyConnect: her platformda kurulum, bağlanma ve güncelleme

> Sitedeki sürüm (daha uzun): https://www.leotun.com/tr/guides/anyconnect-china?utm_source=github&utm_content=client-01

AnyConnect, Cisco'nun kurumsal VPN istemcisidir. Resmî adı artık **Cisco Secure Client**; çalışma şekli aynı. Sertifika dosyasına ya da profil içe aktarmaya gerek yok: adresi, hesabınızı ve parolanızı girin, bağlanabilirsiniz. Çin'de çalışıp çalışmadığı ve bağlanmadığında neye geçeceğiniz için [Çin'den yurt dışı hizmetlere erişim, rehber 02](https://github.com/vipinus/guides-zh-CN/blob/main/overseas-access/02-anyconnect-in-china.md) yazısına bakın (Çince).

## Kurulum

| Platform | Ne kurulur | Nereden indirilir |
|---|---|---|
| Windows 10 ve sonrası | Cisco Secure Client 5.x | [Sitedeki Cisco sayfası](https://www.leotun.com/tr/anyconnect?utm_source=github&utm_content=client-01) |
| Windows 7 / 8 | AnyConnect 4.9 (bu sürümleri destekleyen son sürüm; artık güncellenmiyor) | Yukarıdakiyle aynı |
| macOS | Cisco Secure Client 5.x | Yukarıdakiyle aynı |
| iOS | Cisco Secure Client | App Store; mağazada çıkmıyorsa aynı protokolü kullanan açık kaynaklı OpenConnect'i kurun |
| Android | Cisco Secure Client | Google Play ya da sitedeki sayfada bulunan APK |
| Linux | Sitedeki sayfada bulunan kurulum dosyası ya da dağıtımınızın deposundaki openconnect | Yukarıdakiyle aynı |

Windows'ta açık kaynaklı OpenConnect-GUI de var; aynı hesapla onunla da bağlanabilirsiniz.

## Dört adımda bağlanma

1. İstemciyi açın ve adres alanına sunucu adresini girin. LeoTun kullanıcıları sitede bir bölgenin **bayrağına tıklayarak** o bölgenin adresini kopyalayabilir.
2. Hesabınızı (kayıt olduğunuz e-posta) ve parolanızı girin.
3. "Connected" (Bağlandı) yazısını görünce IP'nizi gösteren bir sayfa açın ve çıkışınızın seçtiğiniz bölgede olduğunu doğrulayın.
4. Bölge değiştirmek için başka bir adres kullanın. İstemci kullandığınız adresleri hatırlar; bir dahaki sefere açılır listeden seçebilirsiniz.

## Güncelleme

Önce kaldırmanıza gerek yok: Yeni sürümü eskisinin üzerine kurun, kayıtlı adresleriniz korunur. Telefonda uygulama mağazasından güncelleyin. Büyük bir işletim sistemi yükseltmesinden sonra bağlantı sorunlarını araştırmadan önce istemciyi güncelleyin.

## Sık görülen mesajlar

| Mesaj | Anlamı |
|---|---|
| Login failed | Hesap ya da parola yanlış veya hesabın süresi dolmuş |
| Untrusted server certificate | Büyük olasılıkla sistem saati yanlış ya da bulunduğunuz ağ şifreli bağlantılara müdahale ediyor; başka bir ağ deneyin |
| Connection attempt has failed | Bu adrese şu an ulaşılamıyor; bölge değiştirin |

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-01) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-01) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 4 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
