# Dünya Ambalaj – Fuar Tahsilat Sistemi

## Kullanım ve Kurulum Kılavuzu

---

## 📌 İçindekiler

1. [Giriş Yapma](#1-giriş-yapma)
2. [Kullanıcı Rolleri ve Yetkiler](#2-kullanıcı-rolleri-ve-yetkiler)
3. [Sekmeler](#3-sekmeler)
4. [Müşteri Kayıtları (Müşteriler Sekmesi)](#4-müşteri-kayıtları)
5. [Yeni Kayıt Ekleme](#5-yeni-kayıt-ekleme)
6. [Filtreleme ve Arama](#6-filtreleme-ve-arama)
7. [Tablo Görünümü](#7-tablo-görünümü)
8. [Toplu İşlemler](#8-toplu-işlemler)
9. [Müşteri Detay Ekranı](#9-müşteri-detay-ekranı)
10. [Bildiri ve Dışa Aktarma](#10-bildiri-ve-dışa-aktarma)
11. [Excel İçe / Dışa Aktarma](#11-excel-içe--dışa-aktarma)
12. [Kullanıcı Yönetimi](#12-kullanıcı-yönetimi)
13. [Temsilci Eşleştirmesi](#13-temsilci-eşleştirmesi)
14. [Firebase Kurulumu](#14-firebase-kurulumu)
15. [Sık Sorulan Sorular](#15-sık-sorulan-sorular)

---

## 1. Giriş Yapma

Sistem şifre ile çalışır. E-posta veya kullanıcı adı gerekmez.

- Giriş ekranında şifrenizi girin ve **Giriş Yap** butonuna tıklayın (veya Enter tuşuna basın).
- Varsayılan admin şifresi: **`8554`**
- Tarayıcı sekmesi kapatılana kadar oturum açık kalır.
- Sayfa yenilendiğinde tekrar şifre girmenize gerek yoktur.

> ⚠️ **Önemli:** İlk girişten sonra admin şifresini değiştirmeniz önerilir.

---

## 2. Kullanıcı Rolleri ve Yetkiler

Sistemde iki rol vardır: **Admin** ve **Kullanıcı**.

| Özellik | Admin | Kullanıcı |
|---------|:-----:|:---------:|
| Müşteriler sekmesi | ✅ Tüm veriler | ✅ Sadece atanmış temsilcinin verileri |
| Firmalar sekmesi | ✅ | ❌ |
| Temsilciler sekmesi | ✅ | ❌ |
| Kurulum sekmesi | ✅ | ❌ |
| Kullanıcılar sekmesi | ✅ | ❌ |
| Yeni kayıt ekleme (+ Yeni) | ✅ | ❌ |
| Excel içe aktarma | ✅ | ❌ |
| Excel dışa aktarma | ✅ Tüm veriler | ✅ Sadece kendi verileri |
| İstatistikler | ✅ Tüm veriler | ✅ Sadece kendi verileri |

---

## 3. Sekmeler

| Sekme | Açıklama |
|-------|----------|
| 📋 **Müşteriler** | Tüm satın alım kayıtlarını listeler. Filtreleme, sıralama, toplu işlem yapılabilir. |
| 🏢 **Firmalar** | Firmaları kart görünümünde gösterir. Her firmanın müşteri sayısı ve toplam tutarı görünür. |
| 👤 **Temsilciler** | Temsilcileri kart görünümünde gösterir. Her temsilcinin müşteri/firma dağılımı görünür. |
| ⚙ **Kurulum** | Firebase bağlantı ayarları. Özel Firebase projesi bağlamak için kullanılır. |
| 👥 **Kullanıcılar** | Kullanıcı ekleme, silme, rol değiştirme, şifre sıfırlama ve temsilci atama. |

> Giriş yapıldığında her zaman **Müşteriler** sekmesi açılır.

---

## 4. Müşteri Kayıtları

Ekranın üst kısmında 6 istatistik kartı gösterilir:

| Kart | Açıklama |
|------|----------|
| **Müşteri** | Toplam benzersiz müşteri sayısı |
| **Toplam** | Tüm kayıtların tutar toplamı |
| **Tahsil** | "Ödeme Tamamlandı" durumundaki kayıtların toplamı |
| **Bekleyen** | "Tahsilat Bekliyor" durumundaki kayıtların toplamı |
| **Firma** | Toplam benzersiz firma sayısı |
| **Temsilci** | Toplam benzersiz temsilci sayısı |

> Kullanıcı rolündeki kişiler yalnızca kendilerine atanmış temsilcinin verilerini görür.

---

## 5. Yeni Kayıt Ekleme

**+ Yeni** butonuna tıklayarak yeni kayıt ekleyebilirsiniz (sadece admin).

| Alan | Zorunlu | Açıklama |
|------|:-------:|----------|
| Müşteri Adı | ✅ | Müşterinin adı soyadı |
| Müşteri Kodu | – | Cari numara veya kod |
| Firma Adı | ✅ | Daha önce girilen firmalar otomatik tamamlanır |
| Temsilci | – | Daha önce girilen temsilciler otomatik tamamlanır |
| Tutar (₺) | – | Satın alma tutarı |
| İl | – | Türkiye'nin 81 ili listeden seçilebilir |
| İlçe | – | Serbest metin |
| Ödeme Durumu | – | Tahsilat Bekliyor / Ödeme Tamamlandı / İptal |
| Tarih | – | Varsayılan: bugünün tarihi |
| Notlar | – | Ek bilgi alanı |

---

## 6. Filtreleme ve Arama

Müşteriler sekmesinde birden fazla filtre birlikte kullanılabilir:

- **🔍 Arama kutusu:** Müşteri, firma, temsilci veya il adına göre arar. Büyük/küçük harf ve Türkçe karakter farkı dikkate alınmaz.
- **Firma filtresi:** Açılır listeden firma seçin.
- **Temsilci filtresi:** Açılır listeden temsilci seçin.
- **Durum filtresi:** Tahsilat Bekliyor / Ödeme Tamamlandı / İptal.
- **İl filtresi:** Açılır listeden il seçin.

Tablo sütun başlıklarına tıklayarak **sıralama** yapabilirsiniz (A→Z / Z→A veya küçükten büyüğe).

---

## 7. Tablo Görünümü

### Masaüstü

İki görünüm modu vardır:

**Müşteri Bazlı Gruplama** (varsayılan – checkbox işaretli):
- Aynı müşteriye ait kayıtlar tek satırda gruplanır.
- Alım sayısı, firma sayısı, toplam tutar ve bekleyen tutar gösterilir.
- Firma sütunu gizlenir (tasarım uyumu için).
- Grup durumu tek seferde değiştirilebilir.

**Düz Liste** (checkbox kaldırıldığında):
- Her kayıt ayrı satırda gösterilir.
- Firma sütunu görünür.
- Her kayıt için düzenle (✏), bildiri (📸) ve sil (✕) butonları bulunur.

### Mobil

700px altı ekranlarda otomatik olarak **kart görünümüne** geçilir:
- Müşteri adı, firma, tutar ve durum bilgisi kart içinde gösterilir.
- Karta tıklayarak müşteri detayına erişilir.

---

## 8. Toplu İşlemler

Tablodan birden fazla kayıt seçerek toplu işlem yapabilirsiniz:

1. Satırların solundaki checkbox'ları işaretleyin (veya "Tümünü Seç" ile hepsini seçin).
2. Üstte beliren işlem çubuğundan:
   - **⏹ Tümünü İptal Et:** Seçili kayıtların durumunu "İptal" yapar.
   - **🗑 Tümünü Sil:** Seçili kayıtları kalıcı olarak siler (geri alınamaz).
   - **✕ Seçimi Kaldır:** Seçimi temizler.

---

## 9. Müşteri Detay Ekranı

Bir müşteriye tıkladığınızda detay ekranı açılır:

- **Satın alınan firmalar listesi:** Her firma için tutar ve ödeme durumu gösterilir.
- **Genel toplam:** Tüm firmaların toplam tutarı.
- **Tahsilat bekliyor:** Bekleyen tutar (varsa).
- **✓ Tahsil Et:** Bir firmanın tüm bekleyen kayıtlarını "Ödeme Tamamlandı" yapar.
- **📸 Bildiri Oluştur:** Müşteriye ait bildiri oluşturur (JPEG/PDF/WhatsApp).

---

## 10. Bildiri ve Dışa Aktarma

Bildiri ekranından üç seçenek sunulur:

| Seçenek | Açıklama |
|---------|----------|
| **📥 JPEG İndir** | Bildiriyi yüksek kaliteli görsel olarak indirir |
| **📄 PDF İndir** | A4 formatında profesyonel PDF oluşturur (logo + firma detayları + özet) |
| **🟢 WhatsApp Paylaş** | Bildiri özetini WhatsApp üzerinden paylaşır |

---

## 11. Excel İçe / Dışa Aktarma

### İçe Aktarma (sadece admin)

1. Üst menüden **📥 Excel** butonuna tıklayın.
2. `.xlsx`, `.xls` veya `.csv` dosyası seçin.
3. Sistem sütun adlarını otomatik eşler.

**Otomatik tanınan sütun adları:**

| Kaynak sütun (Excel'deki) | Eşlendiği alan |
|--------------------------|----------------|
| Müşteri, Ad, İsim, Ad Soyad | Müşteri Adı |
| Firma, Firma Adı | Firma Adı |
| Temsilci, Müşteri Temsilcisi | Temsilci |
| İl, Şehir | İl |
| İlçe | İlçe |
| Tutar, Fiyat, Satış, Miktar | Tutar |
| Durum, Ödeme Durumu | Ödeme Durumu |
| Tarih, Date | Tarih |
| Notlar, Not, Açıklama | Notlar |
| Cari No, Müşteri Kodu, Kod | Müşteri Kodu |

> Sütun adlarındaki büyük/küçük harf, boşluk ve Türkçe karakter farkları otomatik düzeltilir.

### Dışa Aktarma

- **📤 Dışa Aktar** butonuna tıklayın.
- Dosya adı: `dunya_ambalaj_fuar_[TARİH].xlsx`
- Admin tüm verileri, kullanıcı sadece kendi temsilci verilerini dışa aktarır.

---

## 12. Kullanıcı Yönetimi

**Kullanıcılar** sekmesinden (sadece admin erişebilir):

### Yeni Kullanıcı Ekleme

1. **+ Yeni Kullanıcı** butonuna tıklayın.
2. Alanları doldurun:
   - **Ad:** Kullanıcının görünen adı
   - **Şifre:** Giriş şifresi (SHA-256 ile şifrelenerek saklanır)
   - **Rol:** `admin` veya `user`
   - **Temsilci:** Kullanıcıya atanacak temsilci adı (mevcut temsilciler listeden seçilebilir)
3. **Ekle** butonuna tıklayın.

### Mevcut Kullanıcı İşlemleri

Her kullanıcı satırında:

| İşlem | Açıklama |
|-------|----------|
| **Rol değiştir** | Açılır listeden `admin` veya `user` seçin |
| **Temsilci değiştir** | Açılır listeden temsilci atayın |
| **🔑 Şifre Sıfırla** | Yeni şifre girin, onaylayın |
| **🗑 Sil** | Kullanıcıyı kalıcı olarak siler (onay gerekir) |

---

## 13. Temsilci Eşleştirmesi

Temsilci eşleştirmesi, kullanıcıların yalnızca belirli bir temsilciye ait verileri görmesini sağlar.

### Nasıl Çalışır?

1. Admin, **Kullanıcılar** sekmesinden bir kullanıcıya temsilci atar.
2. O kullanıcı giriş yaptığında:
   - Sadece **Müşteriler** sekmesini görür.
   - Tabloda yalnızca atanmış temsilcinin kayıtları listelenir.
   - İstatistikler yalnızca kendi verilerini yansıtır.
   - Filtre seçenekleri (firma, temsilci, il) yalnızca kendi verilerine göre doldurulur.
   - Excel dışa aktarma yalnızca kendi verilerini içerir.

### Örnek Senaryo

> **Ahmet** adlı kullanıcıya **"Mehmet Yılmaz"** temsilcisi atandı.  
> Ahmet giriş yaptığında yalnızca Mehmet Yılmaz'ın müşteri kayıtlarını görür.  
> Diğer temsilcilerin kayıtları tabloda, istatistiklerde ve filtrelerde yer almaz.

---

## 14. Firebase Kurulumu

Sistem verileri **Firebase Firestore** veritabanında saklar.

### Varsayılan Bağlantı

Sistem önceden yapılandırılmış bir Firebase projesine bağlıdır. Ekstra ayar gerektirmez.

### Özel Firebase Projesi Bağlama

Kendi Firebase projenizi kullanmak istiyorsanız:

1. [Firebase Console](https://console.firebase.google.com/) adresinden yeni proje oluşturun.
2. **Firestore Database** oluşturun.
3. Proje ayarlarından web uygulaması ekleyin ve yapılandırma bilgilerini alın.
4. Uygulamada **⚙ Kurulum** sekmesine gidin.
5. Alanları doldurun:

| Alan | Açıklama |
|------|----------|
| API Key | Firebase API anahtarı |
| Auth Domain | `[proje-id].firebaseapp.com` |
| Project ID | Firebase proje kimliği |
| Storage Bucket | `[proje-id].firebasestorage.app` |
| Messaging Sender ID | Bulut mesajlaşma gönderen kimliği |
| App ID | Uygulama kimliği |

6. **Kaydet** butonuna tıklayın.

> Varsayılana dönmek için **Varsayılana Dön** butonunu kullanın.

### Firestore Güvenlik Kuralları

Firebase Console'da Firestore kurallarını aşağıdaki gibi ayarlayın:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

> ⚠️ Bu kurallar herkesin okuma/yazma yapmasına izin verir. Üretim ortamında daha kısıtlayıcı kurallar kullanmanız önerilir.

### Firestore Koleksiyonları

| Koleksiyon | Açıklama |
|------------|----------|
| `kayitlar` | Müşteri satın alım kayıtları (müşteri adı, firma, temsilci, tutar, durum vb.) |
| `users` | Kullanıcı hesapları (ad, şifreli parola, rol, temsilci ataması) |

---

## 15. Sık Sorulan Sorular

**S: Şifremi unuttum, ne yapmalıyım?**  
C: Admin'den şifre sıfırlama isteyin. Admin, Kullanıcılar sekmesinden **🔑 Şifre Sıfırla** butonuyla yeni şifre belirleyebilir.

**S: Verilerim nerede saklanıyor?**  
C: Tüm veriler Firebase Firestore bulut veritabanında saklanır. İnternet bağlantısı gereklidir.

**S: Birden fazla kişi aynı anda kullanabilir mi?**  
C: Evet. Firestore gerçek zamanlı senkronizasyon sağlar. Bir kullanıcının eklediği kayıt diğer kullanıcılarda anında görünür.

**S: Excel dosyamdaki sütun adları farklı, içe aktarabilir miyim?**  
C: Evet. Sistem yaygın sütun adlarını (Müşteri, Ad, İsim, Firma vb.) otomatik tanır. Tanınmayan sütunlar atlanır.

**S: Silinen kayıtlar geri getirilebilir mi?**  
C: Hayır. Silme işlemi kalıcıdır. Silmeden önce dışa aktarma yapmanız önerilir.

**S: Mobilde nasıl kullanılır?**  
C: Sistem otomatik olarak mobil kart görünümüne geçer. Tüm temel işlevler mobilde de kullanılabilir.

**S: Firebase bağlantısı koparsa ne olur?**  
C: Başlıktaki bağlantı göstergesi kırmızıya döner. Bağlantı geri geldiğinde veriler otomatik senkronize edilir.

---

*Son güncelleme: Nisan 2026*
