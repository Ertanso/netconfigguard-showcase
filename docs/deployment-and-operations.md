# Dağıtım ve operasyon yaşam döngüsü

Bu belge kurulum komutları veya dağıtım arşivi yerine ürünün operasyon yaklaşımını açıklar. Yetkili uygulama erişimi için ürün sahibiyle görüşülür.

## Bileşenler

| Bileşen | Görev |
| --- | --- |
| Web / nginx | React arayüzü ve API erişiminin dağıtım katmanı |
| Go API | Kimlik, tenant, cihaz ve değerlendirme kullanım senaryoları |
| Go Worker | Toplama ve uygulanabilir analiz/materialization işleri |
| PostgreSQL | Uygulama kayıtları, snapshot ve değerlendirme persistence |
| Redis | Cache/oturumla ilişkili destek servisleri; job yürütmesinin tek kaynağı gibi yorumlanmaz |
| Prometheus / Grafana / OpenTelemetry | Yapılandırıldığı ölçüde metrik, görünüm ve tracing |

Mevcut collection lifecycle PostgreSQL job kayıtları ve worker polling akışı kullanır. Redis'in mimaride bulunması bütün job'ların Redis kuyruğuyla yürütüldüğü anlamına gelmez.

## Dağıtım seçenekleri

Docker/Compose ve Kubernetes/Helm yolları vardır. Offline paket imajları ve kurulum dosyalarını taşır. Doğrulanmış alpha arşiv hedefi linux/arm64'tür; linux/amd64 runtime doğrulaması ayrıca yapılmamıştır. Public tanıtım deposu container imajları veya kurulum paketi dağıtmaz.

## Temiz kurulum ve migration

Offline installer uygulamayı başlatmadan önce schema hazırlığını yapar; migration metadata'sını takip eder ve migration'ları transactional uygular. Tamamlanmış migration'lar tekrar kurulumda atlanır. Dirty state veya mevcut fakat takip edilmeyen schema otomatik akışı durdurur ve operatör incelemesi ister.

Mevcut uygulamada 20 versioned migration vardır. Installer'ın migration takip metadata'sı ayrıca bulunur. Bu davranış her eski kurulumu otomatik ve risksiz yükseltme garantisi değildir.

## Ağ ve TLS

Production Compose iç servislerin host port yayınını sınırlar. PostgreSQL TLS dosyaları hedef ortamda oluşturulur. TLS şifrelemesi ile sunucu sertifika kimliği doğrulaması ayrıdır; certificate verification için uygun CA/verify-full ayarları gerekir. Web dış erişimi HTTPS reverse proxy arkasında hazırlanmalı, metrics erişimi kısıtlanmalıdır.

## Job ve analiz hatalarını ayırma

Job pending/queued/running/succeeded/failed durumlarını taşır. Zamanlar, attempt/error bağlamı ve correlation kimliği incelemeye yardımcı olur. Aynı tenant/cihaz için aktif toplama işi varken yeni toplama conflict ile reddedilebilir.

Başarılı snapshot toplamasından sonra findings, compliance veya risk materialization adımı başarısız olabilir. Operatör yalnızca job sonucuna bakarak bütün analizlerin tamamlandığını varsaymamalıdır. Log ve audit outcome'ları bu ayrımı destekler.

## Backup, restore ve işletim

Yerel doğrulamada PostgreSQL dump ayrı disposable veritabanına restore edilmiştir. Bu test, hedef production ölçeğinde disaster recovery tatbikatı veya belirlenmiş RPO/RTO kanıtı değildir. Pilot sırasında yedek bütünlüğü, restore süresi, retention, secret recovery ve sorumluluklar ölçülmelidir.

Health/readiness, metrikler, correlation logları ve audit verisi birlikte incelenir. Logların varlığı tek başına alert rotası veya 7/24 operasyon hizmeti olduğu anlamına gelmez.

[Doğrulama kaydı](validation.md) · [Mimari](architecture.md)
