# Knowledge Base
<!-- AUTO-UPDATE-TIMESTAMP --> Last auto check: 2025-12-29 05:09:25 UTC

Bu dosya, tüm script geliştirme sürecinde öğrendiğimiz kalıpları, hataları ve çözümleri kalıcı olarak saklar. Operasyonel kurallar ve parametreler için `project-profile.json` kullanılır.

## Çalışma Kuralları
- Sorun çözümü: Tek atımlık patch + kısa kabul kriteri + 1 küçük test. Başarısızsa sadece tek ölçüm ekleyip final patch.
- Log etiketleri: [BANK], [GE], [TRADE], [HOP], [QS], [OVERLAY]

## Ortam
- DreamBot: 3.30.48.1
- Java: 17+
- OS: Windows 11
- QuickStart örnekleri:
  - `-params profile=m1 role=MULE nogui=1`
  - `-params profile=w1 role=WORKER nogui=1`
- Proxy: `-proxyHost ... -proxyPort ... [-proxyUser ... -proxyPass ...]`

## Bank Kalıpları (Coins exact, UI’siz)
- Öncelik: `Bank.withdraw("Coins", need)`; 2.5s içinde inv artmazsa fallback:
- Fallback (hızlı/sağlam): `withdrawAll("Coins")` → `deposit(diff)`
- Noted: Coins için `false`
- Her aksiyon sonrası `sleepUntil(inv/bank değişimi, <=2500ms)`
- Yaygın hata: “Bank does not have an interact call for X” → Çözüm: UI “Withdraw-X” yok, sadece Bank API

## GE Kalıpları
- `open → cancelAll → buy/sell → collect → close`
- Batch akışı ve `sleepUntil(widget/state, 2-5s)`

## Trade Kalıpları
- Bankta exact hazırlık → Trade’de minimal etkileşim (Coins Offer-All)
- 1. ekran doğrula → accept1 → 2. ekran doğrula → accept2
- Sıra/queue dışında gelen isteği reddet

## World Hop
- `hop(int)` → `sleepUntil(currentWorld==target, 20s)`
- Rate-limit: ≥10s; başarısızsa tek retry

## Widget/Dialog/Welcome
- “CLICK HERE TO PLAY” bypass
- Prompt/focus kontrolleri; metin `contains` ile seçim

## QuickStart/Proxy
- `-params` sadece bir kez, son argüman
- Proxy bayrakları ayrı kullanılır

## Overlay/Telemetri
- Tek satır Total GP (inv+bank) K/M
- Banka yakınında 10s’de bir probe open/read/close

## Hata/Çözüm Arşivi (Örnekler)
- [BANK] UI Withdraw-X hatası → Bank API-only; withdrawAll + deposit(diff)
- [GE] Collect stuck → `collect()` sonrası `sleepUntil(inv/bank değişimi)`; gerekirse `close()` tekrar aç

## Karar Kayıtları (ADR)
- ADR-001: Coins exact için withdrawAll+deposit(diff) fallback zorunlu
- ADR-002: Overlay’de toplam GP tek satır, K/M format
