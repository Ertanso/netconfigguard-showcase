# Mühendislik yaklaşımı ve proje vaka anlatımı

Bu bölüm projeyi teknik değerlendirme veya LinkedIn portföy incelemesi için açıklar. Uygulama private kaldığından bu depo kod incelemesinin yerine geçmez; tasarım ve doğrulama yaklaşımını görünür kılar.

## 1. Farklı vendor biçimlerini ortak akışa taşımak

Collector, parser, normalizer, rule pack ve capability descriptor sınırları vendor onboarding'i düzenler. Böylece katalog adı ile uygulanmış analiz derinliği ayrı tutulabilir. Yeni bir vendor girdisi tek başına geniş üretim desteği olarak sunulmaz.

## 2. İş mantığını HTTP ve veritabanından ayırmak

Domain modelleri I/O'dan ayrıdır. Application katmanı kullanım senaryolarını ve ihtiyaç duyduğu interface'leri tanımlar. Persistence bunları uygular; HTTP katmanı istek/yanıt ve wiring ile ilgilenir. Bu tercih saf değerlendirme mantığı ile dış servis davranışını ayrı test etmeyi kolaylaştırır.

## 3. İş tamamlanması ile analizi ayırmak

Toplama job'ı ve analiz persistence adımları farklı sonuçlar taşıyabilir. Correlation, audit ve materialization outcome'ları toplama başarılıyken yönetişim verisinin neden eksik olduğunu açıklamaya yardımcı olur. Bu ayrım operatöre yanlış başarı sinyali verilmesini önlemeyi hedefler.

## 4. Geçmişi ve kanıtı korumak

Snapshot/snapshot pair, bulgu, kontrol ve risk bağlamları ayrı modellerdir. Lineage üzerinden bir özetin hangi veriden üretildiği takip edilir. Eksik veya değerlendirilmemiş sonuçların temiz durum gibi sunulmaması tasarım ilkesidir.

## 5. Offline kurulumun tekrar çalışmasını düşünmek

Installer temiz schema başlangıcı, migration takibi, tekrar kurulum ve dirty-state reddi açısından doğrulanmıştır. Backup/restore ayrı veritabanında çalıştırılmıştır. Bu çalışma yalnızca uygulama feature'larını değil kurulum ve recovery davranışını da ele alır.

## 6. Doğrulamayı açıkça sınırlandırmak

CI, unit/race, zorunlu DB integration, Helm render ve deployment smoke sonuçları ile gerçek cihaz doğrulaması birbirinden ayrılır. Fiziksel/lab cihaz kanıtı bulunmadığında production verified ifadesi kullanılmaz. Uygulama alpha olarak konumlandırılır.

## Teknik görüşmede incelenebilecek başlıklar

- Semantic diff ile raw diff'in tamamlayıcı rolleri.
- Tenant kontrollerinin uygulama sınırındaki yeri.
- Snapshot lineage ve geçmiş raporlama bağlamı.
- Baseline risk ile change risk'in ayrı modellemesi.
- Migration idempotency, transactional uygulama ve failure guard'ları.
- Optional AI'nin deterministik analizden ayrılması.

Performans artışı, müşteri kazanımı veya operasyon maliyeti azalmasına ilişkin ölçüm yayımlanmamıştır. Bunlar pilotta ölçülecek çıktılardır.

[Ana sayfa](../README.md) · [Doğrulama](validation.md)

## Görsel senaryonun hazırlanması

API üzerinden dört laboratuvar cihazı kaydedildi, üç cihaza toplam altı sentetik snapshot yüklendi. Uygulama kendi bulgu, kontrol ve risk verisini üretti; browser capture bu veriyi gerçek arayüzde kaydetti. Capture sırasında bulunan dashboard yetki ve history lineage sorunları ayrı kaynak dalında düzeltildi, tenant yetkileri race testleriyle doğrulandı. Sonuçlar UI üzerinden yeniden yakalandı; veri boşlukları görsel düzenlemeyle kapatılmadı.

[Görsel ürün turu](visual-tour.md)
