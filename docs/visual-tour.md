# NetConfigGuard — görsel ürün turu

**Gerçek çalışan uygulama, sentetik laboratuvar verisi.** Bu galeri müşteri ortamı, canlı cihaz doğrulaması veya üretim referansı değildir. Kayıt: 2026-09-17.

[Tur videosu (MP4)](../media/netconfigguard-laboratory-tour.mp4) · [Örnek cihaz raporu (PDF)](../media/netconfigguard-laboratory-report.pdf) · [Ana sayfa](../README.md)

## Senaryo

HQ firewall'da yönetim erişimi ve politika kapsamı genişletilir; logging/timeout ayarları zayıflatılır. Branch firewall'da bir address object değişir. Cisco router ayrı static posture denetimiyle incelenir. Dördüncü cihazda henüz veri bulunmaz. Böylece dolu sonuçlar kadar değerlendirilmemiş durum da gösterilir.

Dört kayıt oluşturuldu ve üç cihaza toplam altı snapshot API üzerinden yüklendi. Ham yapılandırmalar sentetiktir; findings/compliance/risk çıktıları uygulamanın kendi parser ve analiz hattından gelir. Hazır sayılar veya sahte API yanıtlarıyla dashboard doldurulmadı.

## Kayıt ve sürüm bağlamı

- Uygulama tabanı 0.3.0-alpha.1; kayıt için kullanılan private kaynak commit'i `6e087e1` (`fix/showcase-governance-views`).
- Bu dal dashboard bulk okuma yetki/tenant eşlemesini, geçmiş sorgularının lineage parametresini ve iki yanıltıcı durum metnini düzeltir. Görseller bu geliştirme dalını gösterir; ilk alpha arşivinin birebir ekran kaydı olduğu iddia edilmez.
- Üstteki laboratuvar şeridi kayıt sırasında eklenen açıklama etiketidir; standart ürün navigasyonunun parçası değildir. Analiz sonucu, sayı ve risk verileri değiştirilmedi.
- Tenant, hesap ve cihaz adları örnektir. Dış alert kanalları ve AI kapalı tutuldu. Kaynak, token, credential ve aktivasyon materyali bu depoda yayımlanmaz.
- Görseller 1920 px genişlikte tarayıcı kayıtlarıdır; yazdırılabilir rapor 1440 px genişlikte yakalandı. Uzun ekranları tam boy açarak inceleyebilirsiniz.

## İnceleme rotası

1. Operasyon kontrol paneli
2. Cihaz envanteri
3. Cihaz genel bakış
4. Snapshot geçmişi
5. Seçilen snapshot çiftinin ham farkı
6. Semantik karşılaştırma
7. Değişiklik bulguları
8. Bulgunun kanıt ayrıntısı
9. Eyleme dönük bildirim adayları
10. Tek snapshot güvenlik denetimi
11. Değişim bazlı risk
12. Kontrol değerlendirmeleri
13. Raporlama çalışma alanı
14. Yazdırılabilir cihaz raporu
15. Denetim izi
16. Politika ve kontrol kataloğu
17. Cisco IOS için statik denetim
18. Verisi olmayan cihaz

## Ekranlar

### 1. Operasyon kontrol paneli

Dört laboratuvar cihazının değişim riski, mevcut duruş riski, bulgu ve kontrol dağılımı birlikte görülür. On bulgu, verinin gerçekten analiz edildiği iki firewall değerlendirmesinden gelir; Cisco kaydının statik denetimi ayrıca görünür. Snapshot bulunmayan cihaz değerlendirilmedi olarak ayrılır.

![Operasyon kontrol paneli — laboratuvar verisi](../images/gallery/01-dashboard.png)

### 2. Cihaz envanteri

HQ firewall, branch firewall, Cisco router ve snapshot bulunmayan yeni kayıt. Device isimleri laboratuvar etiketi taşır; yönetim adresleri örnek senaryo bağlamındadır.

![Cihaz envanteri — laboratuvar verisi](../images/gallery/02-inventory.png)

### 3. Cihaz genel bakış

HQ firewall için dokuz değişiklik bulgusu, kontrol/risk çıktıları ve ayrıca on iki statik denetim bulgusu vardır. Değişim riski ile 100/100 baseline posture göstergesi farklı değerlendirmelerdir; yüzde saldırı olasılığı değildir.

![Cihaz genel bakış — laboratuvar verisi](../images/gallery/03-device-overview.png)

### 4. Snapshot geçmişi

API üzerinden yüklenen iki snapshot ve son yapılandırma karşılaştırması. Manuel yükleme kullanıldığı için cihaz üst bilgisindeki collector son toplama alanı henüz toplanmadı gösterebilir; bu bir canlı cihaz toplama demosu değildir.

![Snapshot geçmişi — laboratuvar verisi](../images/gallery/04-snapshots.png)

### 5. Seçilen snapshot çiftinin ham farkı

Operatör iki snapshot seçip karşılaştırma penceresini açar. Ham diff yapılandırma satırlarındaki değişiklikleri gösterir.

![Seçilen snapshot çiftinin ham farkı — laboratuvar verisi](../images/gallery/15-raw-compare.png)

### 6. Semantik karşılaştırma

Aynı snapshot çiftinin desteklenen nesne ve alan değişiklikleri. Metin farkının yanına yapılandırma anlamı eklenir; parser kapsamı dışındaki bütün ayarların değerlendirildiği iddia edilmez.

