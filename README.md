# 🎬 FİLM VE DİZİ ARŞİVİ GEREKSİNİMLERİ

## 👤 Kullanıcı Gereksinimleri

### Genel Kullanıcı Gereksinimleri
- **Kayıt ve Giriş İşlemleri:** Kullanıcılar, siteye kayıt olabilmeli ve kullanıcı adı/e-posta ve şifre ile giriş yapabilmelidir.
- **Profil Güncelleme:** Kullanıcılar, profil bilgilerini (kullanıcı adı, e-posta, şifre) güncelleyebilmelidir.
- **Arama ve Filtreleme:** Kullanıcılar, film ve dizileri başlık, tür, yıl, ülke gibi özelliklere göre arayabilmeli ve filtreleyebilmelidir.
- **Favorilere Ekleme:** Beğendikleri yapımları favorilerine ekleyebilmelidir.
- **İzleme Listesi Yönetimi:** İzleme listesine ekleyip, listedeki yapımların durumunu (İzlenecek, İzleniyor, Tamamlandı) güncelleyebilmelidir.
- **Yorum Yapma ve Puan Verme:** İzledikleri yapımlara yorum yapabilir ve puan verebilir.
- **Öneri Sistemi:** İzledikleri veya beğendikleri yapımlara göre öneriler alabilirler.

### Yönetici (Admin) Gereksinimleri
- **Film ve Dizi Yönetimi:** Yeni film ve diziler ekleyebilir, var olanları güncelleyip silebilir.
- **Kategori (Tür) Yönetimi:** Yeni kategoriler ekleyebilir, mevcut kategorileri güncelleyip silebilir.
- **Oyuncu ve Yönetmen Yönetimi:** Yeni oyuncu ve yönetmen ekleyebilir, var olanları güncelleyip silebilir.
- **Ödül Yönetimi:** Ödül kategorileri ekleyebilir, film/dizi ödüllerini güncelleyebilir.
- **Kullanıcı Yorum Yönetimi:** Yorumları inceleyip gerektiğinde silebilir.
- **Sezon ve Bölüm Yönetimi:** Dizilere yeni sezon ve bölüm ekleyebilir, var olanları güncelleyebilir.

---

## 🏷️ Varlıklar ve Nitelikleri

### 1️⃣ Film ve Dizi Tablosu (**Movies & Series**)
- **ID:** Birincil anahtar  
- **Title:** Film veya dizi adı  
- **Release_Year:** Çıkış yılı  
- **Duration:** Süre (dizi ise bölüm sayısı da olabilir)  
- **Average_Rating:** Ortalama izleyici puanı  
- **Description:** Kısa açıklama  
- **Type:** Film veya dizi tipi  

### 2️⃣ Kategori Tablosu (**Genres**)
- **ID:** Birincil anahtar  
- **Name:** Tür adı  
- **Description:** Tür hakkında açıklama  

### 3️⃣ Film-Kategori İlişkisi (**Movies_Series_Categories**)
- **ID:** Birincil anahtar  
- **Movies_Series_ID:** Film veya dizinin ID’si (yabancı anahtar)  
- **Category_ID:** Türün ID’si (yabancı anahtar)  
> **Not:** Bir film/dizi birden fazla kategoriye sahip olabilir; bu tablo N-N ilişkiyi sağlar.

### 4️⃣ Kullanıcı Tablosu (**Users**)
- **User_ID:** Birincil anahtar  
- **Username:** Kullanıcı adı  
- **Password:** Şifre  
- **Email:** E-posta adresi  
- **Role:** Kullanıcı türü (normal kullanıcı veya yönetici)  
- **Created_At:** Hesap oluşturulma tarihi  

### 5️⃣ Oyuncu Tablosu (**Actors**)
- **ID:** Birincil anahtar  
- **Name:** Oyuncu adı  
- **Birth_Date:** Doğum tarihi  
- **Nationality:** Uyruğu  
- **Biography:** Kısa biyografi  

### 6️⃣ Yönetmen Tablosu (**Directors**)
- **ID:** Birincil anahtar  
- **Name:** Yönetmen adı  
- **Birth_Date:** Doğum tarihi  
- **Nationality:** Uyruğu  
- **Biography:** Kısa biyografi  

### 7️⃣ Kullanıcı Yorum Tablosu (**User_Reviews**)
- **Review_ID:** Birincil anahtar  
- **User_ID:** Kullanıcının ID’si (yabancı anahtar)  
- **Movies_Series_ID:** Filmin/dizinin ID’si (yabancı anahtar)  
- **Rating:** Kullanıcının verdiği puan  
- **Comment:** Yorum içeriği  
- **Date:** Yorum tarihi  

### 8️⃣ Favori Tablosu (**User_Favorites**)
- **User_ID:** Kullanıcının ID’si (yabancı anahtar)  
- **Movies_Series_ID:** Filmin/dizinin ID’si (yabancı anahtar)  
- **Date_Added:** Favorilere eklenme tarihi  

### 9️⃣ İzleme Listesi Tablosu (**User_Watchlist**)
- **User_ID:** Kullanıcının ID’si (yabancı anahtar)  
- **Movies_Series_ID:** Filmin/dizinin ID’si (yabancı anahtar)  
- **Date_Added:** İzleme listesine eklenme tarihi  
- **Status:** İzleme durumu (İzlenecek, İzleniyor, Tamamlandı)  

### 🔟 Ödül Tablosu (**Awards**)
- **Award_ID:** Birincil anahtar  
- **Name:** Ödül adı  
- **Category:** Ödül kategorisi (En İyi Film, En İyi Erkek Oyuncu vb.)  
- **Year:** Ödül yılı  
- **Country:** Ödülün verildiği ülke  

### 1️⃣1️⃣ Film/Oyuncu İlişkisi (**Movies_Series_Actors**)
- **ID:** Birincil anahtar  
- **Movies_Series_ID:** Film/dizinin ID’si (yabancı anahtar)  
- **Actor_ID:** Oyuncunun ID’si (yabancı anahtar)  
- **Character_Name:** Karakter adı  

### 1️⃣2️⃣ Film/Yönetmen İlişkisi (**Movies_Series_Directors**)
- **ID:** Birincil anahtar  
- **Movies_Series_ID:** Film/dizinin ID’si (yabancı anahtar)  
- **Director_ID:** Yönetmenin ID’si (yabancı anahtar)  

### 1️⃣3️⃣ Film/Ödül İlişkisi (**Movies_Series_Awards**)
- **ID:** Birincil anahtar  
- **Movies_Series_ID:** Film/dizinin ID’si (yabancı anahtar)  
- **Award_ID:** Ödülün ID’si (yabancı anahtar)  
- **Year:** Ödül yılı  
- **Is_Winner:** Kazandı mı (boolean)  

---

## ⚡ Notlar
- Bir film/dizi birden fazla kategoriye sahip olabilir.  
- Tüm film/dizi ilişkileri (Oyuncular, Yönetmenler, Ödüller) N-N ilişki şeklindedir.  
- Kullanıcılar yorum, favori ve izleme listesi özelliklerini rahatlıkla kullanabilir.  
- **Foreign Key kullanımı**, tablolar arası veri tutarlılığını ve bütünlüğünü sağlar.
  
