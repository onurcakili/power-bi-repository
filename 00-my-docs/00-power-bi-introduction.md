# Power BI'ye Giriş

## 1. Genel Bakış

Power BI, veriyi farklı kaynaklardan alıp temizleme, modelleme, analiz etme, görselleştirme ve kullanıcılarla paylaşma sürecini uçtan uca yönetebilen bir iş zekâsı platformudur.

Power BI öğrenirken yalnızca görsel oluşturmayı değil, veri kaynağından rapor paylaşımına kadar olan bütün akışı anlamak gerekir. 
İyi bir Power BI raporu, arka planda doğru kurgulanmış bir veri modeli ve sürdürülebilir bir veri yenileme yapısı üzerine kurulur.

Bu notlarda sırasıyla şu konular ele alınmaktadır:

- Power BI ekosisteminin genel topolojisi ve bileşenleri
- Power BI Desktop'ın kurulumu ve arayüzü
- Veri kaynaklarına bağlanma yöntemleri (Import / DirectQuery)
- Power Query ile ETL (Extract–Transform–Load) süreci
- Veri modelleme mantığı: fact ve dimension tabloları, ilişkiler
- Rapor görselleştirme
- PowerBI.com üzerinde yayımlama, paylaşım ve gateway yapısı

## 2. Power BI Ekosistemi

Power BI ekosistemi genel olarak üç ana bileşen üzerinden düşünülebilir:

- **Veri Kaynakları (Data Source):** Excel, CSV, SQL Server, farklı veritabanları, OneDrive, SharePoint, OData (Open Data Protocol) veya kurumsal sistemler.
- **Power BI Desktop:** Rapor ve veri modelinin geliştirildiği masaüstü uygulaması.
- **PowerBI.com (Cloud Service):** Geliştirilen modelin ve raporların yayımlandığı, paylaşıldığı ve zamanlanmış veri yenileme gibi işlemlerin yönetildiği bulut servisi.

### Power BI Desktop'ın İç Yapısı

Power BI Desktop dışarıdan tek bir uygulama gibi görünse de kendi içinde üç temel katman barındırır:

1. **ETL katmanı:** Veri kaynaklarına bağlanıp veriyi temizlediğimiz, dönüştürdüğümüz ve raporlamaya uygun hale getirdiğimiz katmandır. 
Bu işlem Power Query (M Query) ile yapılır.

2. **Veri modeli katmanı:** Tablolar arasındaki ilişkilerin kurulduğu, ölçülerin hazırlandığı ve analitik yapının temelinin oluşturulduğu katmandır.

3. **Raporlama katmanı:** Kullanıcıların göreceği görsellerin, sayfaların, tabloların, grafiklerin ve filtrelerin hazırlandığı katmandır.

Bu nedenle Power BI Desktop yalnızca bir görselleştirme aracı olarak düşünülmemelidir; 
- veri hazırlama,
- modelleme,
- raporlama süreçlerinin tamamı burada başlar.

## 3. Power BI Desktop Kurulumu

Power BI Desktop iki temel yöntemle kurulabilir:

- **Microsoft Store üzerinden:** Pratik ve tercih edilen bir yöntemdir; bu şekilde kurulan uygulama kendini otomatik olarak günceller.
- **Power BI web sitesinden indirerek:** Genellikle 64 bit kurulum dosyası indirilir ve klasik "next next" mantığıyla kurulum tamamlanır.

Microsoft Store'da Power BI aratıldığında birden fazla ilgili uygulama görülebilir:

- **Power BI Desktop:** Rapor ve model geliştirme uygulaması.
- **Power BI mobil uygulaması:** Raporlara mobil erişim için.
- **Power BI Report Builder:** Paginated report hazırlamak için.

Bu notların odağı Power BI Desktop üzerindedir.

## 4. Power BI Desktop Arayüzü

Power BI Desktop açıldığında karşımıza boş bir rapor kanvası çıkar; bu, rapor sayfalarının ve görsellerin oluşturulacağı ana çalışma alanıdır.

