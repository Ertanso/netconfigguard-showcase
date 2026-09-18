# Ayrıntılı Türkçe ürün anlatımı

Gerçek uygulama ekranlarından hazırlanmış, Türkçe sentetik sesli ürün turu. Ses: Ahmet Neural. İnsan sesi klonlanmamıştır.

Her bölüm ekranın işlevini, inceleme gerekçesini ve mevcut kapsamı anlatır. Sektör örnekleri açıklayıcı bağlamdır; ölçülmüş müşteri sonucu veya tüm riskleri bulma garantisi değildir.

[Videoyu aç](../media/netconfigguard-product-walkthrough.tr.mp4) · [Altyazı](../media/netconfigguard-product-walkthrough.tr.srt)

## 00:00 — NetConfigGuard

Bir sistem çalışıyor olabilir. Peki, yapılandırması gerçekten güvenli mi? Bir erişim kuralı genişletildiğinde veya kayıt tutma kapatıldığında, hizmet devam edebilir. Ama güvenlik duruşu değişmiştir. Net Config Guard, gözden kaçabilecek bu riskleri kanıtlarıyla görünür kılmak için geliştiriliyor. Şimdi, sentetik verilerle çalışan gerçek uygulama üzerinden, değişiklikten rapora uzanan yolculuğu birlikte inceleyelim.

## 00:35 — Operasyon kontrol paneli

İlk ekran, operasyon kontrol paneli. Burada tek bir risk sayısından fazlasını görüyoruz. Değişikliklerden doğan risk ile mevcut yapılandırmanın güvenlik duruşu ayrı gösteriliyor. Bu ayrım önemli: bugün hiçbir değişiklik yapılmamış olması, sistemin güvenli olduğu anlamına gelmez. Ekipler bu görünümden incelemeye nereden başlayacaklarını belirleyebilir. Veri bulunmayan cihazlar da sonuç üretilmiş cihazlardan ayrı tutuluyor.

## 01:10 — Cihaz envanteri

Envanter, incelemenin başlangıç noktası. Hangi cihazın hangi üreticiye ait olduğunu ve hangi yapılandırmaların değerlendirileceğini burada takip ediyoruz. Bu laboratuvarda iki güvenlik duvarı, bir yönlendirici ve henüz verisi olmayan yeni bir cihaz var. Farklı sistemler farklı yapılandırma dilleri kullanıyor. Ortak bir envanter, bu çeşitliliği tek bir inceleme akışında yönetmek için ilk adım.

## 01:42 — Cihazın genel görünümü

Bir cihazı açtığımızda, o cihazın inceleme bağlamını görüyoruz. Değişiklik bulguları, kontrol sonuçları ve risk çıktıları burada bir araya geliyor. Mevcut yapılandırmanın statik denetimi ise ayrı bir değerlendirme. Neden? Çünkü bir değişikliğin oluşturduğu risk ile önceden var olan zayıflık aynı şey değil. Buradaki skorlar, incelemeye yardımcı göstergeler; bir saldırının gerçekleşme olasılığı olarak yorumlanmamalı.

## 02:17 — Snapshot geçmişi

Snapshot geçmişi, yapılandırmanın zaman içindeki izini tutuyor. Bir ayarın ne zaman ve nasıl değiştiğini anlamak için önceki duruma ihtiyacımız var. Yalnızca son yapılandırmaya bakarsak, değişikliğin başlangıç noktasını kaçırabiliriz. Bu demoda snapshot'lar manuel olarak yüklenmiş durumda. Canlı cihaz toplaması gösterilmiyor. Geçmiş sürümler, karşılaştırma ve düzeltme sonrası yeniden değerlendirme için temel oluşturuyor.

## 02:52 — Ham yapılandırma farkı

Ham fark ekranında, eklenen ve kaldırılan satırları görüyoruz. Bu görünüm, değişikliği doğrudan yapılandırma üzerinde doğrulamak isteyen uzman için önemli. Ancak bir satırın değişmesi, tek başına güvenlik etkisini açıklamaz. Bir değer değişikliği erişim kapsamını genişletebilir; başka bir değişiklik yalnızca açıklama metnini güncelleyebilir. Bu nedenle ham kanıtı koruyor, sonraki adımda değişikliğin anlamını da inceliyoruz.

## 03:26 — Semantik karşılaştırma

