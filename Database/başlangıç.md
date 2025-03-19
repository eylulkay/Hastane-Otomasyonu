CREATE TABLE Hasta (
    id INT IDENTITY(1,1) PRIMARY KEY, --sirali bir sekilde artan hastalarin idsi
    kullanici_id INT UNIQUE NOT NULL, --üsttekinin aynısı fakat kullanıcı id olarak siniflandirdim
    ad NVARCHAR(50) NOT NULL,
    soyad NVARCHAR(50) NOT NULL,
    dogum_tarihi DATE NOT NULL,
    telefon NVARCHAR(15),
    adres NTEXT
);

--hasta tablosunun verileri
SET IDENTITY_INSERT Hasta ON;
INSERT INTO Hasta (id, kullanici_id, ad, soyad, dogum_tarihi, telefon, adres) VALUES
(1, 1, N'Ahmet', N'Yılmaz', '1990-05-12', N'05551234567', N'İstanbul, Türkiye'),
(2, 2, N'Mehmet', N'Demir', '1985-08-23', N'05559876543', N'Ankara, Türkiye'),
(3, 3, N'Ayşe', N'Kaya', '1998-12-02', N'05441239876', N'İzmir, Türkiye'),
(4, 4, N'Fatma', N'Çelik', '2000-07-15', N'05325647891', N'Bursa, Türkiye'),
(5, 5, N'Hasan', N'Koç', '1975-03-30', N'05563451278', N'Adana, Türkiye'),
(6, 6, N'Ayşe', N'Aydın', '1993-06-21', N'05324568793', N'Trabzon, Türkiye'),
(7, 7, N'Hüseyin', N'Şahin', '1982-09-10', N'05457896521', N'Konya, Türkiye'),
(8, 8, N'Elif', N'Yıldırım', '1999-01-25', N'05534789562', N'Eskişehir, Türkiye'),
(9, 9, N'Cem', N'Karaca', '1987-11-14', N'05326987451', N'Gaziantep, Türkiye'),
(10, 10, N'Burak', N'Eren', '1995-04-05', N'05542367895', N'Diyarbakır, Türkiye'),
(11, 11, N'Emre', N'Taş', '2001-10-18', N'05451239874', N'Samsun, Türkiye'),
(12, 12, N'Serkan', N'Güneş', '1978-12-29', N'05347891236', N'Kayseri, Türkiye'),
(13, 13, N'Gül', N'Öztürk', '1989-07-07', N'05531254789', N'Antalya, Türkiye'),
(14, 14, N'Okan', N'Tekin', '1997-02-17', N'05456987423', N'Mersin, Türkiye'),
(15, 15, N'Seda', N'Duman', '2003-05-28', N'05548751236', N'Kocaeli, Türkiye'),
(16, 16, N'İsmail', N'Bozkurt', '1965-09-22', N'05452147896', N'Denizli, Türkiye'),
(17, 17, N'Merve', N'Özkan', '1992-11-03', N'05321478596', N'Malatya, Türkiye'),
(18, 18, N'Cihan', N'Tuna', '1984-08-16', N'05569874123', N'Erzurum, Türkiye'),
(19, 19, N'Büşra', N'Sezer', '1996-06-14', N'05458763214', N'Sakarya, Türkiye'),
(20, 20, N'Efe', N'Altın', '2005-12-01', N'05563214789', N'Muğla, Türkiye');
SET IDENTITY_INSERT Hasta OFF;

---------------------------------------------------------------------------------------------------

CREATE TABLE Doktor (
    id INT IDENTITY(1,1) PRIMARY KEY, --hasta tablosundaki gibi sirali bir sekilde articak benzersiz kimlikleri
    ad NVARCHAR(50) NOT NULL,
    soyad NVARCHAR(50) NOT NULL,
    uzmanlik NVARCHAR(100) NOT NULL,
    telefon NVARCHAR(15)
);

SET IDENTITY_INSERT Doktor ON;
INSERT INTO Doktor (id, ad, soyad, uzmanlik, telefon) VALUES
(1, N'Barış', N'Aslan', N'Kardiyoloji', N'05327894561'),
(2, N'Selin', N'Ekinci', N'Nöroloji', N'05431234678'),
(3, N'Oğuz', N'Kurt', N'Ortopedi', N'05559871234'),
(4, N'Fırat', N'Tan', N'Göz Hastalıkları', N'05329874123'),
(5, N'Ezgi', N'Arslan', N'Dahiliye', N'05458796321'),
(6, N'Levent', N'Yücel', N'Kadın Hastalıkları', N'05541236587'),
(7, N'Berna', N'Akın', N'Psikiyatri', N'05324781245'),
(8, N'Emir', N'Deniz', N'Genel Cerrahi', N'05451239874'),
(9, N'Deniz', N'Kaya', N'Üroloji', N'05542368795'),
(10, N'Berkay', N'Ergin', N'Dermatoloji', N'05327894512'),
(11, N'Tuğba', N'Demirtaş', N'Kardiyoloji', N'05531254789'),
(12, N'Serhat', N'Boz', N'Nefroloji', N'05456987423'),
(13, N'Can', N'Yüksel', N'Endokrinoloji', N'05548751236'),
(14, N'İpek', N'Soylu', N'Kulak Burun Boğaz', N'05452147896'),
(15, N'Rıza', N'Kaptan', N'Nöroloji', N'05321478596'),
(16, N'Hande', N'Yıldız', N'Çocuk Sağlığı', N'05569874123'),
(17, N'Mert', N'Uçar', N'Psikiyatri', N'05458763214'),
(18, N'Sibel', N'Özdemir', N'Kadın Hastalıkları', N'05563214789'),
(19, N'Tuna', N'Koç', N'Genel Cerrahi', N'05458763214'),
(20, N'Erdem', N'Şahin', N'Ortopedi', N'05321478596');
SET IDENTITY_INSERT Doktor OFF;

