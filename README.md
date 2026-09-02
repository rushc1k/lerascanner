# 🔍 LeraScanner v2.0.0 - Minecraft Ghost Client Detector

**Advanced Forensic Scanner** - JAR analizi, RAM tarama ve Windows Prefetch analizi ile Minecraft ghost clientlerini tespit edin!

## ⚡ Kurulum

### Yöntem 1: EXE İndirme (En Kolay) ⭐

```
1. GitHub Releases sayfasına git:
   https://github.com/rushc1k/lerascanner/releases

2. En son release'i bul

3. LeraScanner.exe'yi indir

4. Sağ tık → "Yönetici olarak çalıştır"

5. Menüden [0] seç - Otomatik Tam Tarama
```

**⚠️ Antivirüs Uyarısı:** Bazı AV'ler false positive verebilir. [Detaylı açıklama aşağıda](#️-virustotal-false-positive-uyarısı)

### Yöntem 2: Kaynak Koddan Çalıştırma

```bash
# 1. Projeyi indir
# Source code private - sadece EXE kullanın
cd lerascanner

# 2. Bağımlılıkları yükle
pip install -r requirements.txt

# 3. Çalıştır
python run.py
```

### Yöntem 3: Kendiniz EXE Derleyin

```bash
# 1. Projeyi indir
# Source code private - sadece EXE kullanın
cd lerascanner

# 2. Bağımlılıkları yükle
pip install -r requirements.txt
pip install pyinstaller

# 3. EXE oluştur
python build_exe.py

# 4. dist/LeraScanner.exe hazır!
```

## 🎯 Özellikler

### 1️⃣ JAR Dosyası Tarama
- JAR dosyalarını açıp içeriğini analiz eder
- Ghost client imzalarını tespit eder (Doomsday Client vb.)
- Hızlı ve doğru tespit

### 2️⃣ Sistem Çapında Tarama
- Bilgisayarınızdaki **tüm JAR dosyalarını** tarar
- `.minecraft/mods`, `Downloads`, `Desktop`
- CurseForge, MultiMC, PrismLauncher desteği

### 3️⃣ RAM Memory Tarama 🔥
- **Çalışan Java process'lerini** tarar
- RAM memory'de ghost client imzalarını arar
- Forensic-level memory analysis
- ⚠️ Admin yetkisi gerektirir

### 4️⃣ Windows Prefetch Analizi 🔥
- Windows Prefetch dosyalarını analiz eder
- **Geçmişte çalıştırılan JAR'ları** bulur
- Şüpheli dosya isimlerini tespit eder
- ⚠️ Admin yetkisi gerektirir

## 🚀 Kullanım

### 🔥 Otomatik Tam Tarama (ÖNERİLEN)

En kolay yöntem - her şeyi otomatik tarar:

```bash
python run.py
# Menüden [0] seçin
```

**Ne yapar?**
- ✅ Tüm sistemi otomatik tarar
- ✅ Her JAR'ın içindeki **her dosyayı** kontrol eder
- ✅ RAM memory'de ghost client arar
- ✅ Windows Prefetch geçmişini analiz eder
- ✅ Detaylı rapor ve kanıtlar gösterir

### Console Menü

```bash
python run.py
```

Program açıldığında interaktif menü göreceksiniz:

```
╔═══════════════════════════════════════════════════════════╗
║              🔍 LeraScanner v2.0.0                       ║
║         Minecraft Ghost Client Detector                  ║
║              Advanced Forensic Scanner                    ║
╚═══════════════════════════════════════════════════════════╝

[0] 🔥 OTOMATİK TAM TARAMA (ÖNERİLEN)
[1] JAR Dosyası Tara
[2] Sistem Çapında JAR Tara
[3] RAM Memory Tarama (Java Processes)
[4] Windows Prefetch Analizi
[5] Hakkında
[9] Çıkış
```

### Seçenek 1: JAR Dosyası Tara
Tek bir JAR dosyasını analiz edin:
- Dosya yolu girin
- Ghost client imzaları taranır
- Sonuç gösterilir