Semantik karşılaştırma burada devreye giriyor. Desteklenen parser, yapılandırmayı nesne ve alan bağlamında inceliyor. Örneğimizde bir adres nesnesinin ağ maskesi değişiyor ve kapsamı genişliyor. Uzun bir satır listesi içinde kaybolabilecek bu değişikliği, ilgili nesne üzerinden inceleyebiliyoruz. Amaç yalnızca ne değiştiğini göstermek değil; uzmanın bu değişikliğin neden önemli olabileceğini daha kolay değerlendirmesini sağlamak.

## 04:01 — Değişiklik bulguları

Bulgular ekranında değişiklikler, güvenlik incelemesine konu olan sonuçlara dönüşüyor. Bu laboratuvarda yönetim erişimi, adres kapsamı ve politika ayarları değiştirilmiş durumda. Bulgular uygulamanın kendi analiz hattından geliyor. Buradaki değer, ekiplerin elle incelemede gözden kaçırabileceği değişiklikleri bir araya getirmek. Sonuçlar desteklenen kuralların kapsamıyla sınırlı; her riski bulduğumuz veya insan değerlendirmesine gerek kalmadığı iddia edilmiyor.

## 04:37 — Bulgunun kanıtı

Şimdi bir bulgunun ayrıntısını açıyoruz. Adres nesnesinin ağ maskesi genişletilmiş. Ekranda önceki ve sonraki değerleri, nesnenin bağlamını ve düzeltme önerisini görüyoruz. Bu kanıt, değişikliğin amaçlı mı yoksa yanlışlıkla mı yapıldığını araştırmak için kullanılabilir. Net Config Guard değişikliği operatör adına geri almıyor. İnceleme ve düzeltme kararı, kurumun yetkili değişiklik sürecinde veriliyor.

## 05:11 — Bildirim adayları

Bildirim adayları, bulguyu eyleme dönük incelemeye taşımak için hazırlanıyor. Bir sonuç görmek kadar, hangi konunun takip edilmesi gerektiğini anlamak da önemli. Burada gösterilenler bildirim adayları; dış bir kanala gönderilmiş veya teslim edilmiş mesajlar değil. Demo sırasında dış kanallar kapalı. Bu ayrım sayesinde kullanıcı, analiz sonucu ile bildirimin gerçekten iletilmesini birbirine karıştırmıyor.

## 05:43 — Tek snapshot güvenlik denetimi

Statik güvenlik denetimi, tek bir snapshot üzerinde çalışıyor. Burada soru, son değişiklik neydi değil; mevcut ayarlarda hangi zayıflıklar var? Yönetim erişimi veya kayıt tutma gibi ayarlar, uzun süredir aynı kaldıkları hâlde inceleme gerektirebilir. Değişiklik analizini bu yüzden tek başına yeterli görmüyoruz. Statik denetim, desteklenen üretici ve kurallar kapsamında mevcut yapılandırmaya ayrı bir bakış sağlıyor.

## 06:17 — Değişim bazlı risk

Risk ekranı, değişiklik bulgularını önem seviyeleri ve ilgili değerlendirmelerle birlikte sunuyor. Amaç, çok sayıda sonuç arasında hangi konunun önce inceleneceğini kolaylaştırmak. Bir risk skoru tek başına karar vermek için yeterli değil. Değişikliğin kanıtı, cihazın rolü ve kurumun erişim ihtiyaçları da değerlendirilmelidir. Bu yüzden risk çıktısını, bulgu ve kontrol bağlamından koparmadan gösteriyoruz.

## 06:50 — Kontrol değerlendirmeleri

Kontrol değerlendirmeleri, teknik bulguların hangi kontrol tanımlarıyla ilişkili olduğunu görmemizi sağlıyor. Ekipler yalnızca tek tek hataları değil, değerlendirme kapsamını da takip etmek ister. Bu ekran, sonuçların kontrol bazında incelenmesini destekliyor. Ancak bir framework referansı veya başarılı kontrol sonucu, sertifikasyon anlamına gelmez. Kontrol çıktıları incelemeye yardımcıdır; kurumun tüm güvenlik süreçlerini doğruladığı iddia edilmez.

## 07:27 — Raporlama çalışma alanı

