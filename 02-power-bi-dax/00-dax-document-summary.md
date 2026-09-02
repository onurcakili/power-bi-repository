#  DAX Documents Summary

## BAŞLANGIÇ SEVİYESİ

| Status | No | Fonksiyon | Açıklama | Örnek DAX |
|---|---|---|---|---|
|+ | 1 | SUM | Toplam değer içindir | SUM(Satışlar[Tutar]) |
|+ | 2 | AVERAGE | Ortalama değer içindir | AVERAGE(Ürünler[Fiyat]) |
|+ | 3 | COUNT | Sayısal sütundaki değerleri sayar | COUNT(Satışlar[SiparişID]) |
|+ | 4 | COUNTA | Boş olmayan tüm değerleri sayar | COUNTA(Müşteriler[Email]) |
|+ | 5 | COUNTROWS | Tablodaki satır sayısını verir | COUNTROWS(Satışlar) |
| | 6 | MIN / MAX | En küçük / en büyük değeri bulur |  MAX(Satışlar[Tutar]) |
| | 7 | IF | Koşullu mantık kurar |  IF(Satışlar[Tutar] > 1000, "Yüksek", "Düşük") |
| | 8 | AND / OR / NOT | Mantıksal operatörlerdir | AND(Satışlar[Tutar]>500, Satışlar[Bölge]="İstanbul") |
| | 9 | CONCATENATE / & | Metinleri birleştirir |  Müşteriler[Ad] & " " & Müşteriler[Soyad] |
| | 10 | ISBLANK | Boş değer kontrolü yapar | ISBLANK(Satışlar[Tutar]) |
| | 11 | RELATED | İlişkili tablodan tekil değer çeker |  RELATED(Ürünler[Kategori]) |
| | 12 | FORMAT | Sayı/tarih biçimlendirir |  FORMAT(Satışlar[Tarih], "dd/mm/yyyy") |

---

## ORTA SEVİYE

| Status | No | Fonksiyon | Açıklama | Örnek DAX |
|---|---|---|---|---|
| | 13 | CALCULATE | Filtre bağlamını değiştirir (DAX'ın en kritik fonksiyonu) | CALCULATE(SUM(Satışlar[Tutar]), Satışlar[Bölge]="İstanbul") |
| | 14 | FILTER | Özel filtre tablosu oluşturur | CALCULATE(SUM(Satışlar[Tutar]), FILTER(Satışlar, Satışlar[Tutar]>1000)) |
| | 15 | ALL | Tüm filtreleri kaldırır |  CALCULATE(SUM(Satışlar[Tutar]), ALL(Satışlar)) |
| | 16 | ALLEXCEPT | Belirtilenler hariç tüm filtreleri kaldırır |  CALCULATE(SUM(Satışlar[Tutar]), ALLEXCEPT(Satışlar, Satışlar[Kategori])) |
| | 17 | ALLSELECTED | Kullanıcı seçimini koruyarak filtre kaldırır |  CALCULATE(SUM(Satışlar[Tutar]), ALLSELECTED()) |
| | 18 | SUMX | Satır bazlı (iterator) toplam hesaplar |  SUMX(Satışlar, Satışlar[Adet]*Satışlar[BirimFiyat]) |
| | 19 | AVERAGEX | Satır bazlı ortalama hesaplar | AVERAGEX(Satışlar, Satışlar[Adet]*Satışlar[BirimFiyat]) |
| | 20 | RELATEDTABLE | İlişkili tablodan çoklu satır getirir |  COUNTROWS(RELATEDTABLE(Satışlar)) |
| | 21 | VAR / RETURN | Değişken tanımlar, okunabilirlik/performans artırır |  VAR Ciro = SUM(Satışlar[Tutar]) RETURN Ciro * 0.2 |
| | 22 | SWITCH | Çoklu koşul yönetir |  SWITCH(TRUE(), Satışlar[Tutar]>1000,"Yüksek", Satışlar[Tutar]>500,"Orta", "Düşük") |
| | 23 | DIVIDE | Güvenli bölme yapar (hata önler) |  DIVIDE(Satışlar[Kar], Satışlar[Tutar], 0) |
| | 24 | DISTINCT / VALUES | Benzersiz değerleri listeler | DISTINCTCOUNT(Satışlar[MüşteriID]) |
| | 25 | TOTALYTD | Yıl başından bugüne toplam |  TOTALYTD(SUM(Satışlar[Tutar]), Takvim[Tarih]) |
| | 26 | SAMEPERIODLASTYEAR | Geçen yılın aynı dönemi |  CALCULATE(SUM(Satışlar[Tutar]), SAMEPERIODLASTYEAR(Takvim[Tarih])) |

---

## İLERİ SEVİYE

| Status | No | Fonksiyon | Açıklama | Örnek DAX |
|---|---|---|---|---|
| | 27 | DATEADD | Belirtilen periyot kadar tarihi kaydırır | Önceki Ay = CALCULATE(SUM(Satışlar[Tutar]), DATEADD(Takvim[Tarih], -1, MONTH)) |
| | 28 | DATESYTD | Yıl başından bugüne tarih tablosu döndürür | YTD Manuel = CALCULATE(SUM(Satışlar[Tutar]), DATESYTD(Takvim[Tarih])) |
| | 29 | PARALLELPERIOD | Belirtilen periyodu paralel kaydırır | Geçen Çeyrek = CALCULATE(SUM(Satışlar[Tutar]), PARALLELPERIOD(Takvim[Tarih], -1, QUARTER)) |
| | 30 | EARLIER | İç içe satır bağlamlarına erişir | Sıra No = RANKX(FILTER(Satışlar, Satışlar[Bölge]=EARLIER(Satışlar[Bölge])), Satışlar[Tutar]) |
| | 31 | RANKX | Dinamik sıralama yapar | Satış Sırası = RANKX(ALL(Ürünler), [Toplam Satış]) |
| | 32 | TOPN | Dinamik en iyi N kaydı getirir | İlk 5 Ürün = TOPN(5, Ürünler, [Toplam Satış], DESC) |
| | 33 | TREATAS | Sanal ilişki kurar | Sanal İlişki = CALCULATE(SUM(Bütçe[Tutar]), TREATAS(VALUES(Satışlar[Bölge]), Bütçe[Bölge])) |
| | 34 | SUMMARIZE | Sanal özet tablo oluşturur | ÖzetTablo = SUMMARIZE(Satışlar, Satışlar[Bölge], "ToplamTutar", SUM(Satışlar[Tutar])) |
| | 35 | SUMMARIZECOLUMNS | Modern sanal tablo oluşturma yöntemi | Özet = SUMMARIZECOLUMNS(Satışlar[Bölge], "Toplam", SUM(Satışlar[Tutar])) |
| | 36 | ADDCOLUMNS | Sanal tabloya hesaplanmış sütun ekler | Ek Sütun = ADDCOLUMNS(Ürünler, "KDV'li Fiyat", Ürünler[Fiyat]*1.20) |
| | 37 | GENERATE | İki tabloyu satır satır ilişkilendirir | Kombinasyon = GENERATE(Ürünler, FILTER(Satışlar, Satışlar[ÜrünID]=Ürünler[ÜrünID])) |
| | 38 | CROSSJOIN | Tabloların kartezyen çarpımını alır | Kombinasyonlar = CROSSJOIN(VALUES(Ürünler[Kategori]), VALUES(Takvim[Yıl])) |

---