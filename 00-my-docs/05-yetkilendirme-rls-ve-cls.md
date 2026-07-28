# Kullanıcı Yetkilendirme, Row Level Security ve Column Level Security

## Amaç

Bu doküman, Power BI'da kullanıcıların neyi görebileceğini yönetmek için kullanılan temel yetkilendirme ve veri güvenliği kavramlarını açıklar.

Bu dokümanın kapsamı:

- Workspace rolleri ile veri güvenliği arasındaki fark
- Row Level Security
- Desktop'ta rol tanımlama
- Service'te kullanıcıları role atama
- RLS test mantığı
- Column Level Security kavramına giriş

Bu doküman ileri seviye güvenlik mimarisi veya Tabular Editor uygulama detaylarını kapsamaz.

## 1. Yetkilendirme ve Veri Güvenliği Farkı

Power BI'da iki farklı güvenlik düzeyi birlikte düşünülmelidir:

- İçeriğe erişim yetkisi
- Veri satırlarına erişim yetkisi

İçeriğe erişim, kullanıcının raporu açıp açamayacağını belirler. Bu genellikle workspace rolleri, app erişimi veya paylaşım izinleriyle yönetilir.

Veri satırlarına erişim ise raporu açan kullanıcının hangi verileri görebileceğini belirler. Bu noktada Row Level Security kullanılır.

## 2. Row Level Security Nedir?

Row Level Security, kullanıcının kim olduğuna göre veri satırlarını filtreleyen güvenlik mekanizmasıdır.

RLS ile tek bir model kurulur, ancak farklı kullanıcılar modelin farklı satırlarını görür.

Örnek:

- İlkay rapora girdiğinde yalnızca İlkay'ın müşterileri görünür.
- Hakan rapora girdiğinde yalnızca Hakan'ın müşterileri görünür.
- Satış müdürü tüm ekibin verisini görebilir.

Bu yapı için ayrı ayrı rapor üretmeye gerek yoktur. Tek model, kullanıcıya göre filtrelenir.

## 3. RLS Nerede Tanımlanır?

RLS iki aşamada yönetilir:

1. Power BI Desktop'ta rol tanımlanır.
2. Power BI Service'te kullanıcılar bu rollere atanır.

Power BI Desktop'ta rol tanımlamak, kuralı yazmak anlamına gelir. Power BI Service'te kullanıcı atamak ise bu kuralın kimlere uygulanacağını belirler.

## 4. Static RLS Örneği

Static RLS, her rol için sabit filtre tanımlandığı durumdur.

Örnek:

- Rol: İlkay
- Filtre: Müşteriler[Satış Sorumlusu] = "İlkay"

Başka bir rol:

- Rol: Hakan
- Filtre: Müşteriler[Satış Sorumlusu] = "Hakan"

Bu yöntem küçük kullanıcı gruplarında anlaşılırdır. Ancak kullanıcı sayısı arttığında her kullanıcı için ayrı rol oluşturmak sürdürülebilir olmayabilir.

## 5. Dynamic RLS Fikri

Dynamic RLS, kullanıcı bilgisini modele bağlı bir kullanıcı tablosu üzerinden dinamik olarak filtreleme yaklaşımıdır.

Temel fikir:

- Kullanıcının e-posta adresi alınır.
- Bu e-posta bir yetki tablosuyla eşleştirilir.
- Kullanıcı yalnızca yetkili olduğu bölge, müşteri veya departmanı görür.

Dynamic RLS daha kurumsal ve sürdürülebilir bir yaklaşımdır.

## 6. Column Level Security Kavramı

Column Level Security, belirli kullanıcıların belirli sütunları görmesini engelleme fikridir.

Örnek:

Satış ekibi satış tutarını görebilsin, ancak maliyet sütununu görmesin.

RLS satır bazlı çalışır. Column Level Security ise sütun bazlıdır. Power BI Desktop'ın temel arayüzünde klasik anlamda basit bir CLS yönetimi yoktur. Bu tür ihtiyaçlar genellikle semantic model seviyesinde Object Level Security gibi gelişmiş tabular model özellikleriyle yönetilir.

## 7. Kısa Özet

Power BI güvenliği yalnızca raporu kimin açabileceğiyle ilgili değildir. Raporu açan kişinin hangi veriyi görebileceği de ayrıca yönetilmelidir.

Hatırlanması gerekenler:

- Workspace rolleri içerik erişimini yönetir.
- RLS veri satırlarını kullanıcıya göre filtreler.
- RLS rolü Desktop'ta tanımlanır, kullanıcı ataması Service'te yapılır.
- Viewer rolü RLS uygulanacak son kullanıcılar için daha uygundur.
- Sütun bazlı güvenlik daha ileri seviye model yönetimi konusudur.

## Kaynak Video

- Video 7: Power BI Eğitimi - Kullanıcı Yetkilendirme, Row Level Security ve Column Level Security  
  https://www.youtube.com/watch?v=sH5h3ldI6lw

