# 🏥 Hastane Otomasyonu

Bu proje, **Java** programlama dili kullanılarak geliştirilen kapsamlı bir **hastane otomasyon sistemidir**. Amacı, hasta, doktor ve randevu yönetimini kolaylaştırarak hastanelerin operasyonel süreçlerini dijital ortamda daha hızlı ve verimli hale getirmektir. Sistem, hastane içerisindeki verilerin düzenli, güvenli ve erişilebilir bir şekilde saklanmasını sağlarken, kullanıcı dostu bir arayüz sunmayı hedeflemektedir.

## 📌 Proje Amaçları
- Hastane içi hasta, doktor ve randevu yönetiminin **otomatikleştirilmesi**.
- **Kağıt tabanlı sistemlerden dijital sistemlere geçişin sağlanması**.
- **Hata payının en aza indirilmesi** ve süreçlerin daha hızlı hale getirilmesi.
- **Hasta bilgilerinin güvenli bir şekilde saklanması ve yalnızca yetkilendirilmiş kullanıcılar tarafından erişilebilir olması**.
- **Kolay yönetilebilir bir randevu sisteminin oluşturulması**.
- **Hastalar için kullanıcı dostu bir arayüz** sunarak online randevu almalarını sağlamak.
- **Doktorların hastalarına ait verilere hızlıca ulaşabilmesi** ve reçete yazma süreçlerinin kolaylaştırılması.

---
## 📌 Özellikler
### 🔹 Hasta Yönetimi
- Yeni hasta kaydı oluşturma
- Hasta bilgilerini güncelleme ve silme
- Hastalara ait tıbbi geçmişi görüntüleme
- Hastalara teşhis ve reçete ekleme
- Hasta dosya ekleme ve arşivleme
- Sigorta bilgilerini ekleme

### 🔹 Doktor Yönetimi
- Doktorların uzmanlık alanlarını kaydetme ve düzenleme
- Çalışma saatlerini belirleme ve değiştirme
- Doktorların hasta geçmişine erişebilmesi
- Randevularını görüntüleme ve yönetme
- Hastalara reçete yazma ve ilaç önerme

### 🔹 Randevu Sistemi
- Hastalar için randevu oluşturma, güncelleme ve iptal etme
- Doktorların müsaitlik durumuna göre randevu planlama
- Otomatik randevu hatırlatma (E-posta / SMS ile)
- Acil durum randevu sistemi
- Randevu geçmişini saklama ve analiz yapabilme

### 🔹 Kullanıcı Rolleri ve Yetkilendirme
- **Admin**: Tüm sistem yönetim işlemlerini gerçekleştirebilir.
- **Doktor**: Hasta bilgilerini görüntüleyebilir, reçete yazabilir ve randevularını yönetebilir.
- **Hasta**: Kendi randevularını oluşturabilir ve geçmiş randevularını inceleyebilir.
- **Sekreter**: Randevuları yönetebilir, doktor ve hasta bilgilerini güncelleyebilir.

### 🔹 Veritabanı Entegrasyonu
- Hasta, doktor ve randevu bilgileri güvenli bir şekilde saklanır.
- **İlişkisel veritabanı yapısı** kullanılarak veri tutarlılığı sağlanır.
- **Gizlilik ve güvenlik önlemleri** ile hasta verileri korunur.
- **Veritabanı yedekleme mekanizması** sayesinde veri kaybı önlenir.

### 🔹 Güvenlik Önlemleri
- **JWT (JSON Web Token) tabanlı kimlik doğrulama** ile güvenli erişim sağlanması
- **Spring Security** ile kullanıcı bazlı yetkilendirme
- **Hassas verilerin şifrelenmesi** (örn. hasta bilgileri ve parola güvenliği için BCrypt kullanımı)
- **Güvenlik duvarı ve IP kısıtlama** ile yetkisiz erişimlerin engellenmesi

---
## 🔧 Kullanılan Teknolojiler
- **Java (Spring Boot)** – Backend geliştirme
- **JavaFX** – Kullanıcı arayüzü (Masaüstü uygulaması için)
- **MySQL / PostgreSQL** – Veritabanı yönetimi
- **Hibernate (ORM)** – Veritabanı işlemleri için
- **Maven / Gradle** – Bağımlılık yönetimi
- **Lombok** – Kodun daha okunabilir ve temiz olması için
- **JWT / Spring Security** – Yetkilendirme ve güvenlik mekanizmaları
- **RESTful API** – Verilerin JSON formatında taşınması
- **Docker** – Konteynerizasyon ve taşınabilirlik
- **Swagger** – API dokümantasyonu

---
## 📅 Proje Takvimi
- **Başlangıç Tarihi**: Şubat 2025
- **Planlanan Tamamlama Tarihi**: 10 Mayıs 2025
- **Geliştirme Aşamaları**:
  1. **Analiz ve Planlama** (Şubat 2025)
  2. **Veritabanı ve Backend Geliştirme** (Mart 2025)
  3. **Frontend ve Kullanıcı Arayüzü Tasarımı** (Nisan 2025)
  4. **Test Süreci ve Son Düzeltmeler** (Nisan - Mayıs 2025)
  5. **Son Teslim ve Dağıtım** (10 Mayıs 2025)

---
## 📌 Ekip Bilgisi
Bu proje, **3 kişilik bir yazılım geliştirme ekibi** tarafından yürütülmektedir. **Grup lideri olarak proje yönetimi ve geliştirme süreçlerinden sorumluyum.**

### 🛠 Katkıda Bulunmak İçin
- Pull request gönderebilir veya önerilerinizle katkıda bulunabilirsiniz!
- Hata bildirmek veya geliştirme sürecine destek olmak için **issue oluşturabilirsiniz**.

🚀 **Projeye Katkılarınızı Bekliyoruz!** ✨
