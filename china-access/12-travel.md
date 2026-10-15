# 12 · İş seyahati ve turistik geziler için kurulum

Kısa bir yurt dışı gezisi ya da Çin'e bir iş seyahati için router'a veya protokol öğrenmeye gerek yok: Telefonunuza Cisco istemcisini (Cisco Secure Client) kurun, yola çıkmadan bir kez bağlanmayı deneyin; indiğiniz anda çalışır. İki yön de aynı şeydir: Çin dışındayken Google, şirket e-postası ve haritalar gerektiğinde yakındaki bir yurt dışı bölgeyi seçin; Çin'deyken Çin videoları izlemek ve internet bankacılığına girmek istediğinizde Çin bölgesini seçin. Bu yazı yola çıkmadan önceki on dakikalık hazırlığı, otel ve havalimanı ağlarının iki yaygın tuzağını ve internet bankacılığı ile ödeme uygulamalarının nasıl kullanılacağını anlatıyor.

## Yola çıkmadan önce on dakika

1. Telefonunuza Cisco Secure Client'ı kurun (App Store / Google Play ya da bu sitenin Cisco sayfasındaki kurulum dosyası), bu siteye giriş yapın ve bir bölgenin adresini kopyalamak için bayrağına tıklayıp adresi istemciye girin; sonra bu sitedeki hesabınız ve parolanızla bir kez bağlanıp çalıştığını doğrulayın.
2. İki bölgenin daha adresini kopyalayıp istemciye kaydedin: biri gideceğiniz yere yakın, diğeri yedek. Oradaki ağ farklı olacaktır ve en iyi bölge çoğu zaman aynı olmaz.
3. Dört alan adını (leotun.com → 7d24hrs.com → 7x24btc.com → anyfq.com) ve en az bir destek grubunun giriş bağlantısını not edin; ağını tanımadığınız bir yerde bir şey ters giderse birine ulaşabilesiniz.
4. Dizüstü bilgisayarınıza da kurun ya da web proxy eklentisini kullanın; şirket bilgisayarına istemci kurulamasa bile bu çalışır.

## İndikten sonra

- Yerel bir SIM'e geçtiyseniz ya da dolaşımı açtıysanız istemci doğrudan bağlanır, yeniden ayar gerekmez; dolaşım verisi zaten yurt dışından çıkıyorsa hatta bağlanmak yalnızca çıkış bölgesini sabitlemek içindir.
- Çin dışındayken Google, Gmail, şirket e-postası ve haritalar gerektiğinde: En iyi hız için yakındaki bir yurt dışı bölgeyi seçin.
- Çin'deyken Tencent Video ve iQIYI izlemek, NetEase Cloud Music dinlemek ya da internet bankacılığına girmek istediğinizde: Çin bölgesini seçin. Çin siteleri Çin IP'sinden çıkar, yurt dışı siteler yine yurt dışından çıkar; yani Çin'deyken Çin bölgesine bağlanmak Gmail'i kullanmaya devam etmenize engel olmaz.
- Çin'in içinden bir yurt dışı bölgeye bağlanılamıyorsa: Bölge değiştirin, mobil veriye geçin; o da olmazsa Hiddify'a ya da OpenVPN'e geçin; üç protokolün engellenmesi birbirinden bağımsızdır.

## Otel, havalimanı ve kafe ağlarının iki tuzağı

- Giriş portalı (captive portal): Wi‑Fi'ye bağlandıktan sonra önce tarayıcıda kimlik doğrulamayı tamamlayın, sonra hattı açın. Otomatik bağlanacak şekilde ayarlanmış bir istemci kimlik doğrulamadan önce dener ve başarısız olur; biraz bekleyin ya da elle yeniden bağlanın.
- UDP kısıtlamaları: Pek çok otel ve havalimanı ağı UDP'yi kısar ya da engeller. Cisco TLS üzerinden çalışır ve etkilenmez; seyahatte ilk önerinin Cisco olmasının nedeni de budur. Hiddify ya da Özel ağ kullanıyorsanız ve yavaşsa veya kopuyorsa Cisco'ya geçin.

