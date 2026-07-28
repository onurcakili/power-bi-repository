# Yayınlama, Workspace, Veri Yenileme ve Gateway

## Amaç

Bu doküman, Power BI Desktop'ta hazırlanan bir raporun Power BI Service'e yayımlanmasını ve veri yenileme sürecinin nasıl yönetileceğini açıklar.

Bu dokümanın kapsamı:

- Workspace oluşturma
- Publish işlemi
- Semantic model ve rapor ayrımı
- Aynı modelden birden fazla rapor üretme
- Workspace erişim rolleri
- Gateway kavramı
- Scheduled refresh mantığı

Bu dokümanda RLS, tenant yönetimi ve modelleme detayları anlatılmaz.

## 1. Workspace Nedir?

Workspace, Power BI Service içinde raporların, semantic model'lerin ve diğer içeriklerin saklandığı çalışma alanıdır.

Workspace iki amaçla kullanılır:

- İçerik geliştirme ve yönetme
- İçeriği ekip veya kullanıcı gruplarıyla paylaşma

Power BI Service'te kişisel çalışma alanı olarak My Workspace bulunur. Ancak ekip veya kurumsal kullanımda ayrı workspace oluşturmak daha doğru yaklaşımdır.

## 2. Publish İşlemi

Power BI Desktop'ta hazırlanan PBIX dosyası Power BI Service'e publish edilir.

Publish işlemi sırasında:

1. Power BI Desktop'ta Publish seçilir.
2. Hedef workspace belirlenir.
3. PBIX dosyasındaki model ve rapor buluta gönderilir.
4. Power BI Service içinde rapor ve semantic model oluşur.

Bu işlemden sonra rapor tarayıcı üzerinden açılabilir.

## 3. Semantic Model ve Report Ayrımı

Bir PBIX dosyası Power BI Service'e publish edildiğinde iki temel artifact oluşur:

- Semantic model
- Report

Semantic model, veriyi, ilişkileri ve ölçüleri içerir. Report ise bu model üzerinde çalışan görsel sayfalardır.

Bu ayrımı erken öğrenmek önemlidir. Çünkü iyi yönetilen Power BI ortamlarında tek bir güvenilir semantic model üzerinden birden fazla rapor üretilebilir.

## 4. Aynı Modeli Tekrar Tekrar Publish Etme Problemi

Eğer her rapor ihtiyacı için aynı PBIX dosyası kopyalanıp tekrar publish edilirse, aynı veri modeli bulutta birden fazla kez oluşur.

Bu durum şu problemlere yol açar:

- Aynı veri farklı semantic model'lerde tekrar eder.
- Veri yenileme işlemleri çoğalır.
- Hangi modelin doğru olduğu belirsizleşir.
- Bakım maliyeti artar.
- Kullanıcılar farklı raporlarda farklı sonuçlar görebilir.

Önerilen yaklaşım:

Bir konuya ait merkezi semantic model oluşturulur. Farklı rapor ihtiyaçları bu model üzerinden geliştirilir.

## 5. Workspace Rolleri

Workspace içinde kullanıcılara farklı roller verilebilir.

Temel roller:

- Admin
- Member
- Contributor
- Viewer

Viewer rolü raporları görüntülemek için kullanılır. Son kullanıcılar için genellikle en uygun roldür.

Contributor, Member ve Admin rolleri geliştirme veya yönetim yetkisi olan kullanıcılar için kullanılmalıdır.

## 6. Gateway Nedir?

Power BI Service bulutta çalışır. Ancak veri kaynağı şirket içindeki bir sunucuda veya yerel dosya sisteminde olabilir.

Gateway, Power BI Service ile yerel veri kaynakları arasında güvenli bağlantı sağlayan yazılımdır.

Gateway özellikle şu veri kaynakları için gerekir:

- Şirket içindeki SQL Server
- Ağ klasöründeki Excel dosyası
- Yerel CSV dosyası
- On-premises ERP sistemi

## 7. Gateway Ne Zaman Gerekir?

Veri kaynağı Power BI Service tarafından doğrudan internet üzerinden erişilemiyorsa gateway gerekir.

Örnek:

Rapor Power BI Service'e publish edilmiştir. Ancak veri şirket içindeki SQL Server'dan gelmektedir. Power BI Service bu SQL Server'a doğrudan erişemez. Bu durumda SQL Server'a erişebilen bir makineye gateway kurulur.

## 8. Scheduled Refresh

Import modunda çalışan semantic model'lerde veri Power BI modeline yüklenir. Bu veri zamanla güncelliğini kaybeder.

Scheduled refresh, modelin belirli zamanlarda kaynak veriden yeniden güncellenmesini sağlar.

Örnek:

Satış raporu her sabah 08:00'de güncellenecek şekilde ayarlanabilir.

## 9. Kısa Özet

Yayınlama ve veri yenileme sürecinde en kritik noktalar şunlardır:

- Her rapor için aynı modeli tekrar publish etmekten kaçınılmalıdır.
- Merkezi semantic model yaklaşımı tercih edilmelidir.
- Workspace rolleri kontrollü verilmelidir.
- Yerel veri kaynakları için gateway gerekir.
- Import modellerde scheduled refresh ayarlanmalıdır.

## Kaynak Video

- Video 5: Power BI Eğitimi - Bulutta Yayınlama ve Gateway Üzerinden Model Güncelleme  
  https://www.youtube.com/watch?v=-PDo9zRsTw0

