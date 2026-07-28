# Power BI'ye Giriş

### Giriş

Power BI, veriyi farklı kaynaklardan alıp temizleme, modelleme, analiz etme, görselleştirme ve kullanıcılarla paylaşma sürecini uçtan uca yönetebilen bir iş zekası platformudur.

Power BI öğrenirken yalnızca görsel oluşturmayı değil, veri kaynağından rapor paylaşımına kadar olan bütün akışı anlamak gerekir. Çünkü iyi bir Power BI raporu, arka tarafta doğru kurgulanmış veri modeli ve sürdürülebilir bir veri yenileme yapısı üzerine kurulur.

Bu bölümde iki ana konu ele alınmaktadır:

- Power BI ekosisteminin genel topolojisi
- Power BI Desktop arayüzü, Power Query, veri modeli ve ilk rapor mantığı

## 1. Power BI Ekosistemi

Power BI ekosistemi genel olarak üç ana alan üzerinden düşünülebilir:

- Veri kaynakları
- Power BI Desktop
- PowerBI.com bulut servisi

Veri kaynakları; Excel, CSV, SQL Server, farklı veritabanları, OneDrive, SharePoint, OData veya kurumsal sistemler olabilir.

Power BI Desktop, rapor ve model geliştirdiğimiz masaüstü uygulamasıdır. PowerBI.com ise oluşturduğumuz modeli ve raporları yayımladığımız, paylaştığımız ve zamanlanmış veri yenileme gibi işlemleri yönettiğimiz bulut servisidir.

### Power BI Desktop Nedir?

Power BI Desktop dışarıdan tek bir uygulama gibi görünür. Fakat kendi içinde üç temel katmanı barındırır:

- ETL katmanı
- Veri modeli katmanı
- Raporlama katmanı

ETL katmanı, veri kaynaklarına bağlanıp veriyi temizlediğimiz, dönüştürdüğümüz ve raporlamaya uygun hale getirdiğimiz bölümdür. Bu işlem Power Query ile yapılır.

Veri modeli katmanı, tablolar arasındaki ilişkileri kurduğumuz, ölçüleri hazırladığımız ve analitik yapının temelini oluşturduğumuz bölümdür.

Raporlama katmanı ise kullanıcıların göreceği görselleri, sayfaları, tabloları, grafikleri ve filtreleri hazırladığımız bölümdür.

Bu nedenle Power BI Desktop yalnızca bir görselleştirme aracı olarak düşünülmemelidir. Veri hazırlama, modelleme ve raporlama süreçlerinin tamamı burada başlar.

## 2. Veri Kaynakları ve Bağlantı Yöntemleri

Power BI Desktop ile farklı veri kaynaklarından veri okunabilir.

Örnek veri kaynakları:

- Excel dosyaları
- CSV dosyaları
- SQL veritabanları
- OneDrive dosyaları
- SharePoint dosyaları
- OData servisleri
- Kurumsal ERP veya CRM sistemleri

OneDrive ve SharePoint gibi servislerde tutulan Excel dosyaları da bulut veri kaynağı olarak düşünülebilir.

### Import Yöntemi

Import yönteminde veri, Power BI dosyasının içine alınır.

Bu yöntemde veri kaynağından okunan veriler Power BI modeline aktarılır. Daha sonra raporlar bu içeri alınmış veri üzerinde çalışır.

Genel başlangıç senaryolarında en çok kullanılan yöntem import yöntemidir. Özellikle Excel ve CSV gibi düz dosya kaynaklarında veriye bağlanmanın temel yolu importtur.

Import yönteminin temel akışı:

- Veri kaynağına bağlanılır.
- Power Query tarafında temizlik ve dönüşümler yapılır.
- Veri modele yüklenir.
- Tablolar arası ilişkiler kurulur.
- Ölçüler ve rapor görselleri oluşturulur.

### DirectQuery Yöntemi

DirectQuery yönteminde veri, Power BI dosyasının içine tamamen alınmaz. Rapor, veri kaynağına sorgu göndererek çalışır.

Bu yöntem daha çok SQL gibi düzenli veritabanı kaynaklarıyla çalışırken gündeme gelir.

Excel ve CSV gibi düz dosyalarda DirectQuery yerine import kullanılır.

### Import ve DirectQuery Arasındaki Temel Fark

