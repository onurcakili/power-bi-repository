# Power BI Lisansları, Hesap Yapısı ve Temel Tenant Ayarları

## Amaç

Bu doküman, Power BI kullanmaya başlamak için gereken hesap, lisans ve temel tenant yönetimi konularını açıklar. Konu yönetimsel olduğu için teknik modelleme detaylarına girilmez.

Bu dokümanın kapsamı:

- Power BI Desktop'ın lisans açısından konumu
- Organizasyonel hesap ihtiyacı
- Kullanıcı başına lisanslar
- Kapasite lisansları
- Developer ortamı mantığı
- Kritik tenant ayarları

Bu dokümanda gateway, RLS, modelleme ve DAX detaylarına girilmez.

## 1. Power BI Desktop Ücretsizdir

Power BI Desktop, yerel bilgisayara kurulan geliştirme uygulamasıdır. Veri kaynaklarına bağlanmak, Power Query ile dönüşüm yapmak, veri modeli oluşturmak ve rapor tasarlamak için kullanılır.

Power BI Desktop'ı lokal geliştirme amacıyla kullanmak için ücretli lisans gerekmez.

Ancak raporu Power BI Service'e yayımlamak, başka kullanıcılarla paylaşmak veya kurumsal iş birliği özelliklerini kullanmak için Power BI lisansına ve organizasyonel hesaba ihtiyaç duyulur.

## 2. Organizasyonel Hesap Gereksinimi

Power BI Service, kişisel e-posta hesaplarıyla değil, iş veya okul hesabıyla kullanılır.

Kullanılabilecek hesap türleri:

- Kurumsal Microsoft 365 hesabı
- Okul hesabı
- Şirket domain'iyle oluşturulmuş Microsoft Entra ID hesabı
- Developer tenant içinde oluşturulmuş kullanıcı

Genel kural olarak Hotmail, Gmail veya kişisel Outlook hesapları Power BI kurumsal servisleri için yeterli değildir.

Örnek:

`ad.soyad@firma.com` uygun bir organizasyonel hesap olabilir.  
`adsoyad@gmail.com` Power BI tenant yapısı için uygun kurumsal hesap değildir.

## 3. Kullanıcı Başına Lisans Türleri

Power BI Service, Microsoft Fabric ile entegre çalışır. Kullanıcı başına temel lisans türleri şunlardır:

- Fabric Free
- Power BI Pro
- Power BI Premium Per User

### Fabric Free

Free lisans, kullanıcının kendi içeriğini oluşturması ve kişisel kullanım senaryoları için uygundur. Ancak klasik paylaşımlı kapasitede iş birliği ve paylaşım özellikleri sınırlıdır.

### Power BI Pro

Power BI Pro, çoğu kurumsal Power BI kullanımının temel lisansıdır.

Pro lisansla kullanıcı:

- Rapor yayımlayabilir.
- Workspace içinde çalışabilir.
- İçerik paylaşabilir.
- Diğer Pro kullanıcılarının içeriklerini tüketebilir.
- App ve workspace tabanlı iş birliği senaryolarında yer alabilir.

Başlangıç ve orta ölçekli ekip senaryolarında genellikle Pro lisans yeterlidir.

### Power BI Premium Per User

Premium Per User, Pro yeteneklerine ek olarak bazı Premium özelliklerini kullanıcı bazında sunar.

PPU özellikle şu durumlarda değerlendirilebilir:

- Premium özelliklere ihtiyaç vardır.
- Kurum genelinde kapasite almak yerine sınırlı kullanıcı grubu için gelişmiş özellikler istenir.
- Daha gelişmiş model ve yönetim kabiliyetleri gerekir.

## 4. Kapasite Lisansları

Kapasite lisansı, tek tek kullanıcıdan ziyade çalışma alanının barındırıldığı kapasiteye uygulanır.

Kapasite yaklaşımının temel mantığı şudur:

- İçerik belirli bir kapasite üzerinde barındırılır.
- Pro veya PPU kullanıcıları bu kapasitede içerik oluşturabilir.
- Belirli kapasite seviyelerinde Free kullanıcılar da paylaşılan içeriği tüketebilir.

Kapasite lisansları genellikle geniş kullanıcı kitlesine rapor dağıtan kurumlarda gündeme gelir.

