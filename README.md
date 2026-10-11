# FIXIT Ticket — Android relizləri

FIXIT Ticket mobil tətbiqinin **imzalı APK** faylları. Mənbə kodu burada deyil.

## Quraşdırma

Ən son versiya: [`latest.json`](latest.json)-da göstərilən fayl (`apk/` qovluğu).

1. APK-nı telefonda endirin.
2. Açın → «Quraşdır». İlk dəfə Android «naməlum mənbədən quraşdırma» üçün
   icazə istəyir - brauzerə (və ya fayl menecerinə) icazə verin.
3. Növbəti versiyalar tətbiqin özündə görünür: ekranın üstündə
   «Yeni versiya mövcuddur → Endir» zolağı.

Tətbiq Google Play-dən quraşdırılıbsa, yeniləmə Play-in öz mexanizmi ilə gəlir.

## Tətbiq yeniləməni necə tapır

Tətbiq 6 saatdan bir bu repo-nun `main` budağındakı `latest.json`-u oxuyur:

```json
{ "version": "1.0.4", "apk_url": "https://raw.githubusercontent.com/…/apk/FIXIT-Ticket-1.0.4.apk" }
```

`version` quraşdırılmışdan böyükdürsə, `apk_url` endirmə linki kimi göstərilir.

## Yeni reliz (tərtibatçı üçün)

1. Tətbiqin repo-sunda versiyanı artırın və imzalı APK yığın (`assembleRelease`).
2. Faylı `apk/FIXIT-Ticket-<versiya>.apk` kimi əlavə edin.
3. `latest.json`-da `version`, `version_code`, `apk_url`, `sha256`, `released`, `notes`-u yeniləyin.
4. Commit + push. Köhnə APK-ları silməyin - köhnə linklər işləməyə davam etsin.

Bütün APK-lar eyni açarla imzalanır (sertifikat SHA-256
`0A:E7:45:12:6C:2D:95:58:7E:2E:CD:CC:13:EF:ED:4C:8B:33:C7:E5:3F:0E:8C:F7:2B:B2:BB:CC:B5:2E:0C:66`).
Başqa açarla imzalanmış fayl quraşdırılmış tətbiqin üstünə yazılmır.