Import yönteminde veri Power BI dosyasına alınır.

DirectQuery yönteminde veri kaynakta kalır ve rapor çalışırken kaynağa sorgu gönderilir.

Başlangıç seviyesinde öğrenme ve pratik yapma açısından import yöntemi daha anlaşılır ve daha yaygın kullanılır.

## 3. Power BI Dosyası ve Yayınlama Akışı

Power BI Desktop üzerinde çalışma tamamlandığında dosya PBIX uzantısıyla kaydedilir.

PBIX dosyası şunları içerir:

- Veri bağlantıları
- Power Query adımları
- Veri modeli
- İlişkiler
- Ölçüler
- Rapor sayfaları
- Görseller

### Publish Nedir?

Publish, Power BI Desktop'ta hazırlanan PBIX dosyasının PowerBI.com üzerindeki bir çalışma alanına gönderilmesidir.

Yayınlama sonrasında bulut tarafında genellikle iki temel yapı oluşur:

- Dataset veya semantic model
- Rapor

Videoda dataset ifadesi kullanılmaktadır. Güncel Power BI terminolojisinde bu yapı çoğu yerde semantic model olarak da geçer.

### Workspace Nedir?

Workspace, PowerBI.com tarafında raporların, modellerin ve ilgili içeriklerin tutulduğu çalışma alanıdır.

Bir rapor kendi kişisel çalışma alanına yayımlanabilir. Ayrıca ekiplerle ortak kullanılan başka çalışma alanlarına da yayımlanabilir.

Workspace, paylaşım ve yetkilendirme açısından önemlidir.

## 4. Rapor Paylaşımı

Power BI raporları kullanıcılarla iki ana yöntemle paylaşılabilir:

- Kullanıcıları workspace'e davet etmek
- Workspace üzerinden Power BI App oluşturmak

### Workspace Üzerinden Paylaşım

Kullanıcılar çalışma alanına davet edilerek farklı yetkiler alabilir.

Örnek roller:

- Viewer: Raporları görüntüleyebilir.
- Contributor: Rapor veya içerik üzerinde katkı sağlayabilir.
- Member: Çalışma alanında daha geniş yönetim ve düzenleme yetkilerine sahip olabilir.

Sadece raporları izleyecek kullanıcılar için Viewer yetkisi yeterlidir.

Raporları düzenlemesi veya geliştirmesi gereken kişilere Contributor veya Member gibi roller verilebilir.

### Power BI App ile Paylaşım

Kullanıcı sayısı arttıkça raporları tek tek workspace yetkisi vererek paylaşmak yönetimsel olarak zorlaşabilir.

Bu durumda Power BI App kullanmak daha avantajlı olabilir.

Power BI App, çalışma alanındaki raporları daha kontrollü ve paketlenmiş bir şekilde son kullanıcılara sunmak için kullanılır.

## 5. Gateway Mantığı

Power BI raporları bulutta yayımlandığında, veri kaynaklarıyla bağlantı meselesi önem kazanır.

Eğer kullanılan veri kaynakları tamamen buluttaysa gateway kurmaya gerek olmayabilir.

Bulut veri kaynaklarına örnekler:

- OneDrive
- SharePoint
- OData
- Bulut tabanlı servisler

Ancak veri kaynağı şirket ağı içinde veya yerel ortamdaysa gateway gerekir.

Yerel veri kaynaklarına örnekler:

- Şirket içindeki SQL Server
- Ağ klasöründeki Excel dosyası
- Yerel CSV dosyası
- On-premise ERP sistemi

### Gateway Ne İşe Yarar?

Gateway, PowerBI.com bulut servisi ile yerel veri kaynakları arasında köprü görevi görür.

Örneğin rapor bulutta yayımlanmıştır fakat veri şirket içindeki bir SQL Server'dan gelmektedir. PowerBI.com bu SQL Server'a doğrudan ulaşamaz. Bu durumda veri kaynağını görebilen bir makineye gateway kurulur.

Gateway ayarları bulut tarafında tanımlanır. Daha sonra Power BI, belirlenen zamanlarda gateway üzerinden yerel veri kaynağına erişir ve rapordaki veriyi yeniler.

### Gateway Gerekliliği İçin Kural

Modelde en az bir tane on-premise veri kaynağı varsa gateway ihtiyacı doğar.