## 5. Power BI Report Server

Power BI Report Server, Power BI içeriğini kurum içi ortamda barındırmak için kullanılan ayrı bir üründür.

Bu seçenek genellikle şu durumlarda değerlendirilir:

- Verinin veya raporların buluta çıkarılamadığı regülasyon senaryoları
- Kurum içi rapor sunucusu zorunluluğu
- Mevcut SQL Server Reporting Services altyapısıyla devam etme ihtiyacı

Ancak Report Server, Power BI Service'e göre bazı özellikleri geriden takip edebilir. Bu nedenle zorunlu bir neden yoksa modern Power BI kullanımında genellikle Power BI Service tercih edilir.

## 6. Developer Ortamı Mantığı

Power BI öğrenen veya geliştirme yapan kişiler için ayrı bir developer tenant kullanmak faydalı olabilir.

Developer tenant şu avantajları sağlar:

- Gerçek kurumsal tenant'ı bozmadan deneme yapılabilir.
- Admin ayarları öğrenilebilir.
- Lisans atama ve workspace yönetimi pratik edilebilir.
- Eğitim ortamı izole tutulabilir.

Developer tenant gerçek üretim ortamı değildir. Güvenlik, veri gizliliği ve kurumsal politika açısından gerçek verilerle dikkatli kullanılmalıdır.

## 7. Kritik Tenant Ayarları

Power BI tenant ayarları, Power BI yöneticisinin kurum genelindeki davranışları kontrol ettiği alandır.

Başlangıçta özellikle şu ayarlar önemlidir:

- Workspace oluşturma yetkisi
- Publish to web
- Custom visuals
- Guest user erişimi
- Certification ve promotion süreçleri
- Analyze in Excel ve XMLA endpoint ayarları
- Information protection ve sensitivity labels

### Workspace Oluşturma Yetkisi

Her kullanıcının serbestçe workspace oluşturabilmesi zamanla yönetilemez bir ortam doğurabilir.

Öneri:

Workspace oluşturma yetkisi tüm organizasyona değil, belirlenmiş güvenlik gruplarına verilmelidir.

### Publish to Web

Publish to web, bir Power BI raporunu internette herkesin erişebileceği public bağlantıyla yayımlamayı sağlar.

Kurumsal veri içeren raporlar için ciddi risk oluşturur. Bu nedenle varsayılan olarak kapalı tutulmalı, gerekiyorsa yalnızca sınırlı güvenlik gruplarına açılmalıdır.

### Custom Visuals

Power BI, standart görseller dışında marketplace üzerinden özel görseller de destekler.

Custom visual kullanımı güçlüdür; ancak her görselin kurumsal güvenlik gereksinimlerine uygun olup olmadığı değerlendirilmelidir.

### Certified ve Promoted İçerikler

Power BI ortamında birçok semantic model ve rapor oluşabilir. Kullanıcıların doğru içeriği bulabilmesi için güvenilir modellerin işaretlenmesi gerekir.

Promoted içerik, geliştirici veya ekip tarafından önerilen içeriktir. Certified içerik ise daha resmi kalite kontrolünden geçmiş, kurumsal olarak güvenilir kabul edilen içeriktir.

## 8. Kısa Özet

Power BI lisanslama ve tenant yönetimi, teknik rapor geliştirmeden ayrı düşünülmelidir.

Hatırlanması gerekenler:

- Power BI Desktop lokal kullanım için ücretsizdir.
- Power BI Service için organizasyonel hesap gerekir.
- Paylaşım ve iş birliği için çoğu senaryoda Pro veya PPU lisansı gerekir.
- Büyük ölçekli dağıtımda kapasite lisansları gündeme gelir.
- Workspace oluşturma ve publish to web gibi tenant ayarları kontrolsüz bırakılmamalıdır.
- Certified semantic model yaklaşımı kurumsal veri güvenilirliği için önemlidir.

## Kaynak Videolar

- Video 2: Power BI Lisans Tipleri, Ücretsiz Developer Lisansı Nasıl Alınır?  
  https://www.youtube.com/watch?v=HVoQihuztS0
- Video 11: Power BI Eğitimi - Önemli Tenant Ayarları  
  https://www.youtube.com/watch?v=p0W1JOb3z7o