Raporlama çalışma alanı, farklı ekranlarda incelenen sonuçları bir araya getiriyor. Bulgular, kontroller ve risk değerlendirmeleri aynı cihaz bağlamında özetleniyor. Teknik inceleme sırasında ayrıntıya ihtiyaç duyarız; sonucu başka bir ekiple paylaşırken ise anlaşılır bir özet gerekir. Bu görünümün amacı, bulgunun önemini anlatırken kanıtını ve kapsamını kaybetmemek. Böylece değerlendirme, yalnızca ekranda görülen bir sayı olarak kalmıyor.

## 08:02 — Paylaşılabilir cihaz raporu

Yazdırılabilir cihaz raporu, incelemeyi paylaşılabilir bir belgeye dönüştürüyor. Bu örnek, uygulamanın oluşturduğu HTML raporunun tarayıcı üzerinden PDF'e aktarılmış hâli. Yönetici özeti ve ilgili sonuçlar, cihaz bağlamıyla birlikte gösteriliyor. Bir değişikliğin neden takip edilmesi gerektiğini anlatmak için kullanılabilir. Rapor sentetik laboratuvar verisine dayanıyor; müşteri ortamında doğrulanmış bir güvenlik değerlendirmesi olarak sunulmuyor.

## 08:38 — Denetim izi

Denetim izi, uygulamadaki işlemleri kullanıcı ve zaman bağlamında incelemeye yardımcı oluyor. Operasyonlarda sadece sonucun ne olduğu değil, hangi işlemlerin yapıldığı da araştırılabilir. Burada laboratuvar işlemlerinin kayıtlarını görüyoruz. Bu görünüm, yapılandırmayı canlı cihaz üzerinde kimin değiştirdiğini otomatik olarak kanıtladığı anlamına gelmiyor. Uygulama içindeki işlem izi ile cihazdaki değişikliğin kaynağını ayrı değerlendirmek gerekiyor.

## 09:13 — Politika ve kontrol kataloğu

Politika ve kontrol kataloğu, değerlendirmelerin dayandığı tanımları görünür kılıyor. Bir bulgunun neden üretildiğini sorgulamak isteyen uzman, ilgili değerlendirme çerçevesini inceleyebilmeli. Katalog bu şeffaflığı destekliyor. Burada listelenen tanımların sayısı, her üreticide aynı kapsamın çalıştığı anlamına gelmez. Parser, kural ve üretici desteği birlikte değerlendirilmelidir. Mevcut kapsam tanıtım deposunda ayrıca belgeleniyor.

## 09:49 — Cisco IOS statik denetimi

Bu ekranda Cisco yönlendirici örneğini görüyoruz. Aynı kullanıcı akışı, farklı üreticinin yapılandırması için statik denetim sonuçlarını sunuyor. Üreticiler arasında komutlar ve yapılandırma anlamları değiştiği için, kapsamın ayrıca doğrulanması gerekiyor. Bu örnekte statik denetim gösteriliyor; her üreticide tüm analizlerin eşit düzeyde çalıştığını söylemiyoruz. Ortak platform yaklaşımı, üreticiye özel ayrıntıları yok saymadan ortak bir inceleme deneyimi kurmayı hedefliyor.

## 10:26 — Verisi olmayan cihaz

Son cihazda henüz snapshot yok. Bu nedenle değerlendirme sonucu da yok. Bu durum özellikle önemli: veri bulunmaması, risk bulunmaması demek değildir. Net Config Guard bu cihazı güvenli olarak işaretlemek yerine değerlendirilmemiş olarak gösteriyor. Kullanıcı böylece önce veri toplaması gerektiğini anlayabiliyor. Eksik bilgi ile başarılı analizi ayırmak, anlamlı bir risk görünümünün temel koşullarından biri.

## 11:00 — Yapılandırmadan kanıta

Net Config Guard'ın hedefi, yapılandırma kaynaklı riskleri bir sorun ortaya çıktıktan sonra araştırmakla sınırlı kalmadan, analiz edilen değişikliklerde görünür kılmak. Bugünkü kapsam ağ cihazları ve güvenlik duvarlarıyla başlıyor. Daha geniş siber güvenlik ürünleri ve yapılandırılabilir sistemler ise geliştirme vizyonu. Proje alpha ve laboratuvar aşamasında. Teknik dokümantasyon, mevcut kapsam ve örnek raporu tanıtım deposundan inceleyebilirsiniz.
