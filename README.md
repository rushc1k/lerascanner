# 🔍 LeraScanner - Minecraft Ghost Client Detector

**Tek Tıkla Otomatik Ghost Client Tespiti**

## ⚡ Hızlı Kullanım

```
1. LeraScanner.exe'yi indirin
2. Sağ tık → "Yönetici olarak çalıştır"
3. Enter'a basın
4. Bekleyin (otomatik tarama)
5. Sonuçları görün
```

Program otomatik olarak **TÜM SİSTEMİ** tarar:
- ✅ Bilgisayarınızdaki tüm JAR dosyaları
- ✅ RAM memory (çalışan Minecraft)
- ✅ Windows Prefetch geçmişi

Ghost client bulunursa **dosya yolu ile gösterir**.

---

## 📦 İndirme

### Yöntem 1: Direkt İndirme
Yukarıdaki **LeraScanner.exe** dosyasına tıklayın → **Download** butonuna basın

### Yöntem 2: Releases (Önerilir)
**[Releases](https://github.com/rushc1k/lerascanner/releases)** sayfasından en son versiyonu indirin

---

## 🎯 Ne Yapar?

### Otomatik Tarama
Program açılır açılmaz otomatik olarak şunları tarar:

#### 1️⃣ JAR Dosyaları (Derin Tarama)
**TÜM BİLGİSAYARINIZI** tarar - her disk, her klasör:
- ✅ **Tüm diskler** (C:, D:, E:, vb.)
- ✅ **Tüm klasörler** (sistem klasörleri hariç)
- ✅ **Her JAR dosyası** nerede olursa olsun
- ✅ **Derin analiz** - JAR içindeki her dosyayı kontrol eder
- ✅ **Progress bar** - Ne kadar tamamlandığını gösterir

```
[████████████░░░░░] 45.2% (23/51) mod-file.jar
```

Program **hiçbir yeri atlamaz** - gizlenmiş JAR'ları bile bulur!

#### 2️⃣ RAM Memory Tarama
Çalışan Java process'lerinde ghost client arar:
- Aktif Minecraft varsa memory'sini tarar
- Runtime tespit (şu an çalışıyor mu?)
- Forensic-level analiz

#### 3️⃣ Windows Prefetch Analizi
Geçmişte çalıştırılan şüpheli JAR'ları bulur:
- Silinmiş dosyaları bile tespit eder
- Forensic timeline analizi
- Geçmiş aktivite kayıtları

---

## 📊 Çıktı Örnekleri

### ✅ Sistem Temiz

```
======================================================================
🔍 LERASCANNER - Minecraft Ghost Client Detector
======================================================================

Sistem otomatik olarak taranıyor...

⏳ JAR dosyaları taranıyor...
✓ JAR tarama tamamlandı

⏳ RAM memory taranıyor...
✓ RAM tarama tamamlandı

⏳ Prefetch analiz ediliyor...
✓ Prefetch analizi tamamlandı

======================================================================
TARAMA TAMAMLANDI
======================================================================

Süre: 12.3 saniye
Zaman: 2026-09-02 14:25:30

======================================================================
✅ SİSTEM TEMİZ
======================================================================

Hiçbir ghost client tespit edilmedi.

Çıkmak için Enter'a basın...
```

---

### ❌ Ghost Client Bulundu!

```
======================================================================
🔍 LERASCANNER - Minecraft Ghost Client Detector
======================================================================

Sistem otomatik olarak taranıyor...

⏳ JAR dosyaları taranıyor...
✓ JAR tarama tamamlandı

⏳ RAM memory taranıyor...
✓ RAM tarama tamamlandı

⏳ Prefetch analiz ediliyor...
✓ Prefetch analizi tamamlandı

======================================================================
TARAMA TAMAMLANDI
======================================================================

Süre: 15.7 saniye
Zaman: 2026-09-02 14:28:45

======================================================================
⚠️  GHOST CLIENT TESPİT EDİLDİ!
======================================================================

Toplam tespit: 3

KANITLAR (DOSYA YOLLARI):

[1] JAR TESPİTİ:
   📦 JAR Dosyası:
   C:\Users\Rush\.minecraft\mods\doomsday-client-v2.jar
   Kanıtlar:
      • net/minecraft/0
      • net/minecraft/1  
      • assets/client/l.png

[2] MEMORY TESPİTİ:
   🧠 RAM Memory:
   Process: javaw.exe (PID: 12345)
   Tespit sayısı: 3

[3] PREFETCH TESPİTİ:
   📂 Prefetch Geçmişi:
   C:\Users\Rush\Downloads\suspicious-mod.jar

Çıkmak için Enter'a basın...
```

**Bu dosyaları derhal silin!**

---

## ⚠️ Önemli Notlar

### 🛡️ Admin Yetkisi Gerekli

Program **"Yönetici olarak çalıştır"** ile açılmalıdır.

**Neden?**
- RAM memory okuma yetkisi
- Windows Prefetch erişimi
- Sistem klasörlerindeki JAR'lara erişim

**Nasıl?**
```
LeraScanner.exe'ye sağ tık → "Yönetici olarak çalıştır"
```

---

### ⚠️ Antivirüs Uyarısı (False Positive)

**UYARI: Antivirüsler bu programı şüpheli görebilir!**

Bu **NORMALDIR** ve program **GÜVENLİDİR**.

#### Neden Antivirüs Uyarı Veriyor?

1. **Memory Okuma API'leri**
   - Program RAM memory'yi okur
   - Bu API'leri malware'ler de kullanır
   - Forensic araçlar ve debugger'lar da aynı şeyi yapar

2. **Process Enumeration**
   - Çalışan programları listeler
   - Antivirüsler bunu şüpheli bulabilir

3. **Admin Yetkisi İster**
   - Yüksek yetki talebi
   - Bazı AV'ler için red flag

4. **Derlenmiş Program**
   - Python → EXE dönüşümü
   - Bazı antivirüsler otomatik şüpheli görür

#### Program Güvenli mi?

✅ **EVET! %100 Güvenli**

Program:
- ✅ Sadece **okur**, asla yazmaz
- ✅ İnternete **bağlanmaz**
- ✅ Hiçbir veri **göndermez**
- ✅ Zararlı kod **yok**
- ✅ Sadece **analiz** yapar

#### Ne Yapmalıyım?

**Seçenek 1: Antivirüsü Geçici Kapat**
```
1. Antivirüs'ü geçici olarak devre dışı bırak
2. LeraScanner'ı çalıştır
3. Antivirüs'ü tekrar aç
```

**Seçenek 2: İstisna Ekle**
```
Antivirüs ayarları → İstisnalar → LeraScanner.exe ekle
```

**Seçenek 3: Güven ve Çalıştır**
```
Uyarıyı görmezden gel ve "Allow" / "İzin Ver" tıkla
```

#### VirusTotal'da Ne Görürsünüz?

Muhtemel tespit isimleri:
- "Generic.Trojan"
- "Heur.Suspicious"
- "PUA.Tool"
- "Win32.Hacktool"

**Bu isimler korkutucu ama YANLIŞ POZİTİF!**

---

### 🔐 Hash Doğrulama

İndirdiğiniz dosyanın orijinal olduğunu doğrulayın:

```powershell
# PowerShell'de çalıştır:
Get-FileHash -Path LeraScanner.exe -Algorithm SHA256
```

**Beklenen Hash:**
```
8F96C3A937239935114A5785F5D4346ED73A16B2DF6BB6F506B4C17020DCE2D1
```

Eşleşiyorsa → ✅ Orijinal dosya  
Eşleşmiyorsa → ⚠️ Dosya değiştirilmiş, indirmeyin!

---

## 🔍 Ne Aranıyor?

Program **gizli imzalar** kullanır. İmza detayları **paylaşılmaz** çünkü:
- ✅ Client geliştiricileri bypass edemez
- ✅ Daha etkili tespit
- ✅ Güvenlik açığı oluşturmaz

**Tespit Edilen Clientler:**
- Doomsday Client
- *(Diğer clientler için imzalar ekleniyor)*

---

## ❓ Sık Sorulan Sorular

**S: Neden admin gerekiyor?**  
C: RAM okuma ve Prefetch erişimi Windows admin yetkisi gerektirir.

**S: İnternete bağlanıyor mu?**  
C: Hayır, tamamen offline çalışır.

**S: Veri topluyor mu?**  
C: Hayır, hiçbir şey göndermiyor.

**S: Yanlış pozitif olabilir mi?**  
C: Çok nadir. İmzalar çok spesifik.

**S: Ne kadar sürer?**  
C: 10-30 saniye (bilgisayara ve JAR sayısına bağlı).

**S: Minecraft açıkken mi taranmalı?**  
C: RAM taraması için evet ama JAR taraması için gerekli değil.

**S: Source code nerede?**  
C: Source code kapalı. Sadece EXE dağıtılıyor.

**S: Neden source code yok?**  
C: Client geliştiricileri imzaları göremez, bypass edemez.

**S: Güvenilir mi?**  
C: Evet! Antivirüs false positive veriyor ama program tamamen güvenli.

---

## 🛡️ Gizlilik

- ✅ Hiçbir veri internete gönderilmez
- ✅ Tamamen lokal çalışır  
- ✅ Log dosyası oluşturmaz
- ✅ Kişisel bilgi toplamaz
- ✅ Verileriniz güvende

---

## ⚙️ Sistem Gereksinimleri

- **İşletim Sistemi:** Windows 10/11
- **Yetki:** Administrator (Yönetici)
- **RAM:** Minimum 2GB
- **Disk:** 10MB boş alan
- **İnternet:** Gerekli değil (offline çalışır)

---

## 📝 Sorumluluk Reddi

Bu araç **eğitim ve güvenlik** amaçlıdır.

- ✅ Kendi bilgisayarınızı taramak için kullanabilirsiniz
- ❌ Başkasının bilgisayarını izinsiz taramak yasadışıdır
- ⚠️ Kötüye kullanımdan **kullanıcı sorumludur**

---

## 📧 Destek

Sorular için **[GitHub Issues](https://github.com/rushc1k/lerascanner/issues)** açın.

**NOT:** Source code paylaşılmadığı için kod hakkında soru yanıtlanmaz.

---

## 🎯 Özet

1. ⬇️ **LeraScanner.exe'yi indirin**
2. 🛡️ **Yönetici olarak çalıştırın**
3. ⌨️ **Enter'a basın**
4. ⏳ **Bekleyin (otomatik tarama)**
5. ✅ **Sonuçları görün**

Ghost client bulunursa **dosya yollarını gösterir** - derhal silin!

---

**⚡ LeraScanner** - Tek tıkla ghost client tespiti! 🛡️

Made with ❤️ by rushc1k

**Version:** 1.3  
**Release Date:** September 2026  
**SHA256:** 8F96C3A937239935114A5785F5D4346ED73A16B2DF6BB6F506B4C17020DCE2D1