## İnternet bankacılığı, ödemeler, 12306

Bu uygulamalar giriş IP'sini kaydeder ve yurt dışı ile Çin arasında gidip gelmek risk denetimini en kolay tetikleyen şeydir. Bir iş halletmeniz gerektiğinde önce Çin bölgesine bağlanın, sonra uygulamayı açın; işiniz bitince önce uygulamadan çıkın, sonra bağlantıyı kesin. Seyahat boyunca aynı internet bankasını iki tür ağ arasında sık sık geçiş yaparak kullanmayın.

Gelmeyen SMS doğrulama kodlarının hatla ilgisi yoktur; bu, telefon numarasının dolaşım sorunudur. Yola çıkmadan önce Çin numaranızda dolaşımı açın ya da yurt dışında kod alabilen bir tarifeye geçin.

## SSS

**Gezi yalnızca birkaç gün. Bir ay almam gerekir mi?** Hayır. 24 saatlik ücretsiz denemeyi alın ya da puan yükleyip günlük ödeyin: Bireysel plan günde 1 puan, yani günde yaklaşık 0,32 ABD dolarıdır; birkaç gün için tam uygundur.

**Telefonum ve dizüstü bilgisayarım aynı anda bağlanabilir mi?** Evet. Plana göre bir hesapta aynı anda 2 / 4 / 8 cihaz çevrim içi olabilir (Bireysel / Aile / Kurumsal); Bireysel plan tam bir telefon artı bir dizüstü bilgisayar eder.

**Seyahat için neden Hiddify değil de Cisco öneriliyor?** Tanımadığınız bir ağda en büyük endişe kısıtlanmış UDP'dir. Cisco, bir HTTPS sitesini ziyaret etmekle aynı şekilde TLS üzerinden çalışır ve neredeyse her yerden geçer; Hiddify paket kaybı yüksek ağlarda daha hızlıdır ama UDP kısıtlıyken çalışmaz. İkisini de kurup biri çalışmazsa diğerine geçmek en sağlam yoldur.

**Çin dışında Çin bölgesini kullanmak yerel siteleri yavaşlatır mı?** Yerel siteler doğrudan bağlantıda en akıcıdır: Çin içeriğiyle işiniz bitince bağlantıyı kesin ya da yalnızca gerektiğinde bağlanın.

## Devamı için

- [Cisco AnyConnect indirme ve kurulum](https://www.leotun.com/tr/anyconnect?utm_source=github&utm_content=china-access-12)
- [Yurt dışındaki öğrenciler Çin'e giden VPN'i nasıl kurmalı](https://www.leotun.com/tr/guides/students?utm_source=github&utm_content=china-access-12)
- [Bize nasıl ulaşırsınız, bağlantıyı nasıl koparmazsınız](https://www.leotun.com/tr/guides/stay-in-touch?utm_source=github&utm_content=china-access-12)
- [Çin'e giden VPN: ücretsiz mi, ücretli mi](https://www.leotun.com/tr/guides/free-vs-paid?utm_source=github&utm_content=china-access-12)

Bu yazının sitedeki sürümü: https://www.leotun.com/tr/guides/travel?utm_source=github&utm_content=china-access-12

---
[LeoTun](https://www.leotun.com/tr?utm_source=github&utm_content=china-access-12) ekibi hazırladı · Sorunuz mu var? [İletişim sayfasına](https://www.leotun.com/tr/contact?utm_source=github&utm_content=china-access-12) bakın (gruplar, e-posta ve destek orada listeleniyor) · Kaydolun, 24 saat ücretsiz deneyin; davet ettiğiniz bir arkadaşınız ödeme yaparsa ikiniz de 20 gün Bireysel plan kazanırsınız, süresiz geçerli bir kampanya
