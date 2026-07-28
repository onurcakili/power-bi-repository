# Power BI Desktop, Power BI Service ve Temel Topoloji

## Amaç

Bu doküman, Power BI ekosisteminin temel parçalarını ve Power BI Desktop ile Power BI Service arasındaki ilişkiyi açıklar.

Bu dokümanın kapsamı:

- Power BI Desktop'ın temel katmanları
- Power BI Service'in rolü
- Veri kaynakları
- Import ve DirectQuery kavramlarına giriş
- PBIX dosyası
- Power BI Desktop arayüzü
- İlk veri alma ve rapor oluşturma mantığı

Bu dokümanda fact/dimension modelleme, DAX, güvenlik ve gateway detayları yalnızca genel fikir düzeyinde geçer.

## 1. Power BI Topolojisi

Power BI ekosistemi üç temel alandan oluşur:

- Veri kaynakları
- Power BI Desktop
- Power BI Service

Veri kaynakları ham verinin bulunduğu yerdir. Power BI Desktop geliştirme aracıdır. Power BI Service ise raporların yayımlandığı, paylaşıldığı ve yönetildiği bulut ortamıdır.

Örnek veri kaynakları:

- Excel dosyası
- CSV dosyası
- SQL Server
- SharePoint
- OneDrive
- OData servisi
- Kurumsal ERP veya CRM sistemi

## 2. Power BI Desktop'ın Üç Katmanı

Power BI Desktop tek bir uygulama gibi görünür; fakat içinde üç temel çalışma katmanı bulunur.

### 2.1. Veri Hazırlama Katmanı

Bu katmanda Power Query kullanılır.

Power Query ile:

- Veri kaynaklarına bağlanılır.
- Gereksiz satır ve sütunlar temizlenir.
- Veri tipleri düzenlenir.
- Filtreleme yapılır.
- Sütun adları kullanıcı dostu hale getirilir.
- Veriler raporlamaya hazırlanır.

### 2.2. Veri Modeli Katmanı

Bu katmanda tablolar arasındaki ilişkiler kurulur ve ölçüler oluşturulur.

Power BI'da doğru sonuç üretebilmek için veri modeli kritik öneme sahiptir. Ancak bu dokümanda yalnızca model katmanının varlığını bilmek yeterlidir. Modelleme detayları ayrı dokümanlarda ele alınacaktır.

### 2.3. Raporlama Katmanı

Bu katmanda kullanıcıların göreceği rapor sayfaları hazırlanır.

Örnek görseller:

- Tablo
- Matris
- Kart
- Çubuk grafik
- Çizgi grafik
- Harita
- Slicer

## 3. Power BI Service

Power BI Service, Power BI içeriklerinin yayımlandığı ve yönetildiği bulut platformudur.

Power BI Service ile:

- Raporlar yayımlanır.
- Workspace'ler yönetilir.
- Semantic model'ler saklanır.
- Kullanıcılarla paylaşım yapılır.
- Zamanlanmış veri yenileme ayarlanır.
- App oluşturularak rapor dağıtımı yapılır.

Power BI Desktop geliştirme ortamıdır. Power BI Service ise paylaşım ve yönetim ortamıdır.

## 4. Import ve DirectQuery

Power BI veri kaynaklarına farklı bağlantı yöntemleriyle bağlanabilir.

### Import

Import yönteminde veri Power BI modelinin içine alınır.

Bu yöntem başlangıç için en yaygın ve en anlaşılır yöntemdir.

### DirectQuery

DirectQuery yönteminde veri tamamen Power BI modeline alınmaz. Rapor çalışırken veri kaynağına sorgu gönderilir.

Bu yöntem daha çok büyük veritabanları veya güncel veri ihtiyacı olan senaryolarda gündeme gelir.

Başlangıç aşamasında Import yöntemiyle ilerlemek daha sağlıklıdır.

## 5. PBIX Dosyası

Power BI Desktop'ta hazırlanan dosya `.pbix` uzantısıyla kaydedilir.

PBIX dosyası şunları içerebilir:

- Veri bağlantıları
- Power Query adımları
- Veri modeli
- İlişkiler
- Ölçüler
- Rapor sayfaları
- Görseller

Bu dosya Power BI Service'e publish edildiğinde bulut tarafında rapor ve semantic model oluşur.

## 6. Power BI Desktop Arayüzü

Power BI Desktop'ta sol tarafta üç temel görünüm bulunur:

- Report view
- Table view
- Model view

Report view rapor sayfalarının oluşturulduğu alandır. Table view modele yüklenen verilerin incelendiği alandır. Model view tablolar arasındaki ilişkilerin görsel olarak izlendiği ve düzenlendiği alandır.

## 7. İlk Veri Alma Akışı

Power BI'da çalışma genellikle veri kaynağına bağlanmakla başlar.

Temel akış:

1. Home sekmesinden Get Data seçilir.
2. Veri kaynağı türü seçilir.
3. Dosya veya sunucu bilgisi gösterilir.
4. Gerekirse Transform Data seçilerek Power Query açılır.
5. Veri temizlenir ve hazırlanır.
6. Close & Apply ile model tarafına yüklenir.
7. Rapor görünümünde görseller oluşturulur.

Veri üzerinde temizlik veya dönüşüm gerekiyorsa doğrudan Load demek yerine Transform Data seçilmelidir.

## 8. Kısa Özet

Power BI'ın temel topolojisi şu şekilde özetlenebilir:

1. Veri kaynaklarından veri alınır.
2. Power BI Desktop'ta veri hazırlanır.
3. Model ve rapor oluşturulur.
4. PBIX dosyası Power BI Service'e publish edilir.
5. Rapor kullanıcılarla paylaşılır.
6. Gerekirse veri yenileme ve gateway ayarları yapılır.

## Kaynak Videolar

- Video 3: Power BI Eğitimi - PowerBI Desktop PowerBI com Topoloji  
  https://www.youtube.com/watch?v=u2WxpfxL_MU
- Video 4: Power BI Eğitimi - Power BI'a Giriş  
  https://www.youtube.com/watch?v=6ZkNRGjRgBg