Modeldeki tüm kaynaklar buluttaysa gateway gerekmeyebilir.

## 6. Power BI Raporlarına Erişim

PowerBI.com üzerinde yayımlanan raporlara kullanıcılar iki şekilde erişebilir:

- Web tarayıcısı üzerinden
- Power BI mobil uygulaması üzerinden

Web tarayıcısı olarak Chrome, Edge veya benzeri standart tarayıcılar kullanılabilir.

Mobil tarafta ise Power BI'ın Android ve iOS uygulamaları üzerinden raporlar görüntülenebilir.

## 7. Power BI Desktop Kurulumu

Power BI Desktop iki temel yöntemle kurulabilir:

- Microsoft Store üzerinden
- Power BI web sitesi üzerinden kurulum dosyası indirerek

### Microsoft Store Üzerinden Kurulum

Microsoft Store'da Power BI Desktop aranarak uygulama kurulabilir.

Bu yöntem pratik ve tercih edilebilir bir yöntemdir. Çünkü Microsoft Store üzerinden kurulan Power BI Desktop kendisini otomatik olarak güncelleyebilir.

### Web Sitesinden İndirme

Power BI Desktop, Microsoft'un Power BI indirme sayfasından da indirilebilir.

Bu yöntemde genellikle 64 bit kurulum dosyası indirilir. Kurulum dosyası çalıştırılır ve klasik "next next" mantığıyla kurulum tamamlanır.

### İlgili Uygulamalar

Microsoft Store'da Power BI arandığında birden fazla uygulama görülebilir:

- Power BI Desktop: Rapor ve model geliştirme uygulaması
- Power BI mobil uygulaması: Raporlara mobil erişim için
- Power BI Report Builder: Paginated report hazırlamak için

Bu notlarda odak Power BI Desktop üzerindedir.

## 8. Power BI Desktop Arayüzü

Power BI Desktop açıldığında karşımıza boş bir rapor kanvası çıkar.

Bu beyaz alan, rapor sayfalarını ve görselleri oluşturacağımız ana çalışma alanıdır.

### Kullanıcı Hesabıyla Oturum Açma

Power BI Desktop içinde kullanıcı hesabıyla oturum açmak önemlidir.

Çünkü model publish edildiğinde doğru tenant ve doğru kullanıcı hesabı altında yayımlanması gerekir.

### Rapor Kanvası

Rapor kanvası, görsellerin yerleştirildiği ana beyaz alandır.

Bir veri modeline bağlı birden fazla rapor sayfası oluşturulabilir.

Sayfalar alttaki sekmeler üzerinden yönetilir. Yeni sayfalar eklenebilir, mevcut sayfalar yeniden adlandırılabilir.

### Ribbon Menü

Üst taraftaki ribbon menü, Microsoft Office uygulamalarındaki menü yapısına benzer.

Power BI bazen "data için PowerPoint" gibi konumlandırılır. Bu ifade, rapor sayfalarının görsel olarak tasarlanmasına gönderme yapar. Fakat Power BI yalnızca görsel tasarım aracı değildir; veri modeli ve ETL tarafı da kritik öneme sahiptir.

### Visualizations Paneli

Sağ tarafta rapor oluştururken kullanılabilecek görsellerin listesi bulunur.

Standart görseller arasında tablo, matris, çubuk grafik, çizgi grafik, kart, harita ve benzeri görseller yer alır.

Bir görsel seçildiğinde, görselin alanları Visualizations panelindeki ilgili bölümlere yerleştirilir.

### Data veya Fields Paneli

Veri kaynaklarına bağlandıktan sonra sağ tarafta tablolar ve sütunlar listelenir.

Bu panelde:

- Tablolar
- Sütunlar
- Ölçüler
- Gizlenmiş veya görünür alanlar

takip edilebilir.

## 9. Power BI Desktop Görünümleri

Sol tarafta üç temel görünüm ikonu bulunur:

- Report View
- Data View
- Model View

### Report View

Report View, rapor sayfalarının ve görsellerin tasarlandığı görünümdür.

Kanvas, görsel listesi ve alan panelleri bu bölümde aktif şekilde kullanılır.

### Data View

Data View, modele yüklenen tabloların ve sütunların içeriğini incelemek için kullanılır.

Veri yüklendikten sonra satır sayıları, sütunlar ve sütunlardaki değerler burada görülebilir.

