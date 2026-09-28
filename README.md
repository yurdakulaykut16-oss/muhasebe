# X ERP

**Et, tavuk ve kasap ürünleri üreten fabrikalar için üretim, izlenebilirlik ve muhasebe yönetim sistemi.**

X ERP; hammadde kabulünden üretime, soğuk hava deposundan frigorifik sevkiyata ve muhasebeci aktarımına kadar işletmenin temel süreçlerini tek uygulamada toplar.

> **Önemli:** Uygulamadaki örnek şirket, müşteri, tedarikçi ve mali veriler gösterim amaçlıdır. Canlı kullanımdan önce şirket bilgilerini girin ve mali kayıtları yetkili mali müşavirinizle doğrulayın.

## Windows uygulamasını çalıştırma

Hazır Windows uygulaması `release/X-ERP-1.0.0-Windows.exe` dosyasıdır.

1. `release` klasörünü açın.
2. `X-ERP-1.0.0-Windows.exe` dosyasına çift tıklayın.
3. Windows SmartScreen uyarısı gösterirse dosyayı yalnızca bu deponun güvenilir sürümünden indirdiğinizden eminseniz **Ek bilgi > Yine de çalıştır** seçeneğini kullanın.
4. Portable sürüm kurulum istemez; doğrudan açılır.

Windows uygulaması çalışırken kayıtlar bilgisayarınızdaki uygulama verisi alanında saklanır. Düzenli olarak rapor çıktısı ve yedek alınması önerilir.

## İlk kurulum kontrol listesi

Canlı kayıt girmeden önce aşağıdaki sırayı takip edin:

1. **Ayarlar > Firma bilgileri** bölümünü açın.
2. Ticari ünvanı, vergi numarasını, vergi dairesini, MERSİS numarasını ve fatura adresini girin.
3. Çalışma dönemini ve varsayılan para birimini kontrol edin.
4. Müşteri ve tedarikçiler için cari kartları oluşturun.
5. Depo, raf ve karantina lokasyonlarını tanımlayın.
6. Kullanılan ürün reçetelerini ve hedef randımanları kontrol edin.
7. Açılış stoklarını parti bazında kaydedin.
8. Banka ve kasa başlangıç kayıtlarını mali müşavirinizle doğrulayın.
9. e-Belge ve vergi kayıtlarını yetkili entegratör/mali müşavir bilgileriyle eşleştirin.

## Modüllerin kullanımı

### Genel Bakış

İşletmenin özet kontrol ekranıdır. Aşağıdaki bilgileri gösterir:

- Aylık satış hacmi
- Toplam stok miktarı
- Açık cari bakiye
- Aktif ithalat/ihracat sevkiyatları
- Günlük üretim miktarı
- Ortalama randıman
- Kalite kontrol durumu
- Soğuk depo kapasitesi ve sıcaklığı
- Yevmiye denge kontrolü
- Banka mutabakatı
- Döviz pozisyonu

Kartlara tıklayarak ilgili modüle geçebilirsiniz.

### Üretim Planlama

Et, tavuk ve işlenmiş ürünler için iş emri açılır.

Her üretim emrinde en az şu bilgiler bulunmalıdır:

- İş emri numarası
- Üretilecek ürün veya operasyon
- Üretim hattı
- Planlanan kilogram
- Hammadde partisi
- Hedef randıman
- Başlangıç ve bitiş zamanı
- Sorumlu ekip

Üretim tamamlandığında gerçekleşen ürün, yan ürün ve fire miktarlarını kaydedin.

### Reçete ve Parçalama

Karkas veya hammaddenin hangi çıktılara dönüşeceğini tanımlar.

Örneğin dana karkas parçalama reçetesinde bonfile, kontrfile, antrikot, tranç, kıyma, kemik, yağ ve fire oranları ayrı tutulabilir. Gerçekleşen toplam çıktı, kullanılan hammadde miktarını aşmamalıdır.

**Randıman hesabı:**

```text
Randıman (%) = Kullanılabilir ürün miktarı / Kullanılan hammadde miktarı × 100
```

Reçetede değişiklik yapılırsa eski kayıtları bozmamak için yeni reçete versiyonu oluşturun.

### Kalite ve İzlenebilirlik

Her hammadde ve mamul partisi için kalite kararı tutulur.

Kontrol edilmesi önerilen alanlar:

- Menşe ve tedarikçi
- Veteriner sağlık belgesi
- Kesim ve üretim tarihi
- Son tüketim tarihi
- Giriş sıcaklığı
- Mikrobiyolojik analiz
- HACCP kontrol noktaları
- Alerjen bilgisi
- Ambalaj ve etiket kontrolü

Uygun olmayan parti **Bloke** durumuna alınmalıdır. Kalite sorumlusu onayı olmadan sevkiyata açılmamalıdır.

### Soğuk Hava Depoları

Ürünleri depo, bölme ve raf konumuna göre takip eder.

- Donuk ürünler
- Soğuk ürünler
- Kanatlı ürünler
- Karantina ürünleri
- Sevkiyat hazırlık ürünleri

Fiziksel stok sayımı ile sistem miktarı düzenli olarak karşılaştırılmalıdır. Sıcaklık sapmaları kalite birimine bildirilmelidir.

### Satışlar

Müşteri satış belgelerinin yönetildiği bölümdür.

1. Cari hesabı seçin.
2. Satılan ürün ve partiyi belirleyin.
3. Kilogram/adet miktarını girin.
4. Birim fiyat, KDV ve para birimini kontrol edin.
5. Vade ve teslimat bilgilerini girin.
6. Belgeyi onaylamadan önce toplamları kontrol edin.

### Alışlar

