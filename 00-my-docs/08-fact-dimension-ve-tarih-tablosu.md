# Fact, Dimension ve Tarih Tablosu

## Amaç

Bu doküman, Power BI veri modelinde fact table, dimension table ve tarih tablosu kavramlarını açıklar.

Bu dokümanın kapsamı:

- Fact table
- Dimension table
- Fact/dimension ayrımı
- Unpivot ihtiyacı
- Slowly changing dimension fikrine kısa giriş
- Tarih tablosunun önemi
- Auto date/time ayarı
- Mark as date table
- Ay ve gün sıralama problemleri

Bu dokümanda kardinalite, granülarite ve kompozit anahtar detayları ayrı dokümana bırakılır.

## 1. Fact Table Nedir?

Fact table, ölçülebilir iş olaylarını tutan tablodur.

Türkçede olgu tablosu veya hareket tablosu olarak düşünülebilir.

Örnek fact tablolar:

- Satışlar
- Siparişler
- Stok hareketleri
- Finansal hareketler
- Web ziyaretleri

Fact tabloda genellikle şu bilgiler bulunur:

- Tarih bilgisi
- Dimension tablolarına bağlanan ID alanları
- Sayısal ölçüm alanları
- İşleme ait satır özellikleri

## 2. Dimension Table Nedir?

Dimension table, fact tablodaki işlemleri açıklayan varlık bilgilerini tutar.

Türkçede boyut tablosu veya master tablo olarak düşünülebilir.

Örnek dimension tablolar:

- Müşteriler
- Ürünler
- Tarih
- Mağazalar
- Satış temsilcileri

Dimension tabloda anahtar alan tekil olmalıdır.

## 3. Fact ve Dimension Ayrımı

Fact tablo ölçülerin hesaplandığı yerdir. Dimension tablo filtreleme ve gruplama için kullanılır.

Örnek analiz:

Müşteri sınıfına göre toplam satış.

Bu analizde:

- Müşteri sınıfı Müşteriler dimension tablosundan gelir.
- Toplam satış Satışlar fact tablosundan hesaplanır.

## 4. Fact Tabloda Ne Kalmalı?

Satış fact tablosunda genellikle şunlar kalmalıdır:

- Satış tarihi
- Müşteri ID
- Ürün ID
- Mağaza ID
- Satış tutarı
- Miktar
- Belge numarası
- Belge tipi

Müşteri adı, müşteri sınıfı, ürün adı, marka ve kategori gibi açıklayıcı bilgiler dimension tablolarda tutulmalıdır.

## 5. Unpivot Nedir?

Unpivot, sütunlara yayılmış değerleri satırlara dönüştürme işlemidir.

Örnek:

Ocak, Şubat ve Mart sütunları tek bir "Ay" sütununa ve tek bir "Tutar" sütununa dönüştürülür.

Power BI modelinde analiz yapılacak değerlerin düzenli ve tekrarlanabilir bir yapıda olması gerekir. Unpivot bu nedenle çok sık kullanılan bir dönüşümdür.

## 6. Slowly Changing Dimension Fikri

Bazı dimension bilgileri zamanla değişebilir.

Örnek:

Bir çalışanın departmanı zaman içinde değişebilir. Bugünkü departmanı İnsan Kaynakları iken, geçmişte Finans departmanında çalışmış olabilir.

Bu tür durumlara veri ambarı literatüründe slowly changing dimension denir.

Başlangıç seviyesinde detayına girmek gerekmez. Bilinmesi gereken nokta şudur:

Dimension tablodaki bir attribute zamanla değişebiliyorsa, geçmişi nasıl tutacağınız model tasarımını etkiler.

## 7. Tarih Tablosu Neden Gereklidir?

Power BI modellerinde tarih tablosu neredeyse her zaman gereklidir.

Tarih tablosu sayesinde:

- Yıl, çeyrek, ay, hafta, gün analizleri yapılır.
- Time intelligence hesaplamaları desteklenir.
- Ay isimleri doğru sırada gösterilir.
- Birden fazla fact tablo aynı tarih boyutu üzerinden analiz edilebilir.

## 8. Auto Date/Time Ayarı

Power BI Desktop, tarih alanları için otomatik gizli tarih tabloları oluşturabilir.

Bu özellik başlangıçta pratik görünür; ancak profesyonel modellerde genellikle kapatılması önerilir.

Neden?

- Modelde görünmeyen gizli tarih tabloları oluşur.
- Dosya boyutu artabilir.
- Tarih yönetimi dağınık hale gelir.
- Tek ve kontrollü tarih tablosu kullanımı zorlaşır.

## 9. Mark as Date Table

Power BI Desktop'ta oluşturulan tarih tablosu "Mark as date table" ile tarih tablosu olarak işaretlenebilir.

Bu işlem sırasında Power BI tarih sütununu doğrular.

Kontrol edilen başlıca noktalar:

- Tekil değerler
- Boş değer olmaması
- Kesintisiz tarih aralığı
- Uygun tarih veri tipi

## 10. Kısa Özet

Fact ve dimension ayrımı Power BI modelinin temelidir.

Hatırlanması gerekenler:

- Fact tablo işlemleri ve ölçülebilir değerleri tutar.
- Dimension tablo açıklayıcı varlık bilgilerini tutar.
- Fact tabloda entity'lerin ID alanları bulunur.
- Açıklayıcı alanlar dimension tablolara taşınmalıdır.
- Excel tipi geniş tablolar çoğu zaman unpivot edilmelidir.
- Her modelde kontrollü bir tarih tablosu bulunmalıdır.

## Kaynak Videolar

- Video 16: Power BI Eğitimi - Fact ve Dimension Tabloları  
  https://www.youtube.com/watch?v=KRTmyIozlao
- Video 17: Power BI Eğitimi - Tarih Tablosu, En İyi Pratikler  
  https://www.youtube.com/watch?v=bid0SNpsQpg