### Model View

Model View, tablolar arasındaki ilişkilerin kurulduğu ve incelendiği bölümdür.

Power BI'da sağlıklı bir model için Model View çok önemlidir. Tablolar arasındaki ilişkiler, raporların doğru hesaplama yapmasını sağlar.

## 10. Get Data ile Veri Kaynağına Bağlanma

Power BI'da her şey veriyle başlar.

Home sekmesinde Excel workbook, SQL Server gibi sık kullanılan veri kaynakları doğrudan görülebilir.

Daha kapsamlı veri kaynağı listesi için Get Data > More seçeneği kullanılır.

Power BI çok sayıda bağlayıcı destekler. Videoda örnek olarak Excel workbook kullanılmıştır.

### Excel Dosyasına Bağlanma Akışı

Temel akış şöyledir:

- Get Data seçilir.
- Excel workbook seçilir.
- Dosyanın bulunduğu konum gösterilir.
- Dosya açılır.
- Excel içindeki sayfalar veya tablolar listelenir.
- Veri kontrol edilir.
- Gerekirse Transform Data ile Power Query'e geçilir.

Veri temizliği veya dönüşüm gerekiyorsa doğrudan Load demek yerine Transform Data seçilmelidir.

## 11. Power Query ve ETL Mantığı

Power Query, Power BI Desktop'ın ETL katmanıdır.

ETL şu kavramların kısaltmasıdır:

- Extract: Veriyi kaynaktan alma
- Transform: Veriyi temizleme ve dönüştürme
- Load: Veriyi modele yükleme

Power Query ekranında üç temel alan vardır:

- Sol tarafta Queries paneli
- Ortada veri ön izleme grid'i
- Sağ tarafta Applied Steps paneli

### Queries Paneli

Queries paneli, bağlanılan veri kaynaklarını ve sorguları gösterir.

Her tablo veya sorgu burada ayrı bir öğe olarak görünür.

### Veri Ön İzleme Grid'i

Ortadaki grid, Excel'e benzeyen bir veri ön izleme alanıdır.

Bağlanılan veri kaynağındaki sütunlar ve satırlar burada incelenebilir.

### Applied Steps Paneli

Applied Steps, veri üzerinde yapılan işlemleri adım adım kaydeder.

Bu panel bir tür makro kaydedici gibi düşünülebilir.

Örneğin:

- Kaynağa bağlanma
- İlk satırı başlık yapma
- Veri tiplerini değiştirme
- Satır filtreleme
- Sütun kaldırma
- Değer değiştirme

gibi işlemler burada adım olarak tutulur.

Her adım silinebilir, yeniden düzenlenebilir veya bazı durumlarda araya yeni adım eklenebilir.

### M Dili

Power Query arka planda M dili ile çalışır.

Arayüzden yapılan işlemler M koduna dönüştürülür. Formül çubuğu açıldığında seçili adımın arka plandaki M ifadesi görülebilir.

Başlangıç aşamasında M dilini bilmek zorunlu değildir. Ancak Power Query'in yaptığı işlemleri anlamak için formül çubuğunu takip etmek faydalıdır.

## 12. Power Query Read-Only Çalışır

Power Query'in önemli özelliklerinden biri kaynak veriyi doğrudan değiştirmemesidir.

Örneğin Excel dosyasından yalnızca satış faturaları filtrelenirse, Excel dosyasındaki diğer satırlar silinmez.

Power Query yalnızca modelin veriyi hangi şekilde göreceğini tanımlar.

Bu nedenle yapılan filtreleme, temizleme ve dönüşümler kaynak dosyayı bozmaz.

### Örnek

Kaynak Excel dosyasında farklı belge tipleri olsun.

Sadece satış faturaları rapora alınmak isteniyorsa belge tipi sütunu filtrelenir.

Bu işlem Excel dosyasındaki diğer belge tiplerini silmez. Sadece Power BI modeline girecek veri görünümünü değiştirir.

## 13. Power Query'de Temel İşlemler

Power Query'de dönüşümler farklı yerlerden yapılabilir:

- Üst ribbon menülerinden
- Sütun başlığına sağ tıklayarak
- Hücre veya değer üzerinden ilgili komutları kullanarak

Temel işlemler:

