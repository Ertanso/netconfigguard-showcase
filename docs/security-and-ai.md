# Erişim, tenant, lisans ve AI sınırları

## Kimlik doğrulama ve yetkilendirme

JWT, API key, MFA/TOTP ve yapılandırılmış OIDC yolları bulunur. Viewer, operator ve admin rolleri işlem yetkilerinin ayrılmasına yardımcı olur. Tenant bağlamı uygulama kullanım senaryolarında kontrol edilir; başka tenant kaynağına erişim yetkili bağlam gibi ele alınmaz.

Bu yapıların mevcut olması bağımsız güvenlik denetiminden geçmiş oldukları anlamına gelmez. Redis kesintisinde JWT revocation fail-open davranışı bilinen sınırlamalardan biridir. Oturum, rol, secret ve ağ politikaları pilot öncesinde ayrıca değerlendirilmelidir.

## Device credentials

Device credentials AES-256-GCM ile at-rest şifrelenir. Şifreleme anahtarının yönetimi dağıtımın sorumluluğudur. Bu public depoda credential, müşteri yapılandırması, lisans dosyası veya signing key yayımlanmaz.

## Offline ürün lisansı

Ürün lisansı backend'de Ed25519 imzasıyla internet gerektirmeden doğrulanır. Tenant, modül ve kapasite bilgileri taşıyabilir. Aktif, bitişi yaklaşan, grace period, expired read-only ve invalid gibi durumlar hesaplanır; modül ve kota kontrolleri ilgili işlemleri sınırlar. Süresi dolan lisansın yenilenebilmesi için aktivasyon yolları ayrı ele alınır.

Ürün aktivasyon lisansı ile bu deponun telif koşulları iki ayrı konudur. Public dokümantasyon uygulama kaynak lisansı veya ürün kullanım hakkı vermez.

## AI'nin rolü

İsteğe bağlı Anthropic veya Ollama sağlayıcıları üzerinden finding açıklaması, cihaz sohbeti, rapor özeti ve politika taslağı gibi yardımcı işlevler vardır. Ollama yerel kullanım seçeneğidir; bunun bulunması tek başına bütün ortamın air-gapped doğrulandığı anlamına gelmez.

AI risk skorunu veya compliance sonucunu belirleyen karar otoritesi değildir. Üretilen açıklama ve taslaklar insan incelemesine tabidir. Harici AI sağlayıcısı seçilirse gönderilen bağlamın veri politikası ayrıca değerlendirilmelidir. Device secrets'ın AI katmanına iletilmemesi tasarım sınırıdır.

## Alert ve takip

Webhook, Slack ve e-posta kanalları yapılandırılabilir; high/critical sonuçlar ve remediation bağlamı takip akışına taşınabilir. Jira/ServiceNow için proxy tüketimi mümkün olsa da burada yerleşik, doğrulanmış uçtan uca entegrasyon iddia edilmez. Alert gönderimi cihaz üzerinde otomatik düzeltme değildir.

[Operasyon](deployment-and-operations.md) · [Doğrulama sınırları](validation.md)
