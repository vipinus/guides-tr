# 09 · Hiddify'ı her platforma kurmak: Windows, macOS, Linux, Android, iOS

Bu sitenin Hiddify bölümünde kullanılan istemci, sing-box çekirdeği içinde gelen açık kaynaklı Hiddify'dır; kurulduktan sonra başka hiçbir şeyi yapılandırmanız gerekmez. Beş platformda da aynı uygulama kullanılır, ama ilk açılıştaki engeller farklıdır: Windows'ta antivirüs yazılımı tarafından engellenebilir ya da silinebilir; Mac'te "hasarlı" uyarısı alabilirsiniz ve ayrıca bir ağ uzantısını onaylamanız gerekir; Linux'ta VPN modunun çalışması için önce bir yetkilendirme komutu çalıştırmanız gerekir; iPhone'da ise Çin mağazasında bulunmaz. Bu yazı her platform için nereden indirileceğini, nasıl kurulacağını ve ilk açılışta ne yapılacağını anlatıyor; sonunda da bir aboneliği içe aktarıp bağlanmanın en kısa adımları var.

## Nereden indirilir

| Platform | Kurulum dosyası | Nereden indirilir |
|---|---|---|
| Windows | Kurulum dosyası (.exe), yalnızca x64 | Hiddify sayfasının indirme alanı |
| macOS | .dmg, Apple Silicon ve Intel için tek paket | Hiddify sayfasının indirme alanı |
| Linux | .deb (Debian / Ubuntu ailesi), yalnızca x64 | Hiddify sayfasının indirme alanı |
| Android | .apk, iki derleme hâlinde: ARM64 ve x86-64 | Hiddify sayfasının indirme alanı ya da Google Play |
| iPhone / iPad | App Store'daki Hiddify Proxy & VPN | App Store; Çin dışı bölgeye ait bir Apple kimliği gerektirir |

Hiddify sayfasının indirme alanı, kullandığınız sisteme uygun paketi otomatik olarak önerir; diğer sistemlerin paketleri altında listelenir. Her satırın yanında Hiddify'ın resmî yayın sayfasına giden bir "Resmî site" simgesi de var, böylece sürümleri karşılaştırabilirsiniz. Üç masaüstü sistemin (Windows, macOS, Linux) video anlatımları da mevcut.

Masaüstü kurulum dosyaları Hiddify'ın resmî yayın paketlerinin değiştirilmemiş kopyalarıdır; üzerlerinde oynanmamış, yeniden paketlenmemiştir. İzin vermeden önce kendiniz kontrol edebilirsiniz: Kurulum dosyasını VirusTotal'e yükleyip bir göz atın; nasıl yapılacağı için [Sorun giderme 06](../troubleshooting/06-antivirus-false-positive.md) yazısına bakın.

## Windows