- Sütun yeniden adlandırma
- Gereksiz sütunları kaldırma
- Satır filtreleme
- Değer değiştirme
- Veri tipini değiştirme
- İlk satırı başlık olarak kullanma
- Tekrarlı kayıtları kaldırma

### İsimlendirme Best Practice'i

ERP veya kurumsal sistemlerden gelen tablo ve sütun isimleri son kullanıcı için anlaşılmaz olabilir.

Örneğin teknik bir tablo adı veya kısaltma son kullanıcı açısından anlamlı değildir.

Bu nedenle tablo ve sütun adları kullanıcıların anlayacağı şekilde düzenlenmelidir.

Örnek:

- F_Satislar yerine Satışlar
- SatisTutarTL yerine Satış Tutarı TL
- MusteriSinif yerine Müşteri Sınıfı

Bu düzenleme hem raporu hazırlayan kişinin hem de son kullanıcının konforunu artırır.

### Applied Steps Adlandırması

Power Query çok sayıda adım üretebilir.

Özellikle karmaşık dönüşümlerde adımların ne yaptığını anlamak zorlaşabilir.

Bu nedenle önemli adımlar anlaşılır şekilde yeniden adlandırılabilir.

Örnek:

- Filtered Rows yerine Sadece Satış Faturaları
- Removed Columns yerine Gereksiz Sütunlar Kaldırıldı
- Renamed Columns yerine Rapor İsimleri Düzenlendi

## 14. Close & Apply

Power Query'de dönüşümler tamamlandıktan sonra Close & Apply seçilir.

Bu işlem Power Query ekranını kapatır ve son haliyle seçilen tabloları Power BI Desktop modeline yükler.

Import yöntemi kullanılıyorsa, tablolar Power BI dosyasının içine alınır.

Close & Apply sonrasında tablolar Data View ve Fields panelinde görünür hale gelir.

## 15. Flat Tablo Problemi

Videoda Excel'den gelen satış verisi örneği üzerinden flat tablo problemi anlatılmaktadır.

Flat tablo, her şeyin tek tabloda tutulduğu geniş tablodur.

Örneğin bir satış tablosunda şu bilgiler aynı satırlarda tekrar ediyor olabilir:

- Ürün ID
- Ürün adı
- Ürün kategorisi
- Müşteri ID
- Müşteri adı
- Müşteri sınıfı
- Satış sorumlusu
- Satış yöneticisi
- Satış tutarı
- Belge tipi

Excel pivot tablo açısından bu yapı kısa vadede çalışıyor gibi görünebilir.

Fakat Power BI veri modeli açısından bu tasarım sağlıklı değildir.

Çünkü Power BI'da doğru modelleme için hareket tabloları ve boyut tabloları ayrıştırılmalıdır.

## 16. Fact Tablosu ve Dimension Tablosu

Power BI veri modelinde iki temel tablo türü sık kullanılır:

- Fact tablo
- Dimension tablo

### Fact Tablosu

Fact tablo, hareket veya işlem tablosudur.

Satışlar tablosu buna örnektir.

Fact tabloda genellikle şu bilgiler yer alır:

- İşleme ait ölçülebilir değerler
- Tarih veya işlem zamanı
- İlgili entity'lerin ID sütunları

Örneğin satışlar fact tablosunda müşteri adı, müşteri sınıfı, ürün adı veya ürün kategorisi gibi açıklayıcı bilgiler yer almamalıdır.

Bunların yerine müşteri ID ve ürün ID gibi anahtar sütunlar bulunmalıdır.

### Dimension Tablosu

Dimension tablo, açıklayıcı özellikleri tutan master tablodur.

Örneğin:

- Müşteriler tablosu
- Ürünler tablosu
- Tarih tablosu
- Bölge tablosu

Müşteriler tablosunda müşteri ID tekil olmalıdır. Aynı müşteri ID yalnızca bir kez geçmelidir.

Bu tablodaki diğer sütunlar müşteriyle ilgili açıklayıcı bilgilerdir:

- Müşteri adı
- Müşteri sınıfı
- Satış sorumlusu
- Satış yöneticisi

Ürünler tablosunda da ürün ID tekil olmalıdır.

Ürünle ilgili açıklayıcı bilgiler bu tabloda tutulur:

- Ürün adı
- Ürün kategorisi
- Ürün sınıfı
- Marka

