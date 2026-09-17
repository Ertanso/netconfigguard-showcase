# Vendor kapsamı ve kanıt seviyesi

Aşağıdaki tablo private uygulamanın canonical depth matrix kaydından 2026-09-17 tarihinde hazırlanmıştır. “Scope” sayısı desteklenen analiz alanlarının kapsam bilgisidir; device model, firmware veya production kurulum sayısı değildir. Collector/static audit sütunları uygulanmış yetenek kaydıdır; gerçek cihaz doğrulama sonucu değildir.

**Deep:** daha geniş scope'lu analiz hattı. **Moderate:** birden fazla kritik scope, genişletme ihtiyacı var. **Foundation:** temel akış, daha dar analiz. **Narrow:** cloud/identity/endpoint gibi belirli policy alanları. **Collectorless:** uzaktan collector yerine dosya/manuel analiz konumlandırması.

| Vendor | Kategori | Derinlik | Scope | Collector | Statik denetim | L3 canlı cihaz kanıtı |
| --- | --- | --- | ---: | --- | --- | --- |
| Fortinet FortiGate | firewall | deep | 10 | Var | Var | Yok |
| Cisco IOS | firewall | deep | 11 | Var | Var | Yok |
| Palo Alto PAN-OS | firewall | deep | 13 | Var | Var | Yok |
| Check Point | firewall | moderate | 7 | Var | Var | Yok |
| Juniper SRX | firewall | moderate | 8 | Var | Var | Yok |
| Cisco Catalyst | switch | moderate | 10 | Var | Var | Yok |
| HPE Aruba AOS-CX | switch | moderate | 8 | Var | Var | Yok |
| Cisco Meraki | wifi | foundation | 3 | Var | Var | Yok |
| Ubiquiti UniFi | wifi | foundation | 3 | Var | Var | Yok |
| MikroTik RouterOS | router | foundation | 3 | Var | Var | Yok |
| Sophos Firewall | firewall | foundation | 3 | Var | Var | Yok |
| WatchGuard Firebox | firewall | foundation | 3 | Var | Var | Yok |
| pfSense | firewall | foundation | 3 | Var | Var | Yok |
| Cisco ASA | firewall | foundation | 3 | Var | Yok | Yok |
| Forcepoint NGFW | firewall | foundation | 3 | Var | Yok | Yok |
| Fortinet FortiWeb | waf_lb | foundation | 3 | Var | Yok | Yok |
| F5 BIG-IP | waf_lb | foundation | 4 | Var | Yok | Yok |
| Citrix ADC | waf_lb | foundation | 3 | Var | Yok | Yok |
| Cloudflare WAF | waf_lb | foundation | 2 | Var | Yok | Yok |
| Cisco Firepower | ips_ids | foundation | 2 | Var | Yok | Yok |
| Suricata / Snort | ips_ids | collectorless | 1 | Yok | Yok | Yok |
| Trend Micro TippingPoint | ips_ids | foundation | 2 | Var | Yok | Yok |
| AWS Security Groups | cloud | narrow | 2 | Var | Yok | Yok |
| Azure NSG | cloud | narrow | 1 | Var | Yok | Yok |
| GCP Firewall | cloud | narrow | 1 | Var | Yok | Yok |
| Kubernetes NetworkPolicy | cloud | narrow | 1 | Var | Yok | Yok |
| Okta | identity | narrow | 2 | Var | Yok | Yok |
| Azure AD | identity | narrow | 2 | Var | Yok | Yok |
| Trend Micro Apex One | edr | narrow | 2 | Var | Yok | Yok |
| Trend Micro Deep Security | edr | narrow | 2 | Var | Yok | Yok |
| SentinelOne | edr | narrow | 2 | Var | Yok | Yok |
| CrowdStrike Falcon | edr | narrow | 2 | Var | Yok | Yok |
| Microsoft Defender | edr | narrow | 2 | Var | Yok | Yok |

## Tabloyu doğru okumak

- Hiçbir girdide kayıtlı L3 canlı cihaz doğrulaması yoktur.
- API/fixture/mock/unit kapsamı, gerçek firmware ve ortamda başarılı toplama kanıtı değildir.
- Collector varlığı erişim, credential, ağ politikası veya cihaz sürümü uyumluluğunu garanti etmez.
- Statik denetim olmayan girdiler diğer değerlendirme akışlarıyla aynı kabul edilmez.
- Katalog sayısı ile canonical depth matrix satır sayısı farklı olabilir; bu tablo yalnızca matrix'te listelenmiş girdileri gösterir. Kayıtlardaki fark production destek iddiasına dönüştürülmez.

Pilot öncesi seçilecek vendor ve firmware için bağlantı, snapshot doğruluğu, parser kapsamı, analiz sonuçları ve failure davranışı ayrı kayıt altına alınmalıdır.

[Analiz hattı](analysis-pipeline.md) · [Doğrulama](validation.md)
