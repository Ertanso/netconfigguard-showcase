# Arayüz ve modül rehberi

Bu rehber uygulamadaki sayfa ve sekmeleri kaynak incelemesine dayanarak açıklar. Public depoda giriş/ilk kurulum görüntülerine ek olarak dolu bir sentetik laboratuvar senaryosundan 18 ekran kaydı, tur videosu ve örnek rapor bulunur. [Açıklamalı görsel turu](visual-tour.md) izleyebilirsiniz.

## Ana sayfalar

| Sayfa | Kullanıcı ne için açar? |
| --- | --- |
| Giriş | API bağlantı bağlamı ve kimlik doğrulama |
| Kontrol paneli | Genel yönetişim görünümünü inceleme |
| Cihazlar | Envanter ve cihaz detayına erişim |
| Politikalar | Yüklü compliance politikaları, kontroller ve vendor filtresi; isteğe bağlı AI politika taslağı |
| Güvenlik | Güvenlik yönetimi ekranı |
| Kullanıcılar | Yetkili kullanıcı yönetimi |
| Tenantlar | Organizasyon bağlamı yönetimi |
| Ayarlar | Ürün ve ortam ayarları |
| Kurulum | On adımlı, devam ettirilebilir kurulum takibi |
| Lisans | Aktivasyon ve lisans durumunun incelenmesi |

Sayfaların varlığı tüm işlemlere her rolden erişilebildiği anlamına gelmez. Backend yetkilendirmesi, tenant ve ürün lisansı erişimi ayrıca sınırlar.

## Cihaz detayındaki çalışma alanları

| Sekme | İçerik ve kullanım |
| --- | --- |
| Genel Bakış | Yönetişim özeti, değişim ve posture bağlamı; ilgili geçmiş/risk görünümü |
| Snapshot Geçmişi | Snapshot listesi, son ham/semantik fark ve seçilen iki snapshot karşılaştırması |
| Bulgular | Değişiklik analizinin bulgu sonuçları |
| Ticketlar | Bulgularla ilgili ticket çalışma alanı; otomatik Jira/ServiceNow entegrasyonu garantisi değildir |
| Güvenlik Denetimi | Desteklenen vendor'larda tek snapshot üzerinde statik denetim |
| Risk | Değişiklik risk çıktıları |
| Uyumluluk | Kontrol değerlendirmeleri ve framework referansları |
| Raporlar | Finding/compliance/risk raporlama verileri |
| Denetim | Audit olayları ve işlem izi |
| İşler | Collection job durumu ve hata bağlamı |
| Chat | Etkinleştirilmiş AI sağlayıcı üzerinden tavsiye niteliğinde cihaz sohbeti |

Cihaz üst eylemlerinde toplama, bağlantı testi, manuel snapshot yükleme ve PDF rapor yolu bulunur. İşlem kapsamı ve başarı, cihaz türüne ve ilgili backend yeteneğine bağlıdır.

## Ekranları nasıl yorumlamalı?

- Snapshot seçimi karşılaştırmanın zaman bağlamını belirler; baz ve hedef yönü önemlidir.
- Değişiklik sonucu ile mevcut yapılandırmanın statik denetimi birbirinden ayrılır.
- Job başarısı snapshot toplandığını gösterebilir; bütün downstream analizlerin başarıyla tamamlandığı anlamına gelmez.
- Veri eksikliği veya değerlendirilmemiş durum temiz/güvenli sonucu gibi yorumlanmamalıdır.

[Gerçek ekranlar](../README.md#gerçek-arayüz) · [Kullanıcı yolculuğu](user-journey.md)
