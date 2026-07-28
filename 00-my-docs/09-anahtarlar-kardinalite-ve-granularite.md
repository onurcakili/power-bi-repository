# Anahtarlar, Kardinalite ve Granülarite

## Amaç

Bu doküman, Power BI veri modelinde kompozit anahtar, kardinalite ve granülarite kavramlarını açıklar.

Bu dokümanın kapsamı:

- Primary key ve foreign key hatırlatması
- Kompozit anahtar
- Kompozit anahtarın nerede oluşturulması gerektiği
- Kardinalite kavramının iki anlamı
- Model boyutu ve performans açısından kardinalite
- Granülarite
- Farklı seviyedeki fact tabloları aynı modelde kullanma

Bu dokümanda many-to-many ve köprü tablolar yalnızca giriş düzeyinde anılır.

## 1. Anahtar Kavramlarını Hatırlama

Power BI veri modelinde tablolar genellikle anahtar sütunlar üzerinden ilişkilendirilir.

Primary key, dimension tablodaki tekil anahtardır.

Foreign key, fact tablodaki tekrar edebilen anahtardır.

Örnek:

Müşteriler tablosunda Müşteri ID tekildir. Satışlar tablosunda aynı Müşteri ID birçok satırda tekrar edebilir.

## 2. Kompozit Anahtar Nedir?

Kompozit anahtar, bir kaydı tekil tanımlamak için birden fazla sütunun birlikte kullanılmasıdır.

Örnek:

Bir ERP sisteminde aynı hesap kodu farklı şirketlerde farklı anlamlara gelebilir.

| Şirket Kodu | Hesap Kodu | Hesap Adı |
| --- | --- | --- |
| 01 | 700100 | Personel Giderleri |
| 02 | 700100 | Pazarlama Giderleri |

Burada yalnızca Hesap Kodu tekil değildir. Hesabı doğru tanımlamak için Şirket Kodu ve Hesap Kodu birlikte kullanılmalıdır.

## 3. Kompozit Anahtar Nerede Oluşturulmalı?

Kompozit anahtar oluşturmak için üç seçenek vardır:

1. Veri kaynağı tarafı
2. Power Query
3. DAX calculated column

Genel tercih sırası:

1. Mümkünse veri kaynağında oluştur.
2. Veri kaynağında mümkün değilse Power Query'de oluştur.
3. En son seçenek olarak DAX calculated column kullan.

## 4. Kardinalite Kavramının İki Anlamı

Power BI'da kardinalite iki farklı bağlamda karşımıza çıkar.

Birinci anlam:

Bir sütundaki tekil değer sayısı.

İkinci anlam:

İki tablo arasındaki ilişkinin türü.

Bu iki anlam karıştırılmamalıdır.

## 5. Sütun Kardinalitesi

Sütun kardinalitesi, bir sütundaki distinct değer sayısıdır.

Örnek:

Cinsiyet sütununda yalnızca "Kadın" ve "Erkek" varsa kardinalite düşüktür.

Müşteri ID sütununda milyonlarca farklı değer varsa kardinalite yüksektir.

Power BI model boyutu ve performansı açısından yüksek kardinalite önemlidir.

## 6. Kardinaliteyi Azaltma Önerileri

Model performansı ve boyutu için şu öneriler uygulanabilir:

- Gereksiz sütunları modele alma.
- "Bir gün lazım olur" düşüncesiyle alan ekleme.
- Auto date/time özelliğini kapat.
- Tarih ve saat bilgisini gerçekten gerektiği kadar detayda tut.
- DateTime sütununda saat bilgisi gerekmiyorsa Date tipine çevir.
- Çok yüksek hassasiyetli sayısal alanları gereksizse yuvarla.
- Calculated column yerine mümkünse veri kaynağı veya Power Query kullan.

## 7. İlişki Kardinalitesi

Tablolar arası ilişkilerde kardinalite, ilişkili sütunlardaki tekil ve tekrar eden değer yapısını ifade eder.

Power BI'da temel ilişki türleri:

- One-to-many
- Many-to-one
- One-to-one
- Many-to-many

Başlangıç ve doğru modelleme açısından en yaygın ve önerilen ilişki türü one-to-many ilişkisidir.

## 8. Granülarite Nedir?

Granülarite, bir tablodaki satırların hangi detay seviyesini temsil ettiğini ifade eder.

Başka bir ifadeyle:

Bir satır neyi temsil ediyor?

Örnek granülarite seviyeleri:

- Gün-ürün seviyesinde satış
- Ay-kategori seviyesinde bütçe
- Fatura satırı seviyesinde satış
- Müşteri-ay seviyesinde hedef

## 9. Farklı Granülarite Problemi

Satışlar tablosu gün ve ürün seviyesinde olabilir.

Bütçe tablosu ise ay ve kategori seviyesinde olabilir.

Bu iki tablo aynı granülaritede değildir.

Satışlar:

- Gün
- Ürün

Bütçe:

- Ay
- Kategori

Bu fark doğrudan ilişki kurmayı zorlaştırır.

## 10. Kısa Özet

Anahtar, kardinalite ve granülarite modelin performansını ve doğruluğunu doğrudan etkiler.

Hatırlanması gerekenler:

- Kompozit anahtar, tek sütunun kaydı tekil tanımlamadığı durumlarda gerekir.
- Kompozit anahtar mümkünse veri kaynağında, değilse Power Query'de oluşturulmalıdır.
- Kardinalite sütundaki tekil değer sayısı anlamına da gelir, ilişki türü anlamına da gelir.
- Yüksek kardinalite model boyutunu ve performansı etkileyebilir.
- Granülarite, fact tablodaki satırın temsil ettiği detay seviyesidir.
- Farklı granülaritedeki fact tablolar doğrudan bağlanmamalı; model tasarımı bilinçli yapılmalıdır.

## Kaynak Videolar

- Video 18: Kompozit Anahtar Nedir, Nasıl Kullanılır?  
  https://www.youtube.com/watch?v=nuLdOpsQip8
- Video 19: Kardinalite Nedir?  
  https://www.youtube.com/watch?v=4q74OMKloyc
- Video 20: Granülarite Nedir?  
  https://www.youtube.com/watch?v=bRyVK1hwMTw

