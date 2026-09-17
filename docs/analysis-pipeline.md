# Snapshot'tan yönetişim sonucuna analiz hattı

## Ham yapılandırma ve normalizasyon

Collector ya da manuel yükleme ham içeriği sağlar. Vendor parser desteklenen biçimi ayrıştırır; normalizasyon ortak analiz kavramlarını oluşturur. Parser kapsamı dışındaki nesneler için bu tanıtım genel güvenlik değerlendirmesi iddia etmez.

Snapshot, zaman ve cihaz bağlamıyla saklanır. Böylece bir değerlendirme yalnızca güncel ekrana değil, değerlendirilen veriye bağlanabilir.

## Ham fark ve semantik fark

Ham fark satır/metin seviyesinde değişiklikleri gösterir. Semantik fark desteklenen yapılandırma nesnelerinin eklenmesi, kaldırılması veya değiştirilmesi gibi olguları üretir. İki yaklaşım tamamlayıcıdır; semantik analiz bütün vendor formatının eksiksiz anlaşılması değildir.

## Findings → compliance → risk

| Katman | Yanıtladığı soru | Korunması gereken bağlam |
| --- | --- | --- |
| Finding | Hangi desteklenen durum incelemeye değer? | Nesne, kanıt, önem ve snapshot ilişkisi |
| Compliance | İlgili kontrol nasıl değerlendirildi? | Kontrol, sonuç, referans ve değerlendirme kapsamı |
| Risk | İnceleme önceliği nasıl ifade ediliyor? | Band/score scheme, gerekçe ve üst kanıt |
| Governance | Bu sonuçlar kullanıcıya birlikte nasıl sunuluyor? | Veri varlığı, lineage ve değerlendirme durumu |

Değişim riskinde vendor/kontrol özelinde eşlemeler kullanılır; tek bir genel istatistiksel tehdit olasılığı modeli iddia edilmez.

## İki ayrı risk yaklaşımı

**Değişim bazlı risk:** Snapshot çifti ve ilgili bulgu/kontrol sonuçlarından hareket eder. Yapılandırmadaki yeni veya değiştirilmiş durumların inceleme önceliğini anlatır.

**Baseline / posture riski:** Desteklenen statik denetim kurallarının tek snapshot üzerinde ürettiği bulgulardan hesaplanır. Mevcut uygulamada critical=40, high=20, medium=8, low=2 ağırlıkları toplanır ve skor 100'de sınırlandırılır. Band en yüksek severity'ye göre belirlenir.

Örneğin desteklenen denetimin bir high ve bir medium bulgu üretmesi 28 skor ve high band verir. Bu yalnızca hesaplama örneğidir; gerçek cihaz çıktısı değildir. Skor saldırı olasılığı yüzdesi değildir. Desteklenmeyen veya uygulanmamış denetim için “0 risk” güvenlik kanıtı oluşturmaz.

## Statik denetim kapsamı

Vendor'a bağlı kurallar telnet, varsayılan SNMP community, zayıf yönetim/şifreleme ayarları, eksik protokol kimlik doğrulaması veya yönetim erişimi gibi yapılandırma koşullarını değerlendirebilir. Bütün bu kontroller her vendor'da uygulanmaz; [vendor kapsamı](vendor-coverage.md) ayrı okunmalıdır.

## Framework referansları

ISO 27001, CIS Controls v8 ve KVKK referansları bulguyu kontrol bağlamına yerleştirir. İlgili ISO eşlemelerinde mevcut uygulamada 2013 referansları bulunur; bütün referansların güncel framework sürümüyle eşitlenmiş olduğu iddia edilmez. Eşleme, sertifikasyon veya hukuki uyumluluk kararı değildir.

## Kanıtın korunması

Lineage sonucu snapshot/snapshot çiftine bağlar. Collection job ve correlation bilgisi operasyonel izlemeyi kolaylaştırır. “Not evaluated”, eksik veri ve başarılı değerlendirme farklı durumlardır. Koleksiyon başarısı downstream findings/compliance/risk persistence başarısıyla karıştırılmaz.

[Örnek senaryo](example-workflow.md) · [Mimari](architecture.md)