### Seçenek 2: Sistem Çapında Tarama
Bilgisayarınızdaki tüm JAR dosyalarını tarar:
- Otomatik lokasyon tespiti
- `.minecraft`, `Downloads`, `Desktop`
- Launcher klasörleri (CurseForge, MultiMC vb.)

### Seçenek 3: RAM Memory Tarama
Çalışan Minecraft'ı tarar:
- Java process'leri bulur
- Memory'de ghost client imzalarını arar
- ⚠️ **Yönetici olarak çalıştırın**

### Seçenek 4: Prefetch Analizi
Geçmiş JAR aktivitesini analiz eder:
- Windows Prefetch dosyalarını okur
- Geçmişte çalıştırılan JAR'ları bulur
- Şüpheli dosya isimleri tespit edilir
- ⚠️ **Yönetici olarak çalıştırın**

## ⚠️ Admin Yetkisi

RAM ve Prefetch özellikleri için:
1. Programı kapatın
2. Sağ tık → **"Yönetici olarak çalıştır"**
3. Tekrar açın

## 📊 Çıktı Örnekleri

### ✅ Temiz JAR
```
🔍 Taranıyor: optifine.jar

✅ TEMİZ - Ghost client bulunamadı
```

### ❌ Ghost Client Bulundu
```
⚠️  GHOST CLIENT TESPİT EDİLDİ!

🚨 Tespit edilen: Doomsday Client

Bulunan dosyalar:
  ├─ 0
  │  Yol: net/minecraft/0
  ├─ 1
  │  Yol: net/minecraft/1
  ├─ l.png
  │  Yol: assets/client/l.png
```

### 🧠 RAM Tarama
```
🔍 Java process'leri aranıyor...
✓ 1 Java process bulundu

Process: javaw.exe (PID: 12345)

🔍 Memory taranıyor...

⚠️  GHOST CLIENT TESPİT EDİLDİ!
   Process: javaw.exe (PID: 12345)
   Tespit sayısı: 3
```

### 📂 Prefetch Analizi
```
🔍 Prefetch dosyaları analiz ediliyor...

Java çalıştırma sayısı: 15
Bulunan JAR referansı: 47

⚠️  ŞÜPHELİ JAR'LAR BULUNDU:

• C:\Users\Rush\.minecraft\mods\doomsday-v2.jar
  Anahtar kelime: doomsday
  Prefetch: JAVAW.EXE-A1B2C3D4.pf
```

## 🔍 Tespit Metodolojisi

### JAR Analizi
- JAR dosyasını ZIP olarak açar
- İçindeki tüm dosyaları listeler
- Ghost client imzalarını arar (0, 1, l.png vb.)
- İmza detayları **gizlidir** - bypass edilemez

### RAM Memory Tarama
- Java process'lerini bulur (java.exe, javaw.exe)
- Process memory'sine erişir
- Byte-by-byte imza arama
- Runtime tespit - anlık hile kontrolü

### Prefetch Forensics
- `C:\Windows\Prefetch` klasörünü tarar
- Java execution history
- JAR file referansları
- Suspicious filename patterns

## 🛠️ Gereksinimler

- Windows 10/11
- Python 3.7+
- Bağımlılıklar:
  - `colorama` - Renkli console
  - `psutil` - Process management

## 📁 Proje Yapısı

```
lerascanner/
├── scanner/
│   ├── __init__.py
│   ├── jar_scanner.py        # JAR analiz motoru
│   ├── memory_scanner.py     # RAM tarama
│   ├── prefetch_scanner.py   # Prefetch analizi
│   ├── system_scanner.py     # Sistem tarama
│   ├── menu_cli.py          # Ana menü
│   └── cli.py               # Eski CLI (deprecated)
├── run.py                   # Ana çalıştırma dosyası
├── requirements.txt
├── setup.py
└── README.md
```

## 🔧 Geliştirme

