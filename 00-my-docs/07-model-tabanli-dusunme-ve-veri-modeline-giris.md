# Model Tabanlı Düşünme ve Veri Modeline Giriş

## Amaç

Bu doküman, Power BI'ın neden rapor tabanlı değil model tabanlı bir uygulama olarak düşünülmesi gerektiğini açıklar. Ayrıca veri modelinin temel kavramlarına giriş yapar.

Bu dokümanın kapsamı:

- Rapor tabanlı yaklaşım
- Model tabanlı yaklaşım
- Semantic layer
- Transaction/fact tablo fikri
- Master/dimension tablo fikri
- Entity, attribute, primary key ve foreign key kavramları
- Denormalize tabloyu modele uygun düşünme

Bu dokümanda tarih tablosu, kardinalite, granülarite ve ileri ilişki tipleri detaylandırılmaz.

## 1. Rapor Tabanlı Yaklaşım Nedir?

Rapor tabanlı araçlarda her rapor sayfası çoğu zaman kendisine özel bir sorgu veya veri setiyle çalışır.

Örnek:

Bir kullanıcı "belge tipine ve ilçeye göre satış toplamı" ister. Geliştirici bu rapor için özel bir SQL sorgusu yazar.

Daha sonra kullanıcı "bunu ay bazında, ürün kategorisiyle ve önceki aya göre değişimle görmek istiyorum" derse sorgu yeniden düzenlenir.

## 2. Model Tabanlı Yaklaşım Nedir?

Power BI model tabanlı bir uygulamadır.

Model tabanlı yaklaşımda önce doğru semantic model kurulur. Raporlar bu modelin üzerine inşa edilir.

Bu modelde:

- Tablolar bulunur.
- Tablolar arasında ilişkiler vardır.
- Ölçüler tanımlanır.
- Kullanıcıların raporda kullanacağı alanlar düzenlenir.

## 3. Semantic Layer

Semantic layer, teknik veri yapısını iş kullanıcılarının anlayabileceği analitik katmana dönüştüren yapıdır.

Örnek:

Kaynak sistemde `SLS_TRX_AMT` gibi bir sütun olabilir. Semantic model içinde bu alan "Satış Tutarı" olarak adlandırılır ve "Toplam Satış" ölçüsüyle kullanılır.

## 4. Neden Model Önce Gelir?

Power BI'da önce rapor sayfasını tasarlamak cazip görünebilir. Ancak model doğru kurulmadan görsel oluşturmak uzun vadede sorun çıkarır.

Yanlış model şu problemlere yol açabilir:

- Filtreler beklenmedik çalışır.
- Toplamlar yanlış hesaplanır.
- Aynı metrik farklı raporlarda farklı sonuç verir.
- Raporlar yavaşlar.
- Bakım zorlaşır.

Temel ilke:

Önce model, sonra rapor.

## 5. Transaction Tablosu

Transaction tablosu, iş olaylarını veya hareketleri tutan tablodur.

Örnek transaction tabloları:

- Satış hareketleri
- Fatura satırları
- Sipariş satırları
- Stok hareketleri
- Finansal hesap hareketleri

## 6. Master Tablo

Master tablo, transaction tablosunda geçen varlıkları açıklayan tablodur.

Örnek master tablolar:

- Müşteriler
- Ürünler
- Hesaplar
- Mağazalar
- Satış temsilcileri

Master tabloda ilgili varlığı tekil tanımlayan bir anahtar bulunur.

## 7. Entity ve Attribute

Entity, modelde ayrı bir varlık olarak ele alınabilecek kavramdır.

Örnek entity'ler:

- Müşteri
- Ürün
- Mağaza
- Hesap

Attribute ise bu entity'yi açıklayan özelliktir.

## 8. Primary Key ve Foreign Key

Primary key, master tabloda ilgili kaydı tekil tanımlayan anahtardır.

Foreign key, transaction tabloda master tabloya referans veren anahtardır.

Örnek:

Müşteriler[Müşteri ID] primary key gibi davranır. Satışlar[Müşteri ID] foreign key gibi davranır.

## 9. Denormalize Tablo Problemi

Denormalize tabloda transaction bilgileri ile master bilgiler aynı tabloda tekrar eder.

Bu yapıda müşteri adı ve ürün adı gibi alanlar tekrar eder. Power BI modelinde bu tablo genellikle ayrıştırılır:

- Satışlar transaction/fact tablosu
- Müşteriler master/dimension tablosu
- Ürünler master/dimension tablosu

## 10. Kısa Özet

Power BI'da başarılı rapor geliştirmenin temeli model tabanlı düşünmektir.

Hatırlanması gerekenler:

- Power BI rapor tabanlı değil, model tabanlı düşünülmelidir.
- Semantic layer iş kullanıcıları için anlamlı analitik katmandır.
- Transaction tablolar hareketleri tutar.
- Master tablolar varlıkları açıklar.
- Primary key master tabloda tekildir.
- Foreign key transaction tabloda tekrar edebilir.
- Denormalize tablolar modelleme için çoğu zaman ayrıştırılmalıdır.

## Kaynak Videolar

- Video 14: Power BI Model Tabanlı Bir Uygulamadır, Rapor Tabanlı Değil  
  https://www.youtube.com/watch?v=xj_a_l0Y4F4
- Video 15: Veri Modelinde Temel Kavramlar, 1st Normal Form, Denormalize Tablolar  
  https://www.youtube.com/watch?v=lKPhrCbVwX0