![Semantik karşılaştırma — laboratuvar verisi](../images/gallery/16-semantic-compare.png)

### 7. Değişiklik bulguları

Sentetik senaryoda netmask genişlemesi, yönetim protokolü, timeout, policy, logging ve yönetici kapsamı değişimleri analiz edilir. Dokuz finding uygulama kurallarınca üretildi; ekran sayaçları veya sonuç payloadları elle düzenlenmedi.

![Değişiklik bulguları — laboratuvar verisi](../images/gallery/05-findings.png)

### 8. Bulgunun kanıt ayrıntısı

Bir finding kartının ayrıntısı açılarak ilgili değişikliğin kanıt bağlamı görünür. Kullanıcı özet sonucundan kaynak yapılandırma olgusuna dönebilir.

![Bulgunun kanıt ayrıntısı — laboratuvar verisi](../images/gallery/17-finding-evidence.png)

### 9. Eyleme dönük bildirim adayları

High/critical bulgulara ilişkin öncelik ve remediation bağlamı. Buradaki ticket görünümü bildirim adayı verisidir; müşteri ticket sistemi veya gerçekleşmiş Slack/webhook/e-posta teslimi değildir. Kayıtta dış bildirim kanalları kapalıdır.

![Eyleme dönük bildirim adayları — laboratuvar verisi](../images/gallery/06-tickets.png)

### 10. Tek snapshot güvenlik denetimi

Mevcut yapılandırma üzerinde unrestricted trusthost, super_admin, Telnet, timeout, policy logging ve ilgili posture kuralları değerlendirilir. Bu örnekte 12 statik bulgu, critical band ve 100 skor üretilmiştir.

![Tek snapshot güvenlik denetimi — laboratuvar verisi](../images/gallery/07-static-audit.png)

### 11. Değişim bazlı risk

Snapshot çifti ile ilişkili kontrol sonuçlarına dayanan risk assessment kayıtları. HQ senaryosunda iki critical ve yedi high assessment vardır; baseline skoruyla aynı gösterge değildir.

![Değişim bazlı risk — laboratuvar verisi](../images/gallery/08-change-risk.png)

### 12. Kontrol değerlendirmeleri

İlgili kontrol, durum ve framework referansları görülür. Bu senaryoda dokuz desteklenen kontrol non-compliant değerlendirilmiştir. Bu sonuç bütün kurumun ISO/CIS/KVKK uyum oranı veya sertifikasyon sonucu değildir.

![Kontrol değerlendirmeleri — laboratuvar verisi](../images/gallery/09-compliance.png)

### 13. Raporlama çalışma alanı

Finding, compliance ve risk raporlama verisi arayüzde incelenir. Rapor bağlamı analiz edilen snapshot lineage ile sınırlıdır.

![Raporlama çalışma alanı — laboratuvar verisi](../images/gallery/10-reports.png)

### 14. Yazdırılabilir cihaz raporu

Uygulamanın HTML rapor çıktısı: yönetici özeti, bulgu tablosu, framework/kontrol ve risk bölümleri. Ekteki PDF bu gerçek HTML çıktısının Chromium üzerinden yazdırılmasıyla oluşturulmuştur; endpoint doğrudan binary PDF üretmiyor.

![Yazdırılabilir cihaz raporu — laboratuvar verisi](../images/gallery/18-printable-report.png)

### 15. Denetim izi

Laboratuvarda yapılan gerçek API işlemlerinin audit kayıtları. Olaylar seed SQL ile uydurulmadı; cihaz ve snapshot işlemleri uygulama üzerinden çalıştırıldı.

![Denetim izi — laboratuvar verisi](../images/gallery/11-audit.png)

### 16. Politika ve kontrol kataloğu

Mevcut compliance politikaları ve kontrol listeleri. Politika eşlemeleri denetimi destekleyen referanslardır; sertifika değildir. Bu kayıtta AI politika taslağı üretilmedi.

![Politika ve kontrol kataloğu — laboratuvar verisi](../images/gallery/12-policies.png)

### 17. Cisco IOS için statik denetim

Sanitize edilmiş sentetik Cisco fixture yapılandırması tek snapshot denetiminde incelenir. Bu cihazın değişim materialization verisi eksik olduğundan dashboard değişim bölümünde değerlendirilmedi gösterilir; bu ayrım gizlenmez.

![Cisco IOS için statik denetim — laboratuvar verisi](../images/gallery/13-router-audit.png)

### 18. Verisi olmayan cihaz

Yeni kayıt için henüz snapshot yok. Bu ekran değerlendirilebilir veri olmamasını gösterir; temiz veya güvenli cihaz kanıtı değildir.

![Verisi olmayan cihaz — laboratuvar verisi](../images/gallery/14-no-snapshot.png)

## Ne gösterilmiyor?

Canlı collector bağlantısı, başarılı dış bildirim teslimi, gerçek müşteri yükü, AI sağlayıcı yanıtı, HA/failover veya production pilot kabulü bu kayıtla doğrulanmaz. Snapshot bulunmayan kaydın static audit isteği expected 409 üretir; bunun için değerlendirilmedi durumu gösterilir.

[Uçtan uca yolculuk](user-journey.md) · [Analiz hattı](analysis-pipeline.md) · [Doğrulama ve yol haritası](validation.md)