### Yeni İmza Ekleme

`scanner/jar_scanner.py`:
```python
SUSPICIOUS_FILES = {
    '0': 'Doomsday Client',
    '1': 'Doomsday Client',
    'l.png': 'Doomsday Client',
    'newfile.dat': 'Another Client'  # Yeni imza
}
```

`scanner/memory_scanner.py`:
```python
SIGNATURES = [
    b'Doomsday',
    b'NewClient',  # Yeni imza
]
```

**Not:** İmza detaylarını public paylaşmayın!

## ⚠️ VirusTotal False Positive Uyarısı

### 🛡️ Antivirüs False Positive

LeraScanner'ın .exe versiyonu bazı antivirüsler tarafından **yanlış pozitif** (false positive) verebilir.

#### Neden False Positive Alınır?

1. **Memory Okuma API'leri**
   - `ReadProcessMemory`, `VirtualQueryEx` gibi Windows API'leri kullanır
   - Bu API'ler malware'ler tarafından da kullanıldığından şüpheli görünür
   - Forensic araçlar ve debugger'lar da aynı API'leri kullanır

2. **Process Enumeration**
   - Çalışan process'leri listelemek
   - Process handle'larına erişim
   - Antivirüsler bunu "process injection" olarak algılayabilir

3. **Admin Yetkisi Talebi**
   - Program admin yetkisi ister
   - Bu davranış bazı AV'ler için red flag

4. **PyInstaller Kullanımı**
   - Python scriptleri .exe'ye dönüştürüldüğünde
   - Bazı AV'ler otomatik olarak şüpheli görür

#### Güvenlik Doğrulaması

✅ **Kaynak Kodu Açık**: Tüm kod GitHub'da görülebilir
✅ **Kendi Build Edebilirsiniz**: `build_exe.py` ile kendiniz derleyin
✅ **Zararlı Kod Yok**: Memory'yi sadece okur, yazmaz
✅ **Veri Gönderimi Yok**: İnternet bağlantısı gerektirmez
✅ **Local İşlem**: Tüm analiz bilgisayarınızda gerçekleşir

#### VirusTotal'da Ne Görürsünüz?

Muhtemel tespit nedenleri:
- "Generic", "Heuristic", "AI Detection"
- "Suspicious behavior: memory access"
- "PUA" (Potentially Unwanted Application)
- "Obfuscated code" (PyInstaller nedeniyle)

#### Nasıl Doğrularsınız?

1. **Kaynak Kodunu İnceleyin**
   ```bash
   # GitHub'dan indirin ve okuyun
   # Source code private - sadece EXE kullanın
   # Tüm Python dosyalarını inceleyin
   ```

2. **Kendiniz Derleyin**
   ```bash
   pip install pyinstaller
   python build_exe.py
   ```

3. **Sandbox'ta Test Edin**
   - Any.run, Joe Sandbox gibi servislerde test edin
   - Zararlı davranış görmeyeceksiniz

#### Güvenlik Önerileri

⚠️ **Sadece Resmi Kaynaktan İndirin**
- GitHub: https://github.com/rushc1k/lerascanner
- Başka kaynaklardan **ASLA** indirmeyin

⚠️ **Hash Kontrolü**
- İndirilen .exe'nin hash'ini kontrol edin
- Releases sayfasında hash değerleri verilir

---

## 📝 Lisans

Bu proje eğitim ve güvenlik araştırması amaçlıdır. Kötüye kullanımdan kullanıcı sorumludur.

## 🤝 Katkıda Bulunma

1. Fork edin
2. Feature branch oluşturun
3. Commit yapın
4. Push edin
5. Pull Request açın

## 📧 İletişim

- GitHub: https://github.com/rushc1k/lerascanner
- Issues: https://github.com/rushc1k/lerascanner/issues

---

**⚡ LeraScanner v2.0.0** - Advanced Minecraft Ghost Client Detector 🛡️

Made with ❤️ by rushc1k