Uygulama içinde kullanıcı hesabıyla oturum açmak önemlidir, çünkü model publish edildiğinde doğru tenant ve doğru kullanıcı hesabı altında yayımlanması gerekir.

Arayüzün temel bileşenleri:

- **Rapor Kanvası:** Görsellerin yerleştirildiği ana alan. 
Bir veri modeline bağlı birden fazla rapor sayfası oluşturulabilir; sayfalar alttaki sekmelerden yönetilir.

- **Ribbon Menü:** Microsoft Office uygulamalarındaki menü yapısına benzer. 
Power BI bazen "Data for PowerPoint" gibi konumlandırılsa da yalnızca görsel tasarım aracı değildir; veri modeli ve ETL tarafı da kritik öneme sahiptir.

- **Visualizations Paneli:** Rapor oluştururken kullanılabilecek görsellerin (tablo, matris, çubuk grafik, çizgi grafik, kart, harita vb.) listelendiği panel. Bir görsel seçildiğinde, ilgili alanlar bu panelde ilgili bölümlere yerleştirilir.

- **Data / Fields Paneli:** Veri kaynaklarına bağlandıktan sonra tabloların, sütunların, ölçülerin ve gizli/görünür alanların listelendiği panel.

### Görünümler (Views)

Sol tarafta üç temel görünüm ikonu bulunur:

- **Report View:** Rapor sayfalarının ve görsellerin tasarlandığı görünüm; kanvas, görsel listesi ve alan panelleri burada aktif olarak kullanılır.
- **Data View:** Modele yüklenen tabloların ve sütunların içeriğinin (satır sayısı, sütunlar, değerler) incelendiği görünüm.
- **Model View:** Tablolar arasındaki ilişkilerin kurulduğu ve incelendiği görünüm. Sağlıklı bir model için bu görünüm çok önemlidir; çünkü ilişkiler, raporların doğru hesaplama yapmasını sağlar.

## 5. Veri Kaynaklarına Bağlanma Yöntemleri

Power BI Desktop ile Excel, CSV, SQL veritabanları, OneDrive, SharePoint, OData servisleri veya kurumsal ERP/CRM sistemleri gibi farklı veri kaynaklarından veri okunabilir. OneDrive ve SharePoint üzerinde tutulan Excel dosyaları da bulut veri kaynağı olarak düşünülebilir.

Bağlantı için iki temel yöntem vardır: **Import** ve **DirectQuery**.

### Import Yöntemi

Import yönteminde veri, Power BI dosyasının içine alınır; raporlar bu içeri aktarılmış veri üzerinde çalışır. 
Özellikle Excel ve CSV gibi düz dosya kaynaklarında veriye bağlanmanın temel yolu importtur ve başlangıç senaryolarında en çok kullanılan yöntemdir.

Import yönteminin temel akışı:

1. Veri kaynağına bağlanılır.
2. Power Query tarafında temizlik ve dönüşümler yapılır.
3. Veri modele yüklenir.
4. Tablolar arası ilişkiler kurulur.
5. Ölçüler ve rapor görselleri oluşturulur.

### DirectQuery Yöntemi

DirectQuery yönteminde veri, Power BI dosyasının içine tamamen alınmaz; rapor, veri kaynağına sorgu göndererek çalışır. 
Bu yöntem daha çok SQL gibi düzenli veritabanı kaynaklarıyla kullanılır. 
Excel ve CSV gibi düz dosyalarda DirectQuery yerine import tercih edilir.

Başlangıç seviyesinde öğrenme ve pratik yapma açısından import yöntemi daha anlaşılır ve daha yaygındır.

### Get Data ile Bağlanma (Örnek: Excel)

Home sekmesinde Excel workbook, SQL Server gibi sık kullanılan veri kaynakları doğrudan görülebilir; daha kapsamlı bir liste için **Get Data > More** seçeneği kullanılır.

Excel dosyasına bağlanma akışı:

1. Get Data seçilir.
2. Excel workbook seçilir.
3. Dosyanın konumu gösterilir ve dosya açılır.
4. Excel içindeki sayfalar veya tablolar listelenir.
5. Veri kontrol edilir.
6. Gerekirse **Transform Data** ile Power Query'e geçilir.