## 17. One-to-Many İlişki Mantığı

Power BI veri modelinde fact tablo ile dimension tablo genellikle one-to-many ilişkisiyle bağlanır.

Örneğin:

- Müşteriler tablosunda müşteri ID bir kez geçer.
- Satışlar tablosunda aynı müşteri ID birçok kez geçebilir.

Bu nedenle ilişki:

Müşteriler[Customer ID] 1 -> * Satışlar[Customer ID]

şeklindedir.

Aynı mantık ürünler için de geçerlidir:

Ürünler[Product ID] 1 -> * Satışlar[Product ID]

One tarafı dimension tablodur. Many tarafı fact tablodur.

## 18. Flat Tabloyu Modele Uygun Hale Getirme

Videoda tek bir satış tablosundan modellemeye uygun üç tablo oluşturulmaktadır:

- Satışlar
- Müşteriler
- Ürünler

### Müşteriler Tablosu Oluşturma

Satış verisi tekrar Power Query'e alınır veya mevcut sorgudan referans/çoğaltma mantığıyla yeni bir sorgu hazırlanır.

Müşteriler tablosu için yalnızca müşteriyle ilgili sütunlar seçilir:

- Müşteri ID
- Müşteri adı
- Müşteri sınıfı
- Satış sorumlusu
- Satış yöneticisi

Daha sonra müşteri ID üzerinde tekrarlı değerler kaldırılır.

Böylece her müşteri ID'nin tekil olduğu bir müşteri dimension tablosu oluşur.

### Ürünler Tablosu Oluşturma

Benzer şekilde ürün dimension tablosu oluşturulur.

Ürünler tablosu için ürünle ilgili sütunlar seçilir:

- Ürün ID
- Ürün adı
- Ürün kategorisi
- Ürün sınıfı
- Marka

Ürün ID üzerinde tekrarlı değerler kaldırılır.

Böylece her ürünün yalnızca bir kez geçtiği ürün master tablosu oluşur.

### Satışlar Fact Tablosunu Düzenleme

Satışlar tablosunda müşteri ve ürünle ilgili açıklayıcı sütunlar kaldırılır.

Satışlar tablosunda kalması gereken temel yapı:

- Müşteri ID
- Ürün ID
- Satış tutarı
- İşleme ait diğer ölçü veya tarih alanları

Müşteri adı, müşteri sınıfı, satış sorumlusu, ürün adı veya marka gibi alanlar fact tabloda tutulmaz. Bu bilgiler ilgili dimension tablolarda tutulur.

## 19. Model View'da İlişkileri Kurma

Tablolar Power BI modeline yüklendikten sonra Model View'a geçilir.

Model View'da satışlar, müşteriler ve ürünler tabloları görülür.

Power BI bazı ilişkileri otomatik kurabilir. Ancak videoda ilişkilerin otomatik kurulumuna güvenmek yerine elle ve bilinçli şekilde kurulması önerilmektedir.

### Otomatik İlişki Algılama

Power BI, tablo ve sütun adlarına bakarak ilişki kurmaya çalışabilir.

Ancak ilişkiler veri modelinin kalbidir. Bu nedenle özellikle öğrenme ve kontrollü modelleme aşamasında otomatik ilişki algılama kapatılabilir.

İlgili ayar yolu:

File > Options and settings > Options > Current file > Data Load

Bu bölümde otomatik yeni ilişki algılama seçenekleri kapatılabilir.

### İlişki Kurma

Müşteriler tablosundaki Müşteri ID, Satışlar tablosundaki Müşteri ID ile ilişkilendirilir.

Ürünler tablosundaki Ürün ID, Satışlar tablosundaki Ürün ID ile ilişkilendirilir.

Sütun adlarının birebir aynı olması şart değildir. Önemli olan bir tarafta tekil değerlerin, diğer tarafta çoklu değerlerin bulunmasıdır.

## 20. Veri Modeli Yerleşimi

Model View büyüdükçe tablo yerleşimi önem kazanır.

Kullanılabilecek iki pratik yaklaşım:

- Fact tabloları altta, dimension tabloları üstte tutmak
- Fact tabloyu ortaya alıp dimension tabloları etrafına yerleştirmek

Satış modeli örneğinde Satışlar fact tablosu merkeze, Müşteriler ve Ürünler dimension tabloları çevresine yerleştirilebilir.

