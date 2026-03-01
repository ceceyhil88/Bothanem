# TheMicrobot Nedir?

## Genel Bakış

**TheMicrobot**, Old School RuneScape (OSRS) oyunu için geliştirilmiş otomatik oyun botudur. Bu proje, oyun içi görevleri otomatikleştirerek zaman kazanmanızı ve tekrarlayan işlemleri kolaylaştırmanızı sağlar.

## Microbot'lar Tam Olarak Nedir?

Microbot'lar, OSRS gibi oyunlarda belirli görevleri otomatik olarak gerçekleştiren yazılım programlarıdır. Bu botlar:

1. **Oyun İçi Eylemleri Otomatikleştirir**: Tekrarlayan görevleri (mining, fishing, trading) sizin yerinize yapar
2. **Akıllı Karar Verme**: Oyun durumuna göre dinamik kararlar alabilir
3. **İnsan Benzeri Davranış**: Tespit edilmemek için rastgele gecikmeler ve hareketler kullanır
4. **Çoklu Profil Desteği**: Farklı karakterler için farklı yapılandırmalar

## Bu Projenin Botları

Bu projede **iki tip bot** bulunmaktadır:

### 1. MULE (Katır) Botu
- **Görev**: GP (Gold Piece) ve eşya transferi
- **İşlev**: Worker botlardan altın toplayıp güvenli bir yerde saklar
- **Kullanım**: Ana hesabınızı riskten korumak için

### 2. WORKER (İşçi) Botu  
- **Görev**: Para kazanma aktiviteleri
- **İşlev**: Çeşitli yöntemlerle GP toplar (mining, crafting, trading)
- **Kullanım**: Aktif olarak oyunda para kazanmak için

## Microbot'ların Avantajları

### ✅ Zaman Tasarrufu
- 7/24 oyunda kalabilir ve size çalışırken para kazanır
- Tekrarlayan görevlerde saatlerce vakit harcamanıza gerek kalmaz

### ✅ Verimlilik
- İnsan hatası yapmaz
- Sürekli aynı hızda ve doğrulukta çalışır
- Yorulmaz, konsantrasyon kaybı yaşamaz

### ✅ Çoklu Hesap Yönetimi
- Aynı anda birden fazla bot çalıştırabilirsiniz
- Her bot farklı görevlerde çalışabilir
- Merkezi yönetim ve kontrol

### ✅ Esnek Yapılandırma
- Proxy desteği (her hesap farklı IP)
- Özelleştirilebilir parametreler
- Profil bazlı ayarlar

### ✅ Gelişmiş Özellikler
- Grand Exchange (GE) otomasyonu
- Banka yönetimi
- Trade (ticaret) sistemi
- World hopping (dünya değiştirme)
- Overlay (ekran üstü bilgi gösterimi)

## Teknik Özellikler

### Platform
- **DreamBot Framework**: 3.30.48.1 sürümü
- **Java**: 17+ gerektirir
- **İşletim Sistemi**: Windows 11 optimize edilmiş

### Temel Özellikler

#### 1. Banka Yönetimi
```
- Hassas coin çekme/yatırma
- Otomatik noted (not edilmiş) item yönetimi
- Akıllı envanter kontrolü
```

#### 2. Grand Exchange (GE)
```
- Otomatik alım/satım
- Batch (toplu) işlem desteği
- Sipariş iptali ve toplama
```

#### 3. Trade Sistemi
```
- Güvenli ticaret protokolü
- İki aşamalı doğrulama
- Queue (kuyruk) yönetimi
```

#### 4. World Hopping
```
- P2P (Premium) dünya desteği
- Rate limit koruması
- Tercih edilen dünyalar: 383, 455
```

## Kullanım Örnekleri

### MULE Botu Başlatma
```bash
-params profile=m1 role=MULE nogui=1
```

### WORKER Botu Başlatma
```bash
-params profile=w1 role=WORKER nogui=1
```

### Proxy ile Kullanım
```bash
-proxyHost 192.168.1.100 -proxyPort 8080 -proxyUser kullanici -proxyPass sifre
```

## Güvenlik ve Risk Yönetimi

### ⚠️ Riskler
- Jagex (OSRS yapımcısı) bot kullanımını yasaklar
- Hesap ban riski mevcuttur
- Bu botları kullanmak kendi sorumluluğunuzdadır

### 🛡️ Güvenlik Önlemleri
- Proxy kullanarak IP çeşitliliği sağlayın
- MULE botları ana hesaplarınızdan ayrı tutun
- İnsan benzeri davranış ayarlarını kullanın
- Aşırı aktiviteden kaçının

## Overlay (Ekran Bilgisi)

Bot çalışırken ekranda gösterilen bilgiler:
- **Total GP**: Toplam altın miktarı (envanter + banka)
- **Format**: K/M formatında (1000 = 1K, 1000000 = 1M)
- **Güncelleme**: Banka yakınında her 10 saniyede bir

Örnek: `Total GP: 2.5M`

## Log Sistemi

Bot aktiviteleri şu etiketlerle loglanır:
- `[BANK]`: Banka işlemleri
- `[GE]`: Grand Exchange işlemleri
- `[TRADE]`: Ticaret işlemleri
- `[HOP]`: Dünya değiştirme
- `[QS]`: QuickStart (hızlı başlatma)
- `[OVERLAY]`: Ekran overlay bilgileri

## Sonuç

Bu proje, OSRS için tam özellikli bir microbot sistemidir. İki ana bot tipi (MULE ve WORKER) ile güvenli ve verimli bir şekilde oyunda ilerleme sağlar. Ancak, bot kullanımının oyun kurallarına aykırı olduğunu ve risk taşıdığını unutmayın.

## Ek Kaynaklar

- **KnowledgeBase.md**: Detaylı teknik dokümantasyon ve hata çözümleri
- **project-profile.json**: Yapılandırma parametreleri ve politikalar

---

*Not: Bu yazılım eğitim amaçlıdır. Kullanımdan doğacak sorumluluk kullanıcıya aittir.*