Veri temizliği veya dönüşüm gerekiyorsa doğrudan **Load** yerine **Transform Data** seçilmelidir.

## 6. Power Query ve ETL Süreci

Power Query, Power BI Desktop'ın ETL katmanıdır. 

ETL kısaltması şu adımları ifade eder:

- **Extract:** Veriyi kaynaktan alma.
- **Transform:** Veriyi temizleme ve dönüştürme.
- **Load:** Veriyi modele yükleme.

Power Query ekranında üç temel alan bulunur:

- **Queries Paneli (sol):** Bağlanılan veri kaynaklarını ve sorguları listeler; her tablo/sorgu ayrı bir öğe olarak görünür.
- **Veri Ön İzleme Grid'i (orta):** Excel'e benzeyen, bağlanılan kaynaktaki sütun ve satırların incelendiği alan.
- **Applied Steps Paneli (sağ):** Veri üzerinde yapılan işlemleri (kaynağa bağlanma, ilk satırı başlık yapma, veri tipi değiştirme, satır filtreleme, sütun kaldırma, değer değiştirme vb.) adım adım kaydeden, bir tür makro kaydedici gibi çalışan panel. Her adım silinebilir, yeniden düzenlenebilir veya araya yeni adım eklenebilir.

Arka planda tüm işlemler **M dili**ne dönüştürülür; formül çubuğu açıldığında seçili adımın M ifadesi görülebilir. 
Başlangıç aşamasında M dilini bilmek zorunlu değildir, ancak formül çubuğunu takip etmek Power Query'nin yaptığı işlemleri anlamak için faydalıdır.

### Power Query'nin Read-Only Çalışması

Power Query'nin önemli bir özelliği, kaynak veriyi doğrudan değiştirmemesidir; yalnızca modelin veriyi hangi şekilde göreceğini tanımlar. 
Örneğin bir Excel dosyasından yalnızca satış faturaları filtrelendiğinde, dosyadaki diğer belge tipleri silinmez — yalnızca Power BI modeline girecek veri görünümü değişir.

### Temel İşlemler ve İsimlendirme Best Practice'leri

Dönüşümler ribbon menülerinden, sütun başlığına sağ tıklayarak veya ilgili hücre/değer üzerinden yapılabilir. 
Başlıca işlemler: sütun yeniden adlandırma, gereksiz sütunları kaldırma, satır filtreleme, değer değiştirme, veri tipini değiştirme, ilk satırı başlık olarak kullanma, tekrarlı kayıtları kaldırma.

ERP veya kurumsal sistemlerden gelen tablo ve sütun isimleri son kullanıcı için anlaşılmaz olabilir; bu nedenle isimler kullanıcı dostu hale getirilmelidir. Örnek:

| Teknik İsim | Kullanıcı Dostu İsim |
|---|---|
| F_Satislar | Satışlar |
| SatisTutarTL | Satış Tutarı TL |
| MusteriSinif | Müşteri Sınıfı |

Aynı mantık Applied Steps adımları için de geçerlidir; karmaşık dönüşümlerde önemli adımlar anlaşılır şekilde yeniden adlandırılmalıdır. 
Örnek: `Filtered Rows` → `Sadece Satış Faturaları`, `Removed Columns` → `Gereksiz Sütunlar Kaldırıldı`.

### Close & Apply

Dönüşümler tamamlandıktan sonra **Close & Apply** seçilir. 
Bu işlem Power Query ekranını kapatır ve seçilen tabloları son haliyle Power BI Desktop modeline yükler 
(Import yönteminde tablolar dosyanın içine alınır). 
İşlem sonrasında tablolar Data View ve Fields panelinde görünür hale gelir.

## 7. Veri Modelleme

### Flat Tablo Problemi