Bu yapı yıldız şemaya benzer ve modelin okunabilirliğini artırır.

## 21. İlk Rapor Görselini Oluşturma

Report View'a dönüldüğünde artık model üzerinden görseller oluşturulabilir.

Görsel oluşturmanın iki temel yolu vardır:

- Sağdaki alanlardan bir sütunu kanvasa sürüklemek
- Önce görsel türünü seçip sonra alanları ilgili bölümlere yerleştirmek

Örneğin bir matris görselinde:

- Satır alanına müşteri sınıfı
- Sütun alanına ürün kategorisi
- Değer alanına satış tutarı

eklenebilir.

Bu mantık Excel pivot tabloya benzer. Ancak Power BI'da asıl güç, düzgün veri modeli ve ölçülerle birlikte ortaya çıkar.

## 22. Görsel Alanları ve Paneller

Bir görsel seçildiğinde Visualizations panelinde farklı alanlar görünür.

Bu alanlar görsel türüne göre değişebilir.

Örneğin:

- Axis
- Legend
- Values
- Rows
- Columns
- Tooltips

Bir matris görselinde satır, sütun ve değer alanları kullanılır.

Bir grafik görselinde eksen, açıklama ve değer alanları öne çıkar.

### Format Paneli

Format paneli, görselin görünüm ayarlarını düzenlemek için kullanılır.

Örnek ayarlar:

- Renkler
- Başlık
- Veri etiketleri
- Font ayarları
- Kenarlık ve arka plan
- Görsel başlıkları

### Analytics Paneli

Analytics paneli, seçili görsel türüne göre farklı analitik seçenekler sunabilir.

Bazı görsellerde bu panel daha dolu, bazı görsellerde daha sınırlı olabilir.

Örneğin çizgi grafiklerde trend çizgisi veya referans çizgisi gibi seçenekler görülebilir.

## 23. Görsellerde Hangi Tablo Kullanılmalı?

Doğru model kurulduktan sonra görsellerde alan seçimi önemlidir.

Son kullanıcıya gösterilecek açıklayıcı alanlar dimension tablolardan gelmelidir.

Örneğin:

- Müşteri adı
- Müşteri sınıfı
- Satış yöneticisi
- Ürün adı
- Ürün kategorisi

gibi alanlar Müşteriler veya Ürünler tablosundan kullanılmalıdır.

Satışlar fact tablosundaki müşteri ID ve ürün ID gibi anahtar alanlar genellikle son kullanıcıdan gizlenmelidir.

### Neden Fact Tablosundaki ID Alanları Gizlenir?

Fact tablodaki ID sütunları ilişki kurmak için gereklidir.

Ancak rapor kullanıcısı için çoğu zaman anlamlı değildir.

Eğer kullanıcı müşteri veya ürün bazında analiz yapacaksa, dimension tablodaki açıklayıcı alanları kullanmalıdır.

Bu nedenle fact tablodaki foreign key sütunları hide edilebilir.

## 24. Hiyerarşi Mantığı

Bir görselin satır veya sütun alanına birden fazla alan eklenirse hiyerarşi oluşabilir.

Örneğin matris görselinde:

- Satış yöneticisi
- Müşteri ID

aynı alana eklendiğinde kullanıcı yukarı-aşağı oklarla hiyerarşi içinde gezinebilir.

Bu yapı drill-down ve drill-up mantığıyla çalışır.

Kullanıcı üst seviyeden alt seviyeye inebilir veya tekrar üst seviyeye dönebilir.

## 25. İlk PBIX Dosyasının Mantıksal Özeti

Videonun sonunda yapılan çalışma şu noktaya gelir:

- Power BI Desktop kurulmuştur.
- Excel dosyasına bağlanılmıştır.
- Power Query'de basit ETL yapılmıştır.
- Flat satış tablosu modellemeye uygun hale getirilmiştir.
- Müşteriler ve Ürünler dimension tabloları oluşturulmuştur.
- Satışlar fact tablosu düzenlenmiştir.
- Tablolar arasında one-to-many ilişkiler kurulmuştur.
- Basit bir rapor sayfası oluşturulmuştur.
- PBIX dosyası kaydedilmeye hazır hale gelmiştir.

Bu aşamada çalışma hâlâ Power BI Desktop tarafındadır.

