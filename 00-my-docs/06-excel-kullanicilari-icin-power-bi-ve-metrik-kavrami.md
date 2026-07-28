# Excel Kullanıcıları İçin Power BI ve Metrik Kavramı

## Amaç

Bu doküman, Excel veya SQL geçmişi olan kullanıcıların Power BI'a geçerken anlaması gereken metrik, Power Query, Power Pivot ve model tabanlı analiz mantığını açıklar.

Bu dokümanın kapsamı:

- Metrik kavramı
- Implicit ve explicit measure ayrımı
- SQL profili için düşünce değişimi
- Power Pivot ve Power Query'in Excel içindeki yeri
- Excel ile Power BI'ın birlikte kullanımı

Bu dokümanda ileri DAX, yıldız şema ve güvenlik konularına girilmez.

## 1. Excel'den Power BI'a Geçiş

Excel kullanıcıları genellikle veriyi tablo halinde görmeye ve pivot tabloyla analiz etmeye alışkındır.

Power BI bu alışkanlığa yakın bir deneyim sunar; fakat arka tarafta daha güçlü bir semantic model mantığı vardır.

Excel'de analiz çoğu zaman dosya merkezlidir. Power BI'da analiz model merkezlidir.

## 2. Metrik Nedir?

Metrik, iş sorusunu sayısal olarak cevaplayan hesaplamadır.

Örnek metrikler:

- Toplam satış
- Toplam maliyet
- Brüt kar
- Kar marjı
- Sipariş sayısı
- Ortalama satış tutarı

Power BI'da metrikler genellikle DAX ölçüleriyle tanımlanır.

Örnek:

```DAX
Toplam Satış = SUM(Satışlar[Satış Tutarı])
```

## 3. Implicit Measure

Power BI'da sayısal bir sütun görsele sürüklendiğinde Power BI otomatik olarak toplam, ortalama veya sayım gibi bir özetleme yapabilir. Buna implicit measure denir.

Başlangıç için kolaydır; ancak profesyonel modelleme açısından sınırlıdır.

Riskleri:

- İş kuralı açık şekilde tanımlanmamıştır.
- Aynı metrik farklı görsellerde farklı yorumlanabilir.
- Kullanıcı yanlışlıkla ortalama veya sayım seçebilir.

## 4. Explicit Measure

Explicit measure, geliştirici tarafından DAX ile açıkça tanımlanmış ölçüdür.

Örnek:

```DAX
Toplam Maliyet = SUM(Satışlar[Maliyet])
```

```DAX
Brüt Kar = [Toplam Satış] - [Toplam Maliyet]
```

Önemli iş metrikleri explicit measure olarak tanımlanmalıdır.

## 5. SQL Profili İçin Düşünce Değişimi

SQL geçmişi olan kullanıcılar çoğu zaman raporun arkasındaki sorguyu yazmaya alışkındır.

Power BI'da önerilen yaklaşım farklıdır. Veri mümkün olduğunca analiz modeline uygun şekilde alınır. Hesaplama ve analiz mantığı semantic model ve DAX ölçüleri üzerinden yürütülür.

Basit ifade:

SQL tarafında her rapor için ayrı karmaşık sorgu yazmak yerine, Power BI tarafında doğru model ve ölçüler kurulur.

## 6. Excel'de Power Query

Power Query yalnızca Power BI Desktop'ta yoktur. Modern Excel sürümlerinde de Power Query bulunur.

Excel'de Power Query ile:

- Veri kaynaklarına bağlanılır.
- Veri temizlenir.
- Dönüşüm adımları kaydedilir.
- Tekrarlayan işler otomatikleşir.

## 7. Excel'de Power Pivot

Power Pivot, Excel içinde veri modeli kurmayı sağlayan teknolojidir.

Power Pivot ile:

- Birden fazla tablo modele alınabilir.
- Tablolar arasında ilişki kurulabilir.
- DAX ölçüleri yazılabilir.
- PivotTable bu model üzerinden çalışabilir.

Power BI Desktop ile Excel Power Pivot aynı tabular model ailesinden gelir. Bu nedenle Power BI'da öğrenilen modelleme ve DAX kavramlarının önemli bölümü Excel Power Pivot için de geçerlidir.

## 8. Excel ve Power BI Rakip Değildir

Power BI'ın amacı Excel'i yok etmek değildir.

Doğru yaklaşım:

- Kontrolsüz Excel dosyalarını azaltmak
- Merkezi ve güvenilir semantic model oluşturmak
- Excel kullanıcılarının gerekirse bu modele bağlanmasını sağlamak

Analyze in Excel bu nedenle önemlidir.

## 9. Kısa Özet

Excel kullanıcıları için Power BI'a geçişte en önemli nokta, dosya merkezli düşünceden model merkezli düşünceye geçmektir.

Hatırlanması gerekenler:

- Metrik, iş sorusunu cevaplayan sayısal hesaplamadır.
- Önemli metrikler explicit measure olarak tanımlanmalıdır.
- Power Query hem Excel'de hem Power BI'da veri hazırlama aracıdır.
- Power Pivot, Excel içindeki veri modeli katmanıdır.
- Power BI ve Excel birlikte kullanılabilir.

## Kaynak Videolar

- Video 9: Excel ve SQL Profili için Metrik Kavramı  
  https://www.youtube.com/watch?v=TZoFf5-Bq9o
- Video 13: PowerPivot + PowerQuery: Excel'deki Power BI  
  https://www.youtube.com/watch?v=xvU7KoPSFEU