CREATE TABLE Randevu (
    id INT IDENTITY(1,1) PRIMARY KEY,
    hasta_id INT NOT NULL,
    doktor_id INT NOT NULL,
    randevu_tarihi DATETIME NOT NULL,
    durum NVARCHAR(20) DEFAULT N'Beklemede', 
    aciklama NTEXT,
    CONSTRAINT fk_hasta FOREIGN KEY (hasta_id) REFERENCES Hasta(id),
    CONSTRAINT fk_doktor FOREIGN KEY (doktor_id) REFERENCES Doktor(id)
);

SET IDENTITY_INSERT Randevu ON;
INSERT INTO Randevu (id, hasta_id, doktor_id, randevu_tarihi, durum, aciklama) VALUES
(1, 1, 5, '2025-03-10 09:30:00', N'Beklemede', N'Hastanın kan tahlili yapılacak.'),
(2, 2, 3, '2025-03-11 14:00:00', N'Tamamlandı', N'Hastaya ortopedik muayene yapıldı.'),
(3, 3, 8, '2025-03-12 10:15:00', N'İptal Edildi', N'Hasta randevuya gelmedi.'),
(4, 4, 1, '2025-03-13 16:45:00', N'Beklemede', N'Kalp rahatsızlığı şüphesi var.'),
(5, 5, 6, '2025-03-14 11:00:00', N'Beklemede', N'Genel sağlık kontrolü yapılacak.'),
(6, 6, 2, '2025-03-15 08:30:00', N'Tamamlandı', N'Hastaya nörolojik testler yapıldı.'),
(7, 7, 7, '2025-03-16 13:20:00', N'İptal Edildi', N'Doktor acil bir operasyon nedeniyle iptal etti.'),
(8, 8, 4, '2025-03-17 15:40:00', N'Beklemede', N'Göz muayenesi ve numara değişikliği kontrolü.'),
(9, 9, 10, '2025-03-18 09:00:00', N'Tamamlandı', N'Cilt alerji testi yapıldı.'),
(10, 10, 9, '2025-03-19 12:10:00', N'Beklemede', N'Hastanın idrar yolları enfeksiyonu şikayeti var.');
SET IDENTITY_INSERT Randevu OFF;

CREATE TABLE Admin (
    id INT IDENTITY(1,1) PRIMARY KEY,
    ad NVARCHAR(50) NOT NULL,
    soyad NVARCHAR(50) NOT NULL,
    kullanici_adi NVARCHAR(50) UNIQUE NOT NULL,
    sifre NVARCHAR(255) NOT NULL,
    rol NVARCHAR(20) DEFAULT N'admin' -- 'admin' veya 'personel' olabilir
);

SET IDENTITY_INSERT Admin ON;
INSERT INTO Admin (id, ad, soyad, kullanici_adi, sifre, rol) VALUES
(1, N'Ahmet', N'Türkoğlu', N'ahmetadmin', N'hashed_password1', N'admin'),
(2, N'Emine', N'Korkmaz', N'eminepersonel', N'hashed_password2', N'personel'),
(3, N'Murat', N'Demir', N'muratadmin', N'hashed_password3', N'admin'),
(4, N'Ayşenur', N'Öztürk', N'aysenurpersonel', N'hashed_password4', N'personel');
SET IDENTITY_INSERT Admin OFF;

-- Randevu detaylarını görmek için sorgu
SELECT 
    R.id AS randevu_id,
    H.ad AS hasta_adi,
    H.soyad AS hasta_soyadi,
    D.ad AS doktor_adi,
    D.soyad AS doktor_soyadi,
    R.randevu_tarihi,
    R.durum
FROM Randevu R
JOIN Hasta H ON R.hasta_id = H.id
JOIN Doktor D ON R.doktor_id = D.id;

-- Bekleyen randevuları görmek için sorgu
SELECT 
    R.id AS randevu_id,
    H.ad AS hasta_adi,
    H.soyad AS hasta_soyadi,
    D.ad AS doktor_adi,
    D.soyad AS doktor_soyadi,
    R.randevu_tarihi,
    R.durum
FROM Randevu R
JOIN Hasta H ON R.hasta_id = H.id
JOIN Doktor D ON R.doktor_id = D.id
WHERE R.durum = N'Beklemede';

-- Hasta ve randevuları görmek için sorgu
SELECT 
    R.aciklama, 
    R.hasta_id, 
    D.ad AS doktor_ad, 
    D.uzmanlik
FROM 
    Randevu R
JOIN Hasta H ON R.hasta_id = H.id
JOIN Doktor D ON R.doktor_id = D.id;
