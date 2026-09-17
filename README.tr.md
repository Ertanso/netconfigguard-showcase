# NetConfigGuard

Ağ yapılandırma değişikliklerini güvenlik bulgularına ve yönetişim özetlerine dönüştüren platform.

**Durum: 0.3.0-alpha.1 · Ticari uygulamanın kaynağı private · Public tanıtım deposu**

[English](README.md) · [Mimari](docs/architecture.md) · [Doğrulama ve yol haritası](docs/validation.md)

## Çözdüğü problem

Farklı cihaz ailelerinde yapılan yapılandırma değişikliklerini izlemek ve bunların güvenlik etkisini anlamak zorlaşabilir. NetConfigGuard yapılandırma geçmişini, anlamlı değişiklikleri, güvenlik bulgularını ve risk özetlerini tek akışta bir araya getirir.

- Yapılandırma snapshot toplama ve sürümleme; semantik fark analizi.
- Hem tek snapshot üzerinde güvenlik durumu hem değişiklik bazlı risk değerlendirmesi.
- ISO 27001, CIS Controls v8 ve KVKK referanslarına eşleme; sertifikasyon veya hukuki uyumluluk kararı değildir.
- React arayüz, rol bazlı erişim, MFA/TOTP, OIDC ve tenant bağlamı.
- Docker/Compose, Helm, offline kurulum ve yerel lisans doğrulama.
- İsteğe bağlı AI açıklamaları; temel kararlar deterministik analizden gelir.

Katalogda **34 vendor girdisi** vardır; toplama ve analiz kapsamları eşit değildir. Alpha sürüm için kayıtlı L3 gerçek cihaz doğrulaması bulunmamaktadır.

## Gerçek arayüz

Aşağıdaki ekranlar izole yerel ilk kurulum ortamından alınmıştır. Müşteri verisi veya örnek cihaz/bulgu üretilmemiştir. Ekrandaki yerel hesap bir geliştirme hesabıdır; public demo hesabı değildir.

![Giriş ekranı](images/login.png)

![İlk kurulum sihirbazı](images/first-run.png)

## Teknik çalışma ve doğrulama

Go API/Worker, React 19/TypeScript, PostgreSQL 16 ve Redis 7 üzerine kuruludur. Dağıtım için Docker ve Helm; gözlemlenebilirlik için Prometheus ve OpenTelemetry kullanılır.

Alpha merge için Go/Web/Helm ve secret scan CI kontrolleri başarılıdır. Yerelde PostgreSQL integration, race, production kimlik doğrulama, linux/arm64 offline temiz/tekrar kurulum ve yedek geri yükleme akışları doğrulanmıştır.

Sıradaki hedefler gerçek cihaz laboratuvar testleri, daha geniş platform doğrulaması, bağımsız güvenlik değerlendirmesi ve ölçümlü pilot kurulumdur. Production doğrulaması iddia edilmemektedir.

## İletişim

Demo görüşmesi, pilot değerlendirmesi veya izinli kaynak incelemesi için [Ertan Soyalp](https://github.com/Ertanso) ile iletişime geçebilirsiniz. Henüz public etkileşimli demo veya demo videosu bulunmamaktadır.

Uygulama kaynağı, kurulum arşivleri ve aktivasyon materyali private depoda tutulur. Bu depo doküman ve ekran görüntülerinden oluşur. Tüm hakları saklıdır; [LICENSE](LICENSE).