1. Kurulum dosyasını Hiddify sayfasının indirme alanından indirin ve çift tıklayarak kurun. (Güncel testlerimizde Windows Güvenliği onu işaretlemiyor; kurduğunuz antivirüs yazılımı işaretlerse [Sorun giderme 06](../troubleshooting/06-antivirus-false-positive.md) yazısının sonundaki SSS'ye bakın.)

## macOS

1. .dmg dosyasını Hiddify sayfasının indirme alanından indirin, açın ve Hiddify'ı "Uygulamalar" klasörüne sürükleyin.
2. "Finder" → "Uygulamalar"da Control tuşunu basılı tutarak Hiddify simgesine tıklayın, "Aç"ı seçin, ardından iletişim kutusunda yeniden "Aç"a tıklayın.
3. Hâlâ açılmıyorsa: "Sistem Ayarları" → "Gizlilik ve Güvenlik", "Güvenlik" bölümünde "Yine de Aç"a tıklayın ve parolanızla onaylayın.
4. "Hasarlı olduğu için açılamıyor" uyarısı alırsanız: Dosya hasarlı değildir; sistemin Gatekeeper'ı onu engelliyordur. "Terminal"i açın, aşağıdaki komutu çalıştırın, Return'e basıp oturum parolanızı girin, sonra Hiddify'ı yeniden açın:

```bash
sudo xattr -dr com.apple.quarantine /Applications/Hiddify.app
```

Bu komut yalnızca dosyayı "internetten indirildi" olarak işaretleyen karantina bayrağını kaldırır ve yalnızca bu uygulamaya uygulanır. Gatekeeper'ı bütün bilgisayarda kapatmak için `sudo spctl --master-disable` **kullanmayın**.

Kurulumdan sonra bağlan düğmesine ilk tıkladığınızda sistem ayrıca bir "Ağ Uzantısı"nı onaylamanızı ister. Bu adımı atlarsanız simge dönüp durur ve hiç bağlanmaz:

- **macOS 15 Sequoia ve sonrası**: "Sistem Ayarları" → "Genel" → "Oturum Açma Öğeleri ve Uzantılar", en alttaki "Uzantılar" bölümüne kaydırın, görünümü "Kategoriye Göre" yapın, "Ağ Uzantıları" yanındaki ⓘ simgesine tıklayın, Hiddify'ın anahtarını açın ve istendiğinde parolanızı girin ya da parmak izinizi kullanın.
- **macOS 13 Ventura / 14 Sonoma**: Önce Hiddify'ı başlatıp bir kez bağlan'a tıklayın; "Sistem Uzantısı Engellendi" uyarısı çıkar. Ardından "Sistem Ayarları" → "Gizlilik ve Güvenlik"e gidin, aşağı kaydırarak "… geliştiricisinin sistem yazılımı yüklenmesi engellendi" satırını bulun, "İzin Ver"e tıklayın ve parolanızı girin.

Şirketin verdiği bir Mac'te bu düğmeler griyse bir cihaz yönetimi politikası onları kilitlemiştir; BT ekibine sorun ya da bunun yerine Cisco, OpenVPN veya Özel ağ istemcilerini kullanın.

## Linux

1. .deb dosyasını Hiddify sayfasının indirme alanından indirin ve çift tıklayarak yazılım merkeziyle kurun ya da indirme klasöründe bir terminal açıp şunu çalıştırın (Debian, Ubuntu ve türevleri):

```bash
sudo apt install ./downloaded-file-name.deb
```

2. Kurduktan hemen sonra bağlanmaya çalışınca "operation not permitted" (işleme izin verilmedi) hatası çıkar ve VPN modu başlamaz; çünkü resmî deb paketi kurulduğunda bu izne sahip değildir. Bir terminal açın, Hiddify'a yetki vermek için aşağıdaki komutu çalıştırın, sonra Hiddify'ı yeniden açın:

```bash
echo /usr/share/hiddify/lib | sudo tee /etc/ld.so.conf.d/hiddify.conf && sudo ldconfig && sudo setcap cap_net_admin,cap_net_raw+ep /usr/share/hiddify/hiddify
```

3. **Her Hiddify güncellemesinden sonra yeniden çalıştırın**: Yetki program dosyasına bağlıdır, güncelleme dosyayı değiştirdiği için yetki kaybolur.

deb paketi x64'tür; ARM Linux cihazlarda OpenVPN kullanın, aynı hesap çalışır.

## Android

1. .apk dosyasını Hiddify sayfasının indirme alanından indirin. Sayfa telefonunuza uygun mimariyi otomatik olarak önerir; telefonların büyük çoğunluğu ARM64'tür. Google Play'i kullanabiliyorsanız doğrudan mağazadan da kurabilirsiniz.
2. Kurulum sırasında "bilinmeyen kaynaklar" hakkında bir uyarı ya da güvenlik yazılımından bir ikaz çıkarsa izin verin.
3. Bağlan'a ilk dokunduğunuzda sistem VPN izni ister; izin verin.

## iPhone / iPad

1. App Store'da "Hiddify"ı arayıp kurun; ücretsizdir.
2. Bulamıyorsanız ya da "Bu uygulama şu anda ülkenizde ya da bölgenizde mevcut değil" uyarısını görüyorsanız: iOS'ta Çin dışı bölgeye ait bir Apple kimliğiyle App Store'dan kurun (Hiddify ABD, Hong Kong, Tayvan, Japonya ve Singapur mağazalarında var). Yeni bir hesap açmanızı öneririz: App Store'da herhangi bir ücretsiz uygulamada "Al"a dokunun → "Yeni Apple Kimliği Oluştur", Hong Kong ya da ABD gibi bir bölge ve ödeme yöntemi olarak "Yok"u seçin. Hesabı yalnızca App Store'da değiştirirsiniz, iCloud etkilenmez. Adımların tamamı için [06 · iOS bir uygulamayı yüklemenize izin vermiyorsa](06-ios-app-store.md) yazısına bakın.
3. Bağlan'a ilk dokunduğunuzda sistem VPN izni ister; izin verin.

Başkasının paylaştığı bir Apple kimliğini **kullanmayın**; cihazınızı uzaktan kilitleyebilirler.

## Kurduktan sonra: aboneliği içe aktarın ve bağlanın

1. Siteye giriş yapın ve Hiddify sayfasını açın.
2. İstediğiniz bölgenin bayrağına tıklayın, bir QR kodu açılır; ya da Çin dışındaki tüm bölgeleri tek seferde içe aktarıp istemcinin otomatik seçmesi için sayfanın üstündeki "Tüm bölgeleri içe aktar · otomatik seç" düğmesine tıklayın. **Çin bölgesi ayrıca içe aktarılır**: Yurt dışından Çin'deki videoları izlemek ya da internet bankacılığını kullanmak için Çin bayrağına tıklayıp onu içe aktarın.
3. QR kodunun altında abonelik türüne göre gruplanmış üç düğme var. Hiddify ilkini kullanır (üzerinde Hiddify / sing-box / GUI.for.SingBox / Karing yazar, alt başlığı "sing-box subscription"); telefonda da bilgisayarda da aynı düğmedir. Telefon: Ona dokunun, sonra Hiddify'a geçip istendiği gibi ekleyin ya da kodu başka bir cihazdaki Hiddify ile tarayın. Bilgisayar: Tıklayınca bir https:// adresi kopyalanır, ardından Hiddify'da "+" → "Add from clipboard"a (panodan ekle) tıklayın.
4. Bağlan'a tıklayın.

Üç düğme arasındaki fark, Clash ve diğer istemcilere nasıl içe aktarılacağı ve aboneliğin süresinin dolup dolmadığı için [02 · Abonelik bağlantısı nasıl içe aktarılır (Hiddify, Clash, Shadowrocket)](02-singbox-subscription-links.md) yazısına bakın. İçe aktardınız ama bağlanamıyorsanız [Sorun giderme 04](../troubleshooting/04-singbox-import-not-connecting.md) yazısına bakın.

## SSS

**Kurulum dosyalarında değişiklik yaptınız mı?** Hayır. Masaüstü kurulum dosyaları Hiddify'ın resmî yayın paketlerinin değiştirilmemiş kopyalarıdır. Hiddify sayfasındaki her satırda resmî yayın sayfasına bir bağlantı var, sürümleri kendiniz karşılaştırabilirsiniz; ayrıca emin olmak için dosyayı VirusTotal'e de yükleyebilirsiniz.


**Mac'imde xattr komutunu çalıştırdım ama yine bağlanmıyor?** Büyük olasılıkla "Ağ Uzantısı" onaylanmamıştır; yukarıdaki macOS bölümünü izleyip Sistem Ayarları'nda Hiddify'ın anahtarını açın.

**Linux'ta Hiddify'ı güncelledikten sonra VPN modu yine çalışmıyor?** Bu beklenen bir durum; güncellemeden sonra yetkilendirme komutunu bir kez daha çalıştırın.

**ARM Windows ya da Linux bilgisayarlarda kullanılabilir mi?** Evet, OpenVPN gibi başka bir erişim yöntemiyle; aynı hesap çalışır. Hiddify masaüstü paketleri şu an x64'tür.

**İzin verme adımlarıyla uğraşmak istemiyor musunuz?** Cisco (Cisco Secure Client), OpenVPN (OpenVPN Connect) ve Özel ağ (Tailscale) çift tıklamayla açılır; antivirüs yazılımları bunları işaretlemez, Mac de "hasarlı" demez ve hesap aynı hesaptır.

## Devamı için

- [Hiddify sayfası: istemci indirmeleri ve her bölgenin QR kodları](https://www.leotun.com/tr/singbox?utm_source=github&utm_content=client-09)
- [Abonelik bağlantısı nasıl içe aktarılır (Hiddify, Clash, Shadowrocket)](https://www.leotun.com/tr/guides/singbox-subscription?utm_source=github&utm_content=client-09)
- [İstemci antivirüse takıldı / Mac hasarlı diyor: önce doğrulayın, sonra izin verin](https://www.leotun.com/tr/guides/antivirus-false-positive?utm_source=github&utm_content=client-09)
- [macOS "Ağ Uzantısı" onayı nedir ve nasıl izin verilir](https://www.leotun.com/tr/guides/macos-network-extension?utm_source=github&utm_content=client-09)
- [iOS bir uygulamayı yüklemenize izin vermiyorsa](https://www.leotun.com/tr/guides/ios-app-store?utm_source=github&utm_content=client-09)

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=client-09) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=client-09) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