Tek bir kaynaktan (örneğin Excel'den) gelen satış verisi genellikle **flat tablo** biçimindedir: 
ürün ID, ürün adı, ürün kategorisi, müşteri ID, müşteri adı, müşteri sınıfı, satış sorumlusu, satış tutarı gibi 
tüm bilgilerin tek, geniş bir tabloda tekrar ettiği yapıdır.

Bu yapı Excel pivot tablo açısından kısa vadede çalışıyor gibi görünse de, Power BI veri modeli açısından sağlıklı değildir; doğru modelleme için hareket (fact) ve boyut (dimension) tabloları ayrıştırılmalıdır.

### Fact ve Dimension Tabloları

- **Fact Tablo:** Hareket veya işlem tablosudur (örn. Satışlar). 
İşleme ait ölçülebilir değerleri, tarih/işlem zamanını ve ilgili varlıklara ait ID sütunlarını içerir. 
Müşteri adı, ürün kategorisi gibi açıklayıcı bilgiler fact tabloda yer almamalı; 
bunların yerine müşteri ID, ürün ID gibi anahtar sütunlar bulunmalıdır.

- **Dimension Tablo:** Açıklayıcı özellikleri tutan master tablodur (örn. Müşteriler, Ürünler, Tarih, Bölge). 
Anahtar sütun (örn. Müşteri ID) tekil olmalı, yalnızca bir kez geçmelidir; müşteri adı, müşteri sınıfı, satış sorumlusu gibi açıklayıcı sütunlar burada tutulur.

### One-to-Many İlişki Mantığı

Fact tablo ile dimension tablo genellikle **one-to-many** ilişkisiyle bağlanır: dimension tablodaki anahtar bir kez, fact tablodaki karşılığı ise birçok kez geçer.

```
Müşteriler[Customer ID]  1 -> *  Satışlar[Customer ID]
Ürünler[Product ID]      1 -> *  Satışlar[Product ID]
```

"One" tarafı dimension, "many" tarafı fact tablodur.

### Flat Tabloyu Modele Uygun Hale Getirme

Tek bir satış tablosundan modellemeye uygun üç tablo türetilebilir:

1. **Müşteriler tablosu:** Satış verisinden yalnızca müşteriyle ilgili sütunlar (Müşteri ID, adı, sınıfı, satış sorumlusu/yöneticisi) seçilip Müşteri ID üzerinde tekrarlı değerler kaldırılarak oluşturulur.

2. **Ürünler tablosu:** Aynı mantıkla yalnızca ürünle ilgili sütunlar (Ürün ID, adı, kategorisi, sınıfı, marka) seçilip Ürün ID üzerinde tekrarlı değerler kaldırılarak oluşturulur.

3. **Satışlar (fact) tablosu:** Müşteri ve ürünle ilgili açıklayıcı sütunlar kaldırılır; geriye Müşteri ID, Ürün ID, satış tutarı ve işleme ait diğer ölçü/tarih alanları bırakılır.

### Model View'da İlişkileri Kurma

Tablolar modele yüklendikten sonra Model View'a geçilir. Power BI bazı ilişkileri otomatik kurabilse de, özellikle öğrenme ve kontrollü modelleme aşamasında ilişkilerin **manuel ve bilinçli şekilde** kurulması önerilir; gerekirse otomatik ilişki algılama şu yoldan kapatılabilir:

`File > Options and settings > Options > Current file > Data Load`

İlişki kurarken sütun adlarının birebir aynı olması şart değildir; önemli olan bir tarafta tekil, diğer tarafta çoklu değerlerin bulunmasıdır (Müşteriler[Müşteri ID] ↔ Satışlar[Müşteri ID], Ürünler[Ürün ID] ↔ Satışlar[Ürün ID]).

Model büyüdükçe tablo yerleşimi de önem kazanır; yaygın iki yaklaşım fact tabloları altta / dimension tabloları üstte tutmak, ya da fact tabloyu ortaya alıp dimension tabloları çevresine yerleştirmektir. 
Bu ikinci yapı yıldız şemaya benzer ve modelin okunabilirliğini artırır.

## 8. Rapor Görselleştirme

Model kurulduktan sonra Report View'da görseller oluşturulur. 
İki temel yol vardır: bir sütunu doğrudan kanvasa sürüklemek, ya da önce görsel türünü seçip sonra alanları ilgili bölümlere yerleştirmek. 

Örneğin bir matris görselinde satır alanına müşteri sınıfı, sütun alanına ürün kategorisi, değer alanına satış tutarı eklenebilir — mantık Excel pivot tabloya benzer, ancak Power BI'ın gücü düzgün veri modeli ve ölçülerle ortaya çıkar.

Görsel seçildiğinde Visualizations panelinde görsel türüne göre değişen alanlar (Axis, Legend, Values, Rows, Columns, Tooltips vb.) görünür. 

Ek olarak:

- **Format Paneli:** Renkler, başlık, veri etiketleri, font, kenarlık/arka plan gibi görünüm ayarlarını düzenler.
- **Analytics Paneli:** Görsel türüne göre trend çizgisi, referans çizgisi gibi analitik seçenekler sunar.

### Görsellerde Hangi Tablo Kullanılmalı?

Son kullanıcıya gösterilecek açıklayıcı alanlar (müşteri adı, müşteri sınıfı, ürün adı, ürün kategorisi vb.) dimension tablolardan kullanılmalıdır. Satışlar fact tablosundaki müşteri ID / ürün ID gibi anahtar alanlar ilişki kurmak için gereklidir ama son kullanıcı için genellikle anlamlı değildir; bu nedenle bu foreign key sütunları hide edilebilir.

### Hiyerarşi Mantığı

Bir görselin satır veya sütun alanına birden fazla alan eklendiğinde hiyerarşi oluşur 
(örn. satış yöneticisi → müşteri ID)
Kullanıcı bu hiyerarşi içinde yukarı-aşağı oklarla **drill-down / drill-up** yapabilir; 
üst seviyeden alt seviyeye inebilir veya tekrar üst seviyeye dönebilir.

## 9. Dosya Kaydetme ve Yayımlama

### PBIX Dosyası

Power BI Desktop üzerindeki çalışma tamamlandığında dosya **PBIX** uzantısıyla kaydedilir. PBIX dosyası veri bağlantılarını, Power Query adımlarını, veri modelini, ilişkileri, ölçüleri, rapor sayfalarını ve görselleri içerir.

### Publish

**Publish**, Power BI Desktop'ta hazırlanan PBIX dosyasının PowerBI.com üzerindeki bir çalışma alanına gönderilmesidir. 
Yayınlama sonrasında bulutta genellikle iki temel yapı oluşur: **dataset (semantic model)** ve **rapor**.

### Workspace

**Workspace**, PowerBI.com tarafında raporların, modellerin ve ilgili içeriklerin tutulduğu çalışma alanıdır. 
Bir rapor kişisel çalışma alanına ya da ekiplerle ortak kullanılan bir çalışma alanına yayımlanabilir. Workspace, paylaşım ve yetkilendirme açısından önemlidir.

## 10. Rapor Paylaşımı

Power BI raporları iki ana yöntemle paylaşılabilir: kullanıcıları workspace'e davet etmek, ya da workspace üzerinden bir Power BI App oluşturmak.

### Workspace Üzerinden Paylaşım

Kullanıcılar çalışma alanına davet edilerek farklı yetkiler alabilir:

- **Viewer:** Yalnızca raporları görüntüleyebilir.
- **Contributor:** Rapor veya içerik üzerinde katkı sağlayabilir.
- **Member:** Çalışma alanında daha geniş yönetim ve düzenleme yetkilerine sahiptir.

Sadece izleyecek kullanıcılar için Viewer yeterlidir; düzenleme/geliştirme yapacak kişilere Contributor veya Member gibi roller verilebilir.

### Power BI App ile Paylaşım

Kullanıcı sayısı arttıkça raporları tek tek workspace yetkisiyle paylaşmak yönetimsel olarak zorlaşabilir. 
Bu durumda **Power BI App**, çalışma alanındaki raporları daha kontrollü ve paketlenmiş bir şekilde son kullanıcılara sunmak için kullanılır.

## 11. Gateway Mantığı

Power BI raporları bulutta yayımlandığında veri kaynaklarıyla bağlantı önem kazanır.

- Veri kaynakları tamamen bulut tabanlıysa (OneDrive, SharePoint, OData vb.) gateway kurmaya gerek olmayabilir.
- Veri kaynağı şirket ağı içinde veya yerel ortamdaysa (şirket içi SQL Server, ağ klasöründeki Excel, yerel CSV, on-premise ERP) **gateway** gerekir.

**Gateway**, PowerBI.com bulut servisi ile yerel veri kaynakları arasında köprü görevi görür: 
PowerBI.com şirket içindeki bir SQL Server'a doğrudan ulaşamayacağı için, veri kaynağını görebilen bir makineye gateway kurulur. 
Gateway ayarları bulut tarafında tanımlanır; Power BI belirlenen zamanlarda gateway üzerinden yerel kaynağa erişip rapordaki veriyi yeniler.

Kural olarak, modelde en az bir on-premise veri kaynağı varsa gateway ihtiyacı doğar; tüm kaynaklar buluttaysa gateway gerekmeyebilir.

## 12. Raporlara Erişim

PowerBI.com üzerinde yayımlanan raporlara kullanıcılar iki şekilde erişebilir:

- Web tarayıcısı üzerinden (Chrome, Edge vb.)
- Power BI mobil uygulaması üzerinden (Android / iOS)

## 13. Uçtan Uca Power BI Akışı

1. Veri kaynağına bağlan.
2. Power Query ile veriyi temizle ve dönüştür.
3. Gereksiz sütunları kaldır.
4. Tablo ve sütun adlarını kullanıcı dostu hale getir.
5. Flat tabloları fact ve dimension mantığına göre ayır.
6. Dimension tablolarda anahtar sütunları tekilleştir.
7. Fact tabloda yalnızca işlem ölçülerini ve foreign key alanlarını bırak.
8. Model View'da ilişkileri elle ve bilinçli şekilde kur.
9. Rapor görsellerini oluştur.
10. Fact tablodaki teknik ID alanlarını son kullanıcıdan gizle.
11. PBIX dosyasını kaydet.
12. PowerBI.com'a publish et.
13. Workspace veya App ile kullanıcılarla paylaş.
14. Gerekirse gateway ve scheduled refresh ayarlarını yap.

## 14. Best Practice'ler

- Veriyi doğrudan rapora sürüklemeden önce model yapısını düşün.
- Flat tablolarla çalışıyorsan fact ve dimension ayrımını yap.
- Dimension tablolarda anahtar sütunları tekil hale getir.
- Fact tablolarda açıklayıcı attribute sütunlarını tutma.
- Kullanıcıya gösterilecek alanları dimension tablolardan kullan.
- Fact tablodaki teknik ID sütunlarını gizle.
- Power Query adımlarını takip et; karmaşık dönüşümlerde Applied Steps adlarını anlamlı hale getir.
- Tablo ve sütun isimlerini son kullanıcının anlayacağı dile çevir.
- İlişkileri otomatik oluşmuş varsaymak yerine Model View'da kontrol et.
- Rapor paylaşımına geçmeden önce veri yenileme ve gateway ihtiyacını düşün.

## 15. Sonuç

Power BI'da başarılı rapor geliştirme yalnızca görsel seçmekten ibaret değildir. 
Sağlıklı bir Power BI çalışması; doğru veri alma, temizleme, modelleme, ilişki kurma, görselleştirme ve paylaşım adımlarından oluşur.

Power BI Desktop bu sürecin geliştirme merkezidir; 
PowerBI.com ise geliştirilen raporların yayımlandığı, paylaşıldığı ve kurumsal kullanım için yönetildiği platformdur.

Temel fikir şudur: **önce veriyi doğru modele dönüştür, sonra raporu oluştur.** Model doğru kurulmadığında görseller ilk bakışta çalışıyor gibi görünse bile, rapor karmaşıklaştıkça hesaplama, filtreleme ve bakım problemleri ortaya çıkar. 
Bu nedenle Power BI öğrenirken ilk odak noktası, veri modelinin mantığını anlamak olmalıdır.
