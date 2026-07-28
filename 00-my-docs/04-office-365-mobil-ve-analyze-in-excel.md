# Office 365 Entegrasyonu, Mobil Kullanım ve Analyze in Excel

## Amaç

Bu doküman, Power BI'ın Microsoft 365 ekosistemiyle nasıl birlikte çalıştığını ve raporların Excel, PowerPoint, Teams ve mobil uygulamalar üzerinden nasıl kullanılabileceğini açıklar.

Bu dokümanın kapsamı:

- Power Automate entegrasyonu
- Power Apps entegrasyonu
- PowerPoint ve Teams kullanımı
- Power BI mobil uygulaması
- Mobil layout
- Analyze in Excel

Bu dokümanda veri modelleme, gateway ve güvenlik detaylarına girilmez.

## 1. Power BI ve Microsoft 365 Ekosistemi

Power BI, Microsoft ekosisteminin diğer araçlarıyla birlikte çalışacak şekilde tasarlanmıştır.

Sık görülen entegrasyonlar:

- Power Automate
- Power Apps
- PowerPoint
- Microsoft Teams
- Excel
- Mobil Power BI uygulamaları

Bu entegrasyonların amacı Power BI raporlarını yalnızca izlenen ekranlar olmaktan çıkarıp iş süreçlerinin bir parçası haline getirmektir.

## 2. Power Automate Entegrasyonu

Power Automate, tetikleyici ve aksiyon mantığıyla çalışan iş akışı aracıdır.

Basit mantık:

Bir olay gerçekleşirse, bir işlem yapılır.

Örnekler:

- Bir dosya SharePoint klasörüne eklenirse bildirim gönder.
- Bir Power BI semantic model'i güncellendiğinde başka bir işlem başlat.
- Kullanıcı rapordaki butona basınca veri yenileme süreci tetikle.

## 3. Power Apps Entegrasyonu

Power Apps, düşük kodlu uygulama geliştirme platformudur.

Power BI raporuna Power Apps görseli eklenerek kullanıcıya rapor ekranından ayrılmadan veri girişi yaptırılabilir.

Örnek:

Finans ekibi bütçe raporuna bakarken aynı ekranda ilgili hesap için bütçe girişi yapabilir.

## 4. PowerPoint ve Teams Entegrasyonu

Power BI raporları PowerPoint sunumlarında kullanılabilir. Bu entegrasyon sayesinde rapor ekran görüntüsü olarak değil, canlı ve etkileşimli içerik olarak sunuma eklenebilir.

Power BI içerikleri Microsoft Teams içinde sekme olarak da paylaşılabilir.

Örnek:

Satış ekibinin Teams kanalına "Satış Dashboard" sekmesi eklenir. Ekip üyeleri Teams'ten ayrılmadan raporu görüntüler.

## 5. Mobil Power BI Kullanımı

Power BI raporlarına iki temel yolla erişilebilir:

- Web tarayıcısı üzerinden
- Power BI mobil uygulaması üzerinden

Mobil uygulamalar telefon ve tabletlerde rapor tüketimi için kullanılır.

## 6. Mobil Layout

Power BI raporu Desktop görünümünde tasarlandığında mobilde aynı şekilde görüntülenebilir. Ancak geniş ekran için hazırlanmış rapor sayfası telefonda okunması zor olabilir.

Bu nedenle Power BI Desktop içinde Mobile layout hazırlanmalıdır.

Mobil layout ile:

- Önemli görseller telefon ekranına uygun sıraya konur.
- Gereksiz veya küçük görseller mobil görünümden çıkarılabilir.
- Kartlar, KPI'lar ve temel grafikler öne alınabilir.

## 7. Analyze in Excel

Analyze in Excel, Excel'in Power BI semantic model'e canlı bağlantı kurmasını sağlar.

Bu özellik, Excel kullanıcılarını Power BI ekosisteminden koparmadan merkezi veri modeliyle çalıştırmak için çok değerlidir.

Temel mantık:

- Semantic model Power BI Service'te yayımlıdır.
- Excel bu modele canlı bağlantı kurar.
- Kullanıcı PivotTable ile analiz yapar.
- Veri Excel dosyasında kopuk ve kontrolsüz şekilde çoğaltılmaz.

## 8. Export to Excel ile Analyze in Excel Farkı

Export to Excel, bir görseldeki veriyi dışarı aktarmaktır.

Analyze in Excel ise Excel'in doğrudan semantic model'e bağlanmasıdır.

Export yaklaşımı veriyi koparır. Analyze in Excel yaklaşımı merkezi modele bağlı kalır.

## 9. Kısa Özet

Power BI, Microsoft 365 ekosistemiyle birlikte kullanıldığında daha güçlü hale gelir.

Hatırlanması gerekenler:

- Power Automate rapordan iş akışı tetiklemek için kullanılabilir.
- Power Apps rapor içine veri girişi deneyimi ekleyebilir.
- PowerPoint ve Teams entegrasyonları raporların iş süreçlerine girmesini sağlar.
- Mobil layout hazırlanmayan raporlar telefonda zor okunabilir.
- Analyze in Excel, Excel kullanıcılarını merkezi Power BI modeline bağlamanın en sağlıklı yollarından biridir.

## Kaynak Videolar

- Video 6: Power BI Eğitimi - Power BI Office 365 Entegrasyonu  
  https://www.youtube.com/watch?v=l8NmdD-J5I8
- Video 8: Power BI Eğitimi - Mobil Aplikasyon  
  https://www.youtube.com/watch?v=QCklcHu0QIE
- Video 10: Power BI Eğitimi - Analyze in Excel  
  https://www.youtube.com/watch?v=NXoRz8aQujI

