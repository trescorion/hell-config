# HELLDESK — canlı denge config'i

`balance.json` oyunun uzaktan ayarlanan sayılarıdır (KOD-05). Uygulama her
açılışta arka planda çeker, doğrular, cache'ler; geçersiz/eski-şemalı config
sessizce yok sayılır (gömülü varsayılan `Balance.standard` ana repoda, kodda yaşar).

Kurallar:

- Her değişiklikte `version` alanını 1 artır (oyunda Settings'te "Config vN" görünür).
- Yalnız SAYILAR değişir — davranış/şema değişikliği kod + build ister
  (`schema` alanı ana repodaki `Balance.currentSchema` ile eşleşmek zorunda).
- `minBuild`: bu build numarasından eski build'ler config'i yok sayar.
- Raw URL ~5 dk CDN cache'lidir; telefonda görmek için commit sonrası oyunu
  kapat-aç ya da Settings → Reload.