Hammadde, navlun, gümrük, ambalaj ve diğer tedarik faturaları kaydedilir. İthalatla ilgili faturaları ilgili operasyon ve maliyet merkezine bağlayın.

### Stok ve Partiler

Stok takibinin temelidir. Her fiziksel ürün girişine benzersiz bir parti numarası verin.

Parti kartında şu bilgiler önerilir:

- Ürün
- Menşe ülke
- Tedarikçi
- Kesim/üretim tarihi
- Son tüketim tarihi
- Miktar ve ölçü birimi
- Depo konumu
- Saklama sıcaklığı
- Kalite durumu

### Sevkiyat ve Filo

Frigorifik araç ve müşteri teslimatlarını yönetir.

Yükleme öncesinde ürün partisi, araç plakası, sürücü, hedef sıcaklık, irsaliye ve teslim noktası doğrulanmalıdır. Teslimat sonrasında teslim sıcaklığı ve teslim alan kişi kaydedilmelidir.

### İthalat ve İhracat

Dış ticaret operasyonlarında referans, güzergâh, ürün, miktar ve tahmini varış bilgileri tutulur. Mal bedeli, navlun, sigorta, gümrük, ardiye ve diğer masrafları aynı operasyon altında toplayın.

### Cari Hesaplar

Müşteri ve tedarikçilerin borç/alacak ilişkisini takip eder.

- **Borç bakiye:** Cari hesabın işletmeye borcu olabilir.
- **Alacak bakiye:** İşletmenin cari hesaba borcu olabilir.
- **Vade:** Ödemenin beklenen tarihidir.
- **Mutabakat:** İki tarafın bakiyeyi karşılaştırıp doğrulamasıdır.

Kesin yorum için mali müşavirinize danışın.

### Kasa ve Banka

Banka, havale, SWIFT ve nakit hareketleri kaydedilir. Aynı işlemin hem manuel hem banka kaydıyla iki kez işlenmemesine dikkat edin. Dönem sonunda banka ekstresiyle mutabakat yapın.

### Genel Muhasebe

Tek Düzen Hesap Planı mantığıyla yevmiye ve mahsup fişlerini tutar. Her muhasebe fişinde toplam borç ve toplam alacak eşit olmalıdır.

Taslak fişleri kontrol etmeden kesinleştirmeyin. Hesap kodları ve vergi uygulamaları işletmeye göre değişebileceği için bu bölüm mali müşavir kontrolünde kullanılmalıdır.

### Maliyet Merkezi

Üretim ve dış ticaret masraflarını ilgili ürünlere dağıtır.

Dağıtılabilecek örnek maliyetler:

- Hammadde
- Navlun
- Gümrük ve ardiye
- İşçilik
- Enerji
- Ambalaj
- Soğuk hava deposu
- Fire
- Kalite ve laboratuvar

### e-Belgeler

e-Fatura ve e-İrsaliye kayıtlarının durumunu takip eder. Uygulamadaki belge ekranı tek başına GİB gönderimi garantilemez; canlı gönderim için yetkili özel entegratör veya GİB bağlantısı gerekir.

### Vergi ve Uyum

KDV beyannamesi, BA/BS kapsamındaki kontroller, cari mutabakat ve dönem görevlerini takip eder. Yasal tarihler değişebileceği için güncel mevzuatı ve mali müşavir bildirimlerini esas alın.

### Raporlar

- **Muhasebeci Paketi:** Fatura, cari, stok ve muhasebe çıktıları
- **Stok Envanter Raporu:** Parti ve depo bazında stok
- **Cari Mutabakat Raporu:** Müşteri ve tedarikçi bakiyeleri
- **İthalat Maliyet Raporu:** Operasyonun toplam ve kilogram maliyeti

Dönem kapanışından önce raporları muhasebecinize iletin.

## Kayıt oluşturma, silme ve çıktı alma

- İlgili modülü açın.
- Sağ üstteki **Yeni...** düğmesini kullanın.
- Zorunlu alanları doldurup **Kaydet** düğmesine basın.
- Satırın sonundaki göz simgesi görüntüleme, kalem düzenleme, çöp kutusu silme içindir.
- **Dışa aktar** rapor çıktısını, **Yazdır** tarayıcı/masaüstü yazdırma ekranını açar.

Silinen kayıtlar için geri alma özelliği bulunmadığından canlı kullanım öncesinde yedekleme sistemi kurulmalıdır.

## Geliştirici kurulumu

Gereksinimler:

- Node.js 22 veya üzeri
- npm

```bash
npm install
npm run dev
```

Üretim web derlemesi:

```bash
npm run build
```

Electron masaüstü uygulaması:

```bash
npm run desktop
```

Windows EXE oluşturma:

```bash
npm run build:exe
```

Çıktı `release` klasörüne yazılır.

## Veri güvenliği ve canlı kullanım notları

Mevcut sürüm kayıtları yerel tarayıcı depolamasında saklayan işlevsel bir ERP arayüzüdür. Bir fabrikanın gerçek ve çok kullanıcılı canlı ortamında kullanmadan önce aşağıdaki altyapılar eklenmelidir:

- Merkezi veritabanı
- Kullanıcı giriş sistemi
- Rol ve yetki matrisi
- Değiştirilemez denetim kayıtları
- Otomatik yedekleme
- Sunucu tarafı doğrulama
- KVKK erişim ve saklama politikaları
- GİB/özel entegratör bağlantısı
- Banka entegrasyonu
- Barkod ve terazi entegrasyonu
- Sıcaklık sensörü entegrasyonu
- Felaket kurtarma planı

Bu kontroller tamamlanmadan uygulamayı tek mali kayıt kaynağı olarak kullanmayın.