Bir sonraki adım bu dosyayı PowerBI.com tarafına publish etmek ve raporu bulutta paylaşılabilir hale getirmektir.

## 26. Uçtan Uca Power BI Akışı

Power BI'da temel akış aşağıdaki gibi özetlenebilir:

1. Veri kaynağına bağlan.
2. Power Query ile veriyi temizle ve dönüştür.
3. Gereksiz sütunları kaldır.
4. Tablo ve sütun adlarını kullanıcı dostu hale getir.
5. Flat tabloları fact ve dimension mantığına göre ayır.
6. Dimension tablolarda anahtar sütunları tekilleştir.
7. Fact tabloda yalnızca işlem ölçüleri ve foreign key alanlarını bırak.
8. Model View'da ilişkileri elle ve bilinçli şekilde kur.
9. Rapor görsellerini oluştur.
10. Fact tablodaki teknik ID alanlarını son kullanıcıdan gizle.
11. PBIX dosyasını kaydet.
12. PowerBI.com'a publish et.
13. Workspace veya App ile kullanıcılarla paylaş.
14. Gerekirse gateway ve scheduled refresh ayarlarını yap.

## 27. Temel Kavramlar

### Power BI Desktop

Rapor geliştirme, veri hazırlama ve modelleme için kullanılan masaüstü uygulamasıdır.

### PowerBI.com

Raporların yayımlandığı, paylaşıldığı ve yönetildiği bulut servisidir.

### PBIX

Power BI Desktop dosya uzantısıdır.

### Power Query

Veriyi alma, temizleme ve dönüştürme aracıdır.

### ETL

Extract, Transform, Load sürecidir.

### Fact Tablo

Hareket veya işlem tablosudur. Satışlar gibi ölçülebilir olayları içerir.

### Dimension Tablo

Fact tabloyu açıklayan master tablodur. Müşteriler ve Ürünler gibi varlıkları içerir.

### One-to-Many İlişki

Bir dimension tablodaki tekil anahtarın fact tabloda birçok kez geçmesiyle oluşan ilişkidir.

### Workspace

PowerBI.com üzerinde rapor, model ve içeriklerin tutulduğu çalışma alanıdır.

### Gateway

Buluttaki Power BI servisi ile yerel veri kaynakları arasında bağlantı sağlayan köprüdür.

## 28. Önemli Best Practice'ler

Power BI öğrenirken aşağıdaki alışkanlıklar erken aşamada kazanılmalıdır:

- Veriyi doğrudan rapora sürüklemeden önce model yapısını düşün.
- Flat tablolarla çalışıyorsan fact ve dimension ayrımını yap.
- Dimension tablolarda anahtar sütunları tekil hale getir.
- Fact tablolarda açıklayıcı attribute sütunlarını tutma.
- Kullanıcıya gösterilecek alanları dimension tablolardan kullan.
- Fact tablodaki teknik ID sütunlarını gizle.
- Power Query adımlarını takip et.
- Karmaşık dönüşümlerde Applied Steps adlarını anlamlı hale getir.
- Tablo ve sütun isimlerini son kullanıcının anlayacağı dile çevir.
- İlişkileri otomatik oluşmuş varsaymak yerine Model View'da kontrol et.
- Rapor paylaşımına geçmeden önce veri yenileme ve gateway ihtiyacını düşün.

### Sonuç

Power BI'da başarılı rapor geliştirme yalnızca görsel seçmekten ibaret değildir.

Sağlıklı bir Power BI çalışması; doğru veri alma, temizleme, modelleme, ilişki kurma, görselleştirme ve paylaşım adımlarından oluşur.

Power BI Desktop bu sürecin geliştirme merkezidir. PowerBI.com ise geliştirilen raporların yayımlandığı, paylaşıldığı ve kurumsal kullanım için yönetildiği platformdur.

Bu iki videoda öğrenilen temel fikir şudur:

Önce veriyi doğru modele dönüştür, sonra raporu oluştur.

Model doğru kurulmadığında görseller ilk bakışta çalışıyor gibi görünse bile, rapor karmaşıklaştıkça hesaplama, filtreleme ve bakım problemleri ortaya çıkar.

Bu nedenle Power BI öğrenirken ilk odak noktası, veri modelinin mantığını anlamak olmalıdır.
