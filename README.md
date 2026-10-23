# ring
Gizlilik Politikası
Son Güncelleme: 23 Ekim 2026

Bu Gizlilik Politikası, Güven Yüzüğü ("Uygulama") mobil uygulamasının ve bu uygulamaya bağlı donanım aksesuarının ("Yüzük") kişisel verileri nasıl işlediğini, sakladığını ve paylaştığını açıklar.

Güven Yüzüğü, kas kilitlenmesi veya acil durumlarda kullanıcının güvenliğini sağlamak amacıyla geliştirilmiş bağımsız, sunucusuz (serverless) ve kişisel bir güvenlik sistemidir. Ticari bir veri işleme veya reklam faaliyeti yürütmez.

1. Temel Mimari ve Veri Felsefesi
Uygulama harici bir merkezi veritabanı, üyelik sistemi veya geliştiriciye ait bir sunucu barındırmaz. Telefon ile yüzük arasındaki veri aktarımı yerel Bluetooth protokolü üzerinden doğrudan gerçekleşir; acil durum bildirimleri ise doğrudan cihazınızdan Telegram Bot API aracılığıyla belirlenen özel Telegram grubuna iletilir. Verileriniz üçüncü şahıslara veya şirketlere satılmaz, kiralanmaz ya da analiz şirketleriyle paylaşılmaz.

2. İşlenen Veriler ve Toplanma Amacı
Uygulamanın acil durum tespiti yapabilmesi için aşağıdaki veriler işlenir:

Hareket ve İvmeölçer Verileri: Yüzük donanımı el hareketlerini ve ivme değişimlerini ölçer. Bu veriler Bluetooth aracılığıyla telefona aktarılır ve yerel olarak analiz edilir. Hareket verileri yalnızca cihazınızın yerel hafızasında son 30 gün boyunca olay geçmişini (iptal edilen uyarılar, kilitlenme durumları) inceleyebilmeniz için tutulur; 30 günün sonunda otomatik olarak silinir. Dilediğiniz an tüm geçmişi tek dokunuşla sıfırlayabilirsiniz.

Konum Verileri (CoreLocation): Uygulama sürekli bir konum takibi yapmaz. Konum bilginiz yalnızca bir acil durum alarmı tetiklendiğinde (hareketsizlik süresi dolduğunda, manuel SOS verildiğinde veya uzun süreli titreme algılandığında) tek seferlik veya canlı konum paylaşımı süresince alınır. Elde edilen konum bilgisi doğrudan yetkilendirdiğiniz Telegram grubuna iletilir. Alarm "İyiyim" butonuyla kapatıldığı anda canlı konum paylaşımı ve konum okuma işlemi derhal durdurulur.

Acil Durum Kişi Listesi: Uygulama içerisinde acil durumlarda aranacak kişilerin ad ve telefon numaraları tamamen cihazınızın yerel depolama alanında saklanır. Bu veriler yalnızca alarm ekranında hızlı arama butonlarının oluşturulması ve Telegram mesajında aranacak kişinin belirtilmesi için kullanılır.

Telegram Bot ve Grup Bilgileri: Telegram Bot Token'ı ve Grup Kimliği (Chat ID), yetkisiz erişimleri önlemek amacıyla cihazınızın güvenli Anahtar Zinciri'nde (Apple Keychain) şifrelenmiş olarak saklanır. Dışa aktarılan tanılama günlüklerinde veya yedeklerde yer almaz.

3. Kullanılan Cihaz İzinleri
Uygulamanın arka planda ve kilit ekranında dahi kesintisiz çalışabilmesi için iOS işletim sisteminden aşağıdaki izinler talep edilir:

Bluetooth (CoreBluetooth): Yüzük donanımı ile sürekli bağlantıda kalmak, yüzükten gelen durum sinyallerini (kalp atışı paketleri, pil seviyesi, hareket şiddeti) okumak ve arka planda yüzükten veri geldiğinde sistemi uyandırmak için kullanılır.

Konum (Her Zaman / Always): Acil bir kilitlenme anında telefon kilitliyken veya cebinizdeyken dahi yakınlarınıza doğru koordinatların gönderilebilmesi için "Her Zaman İzin Ver" yetkisi gereklidir.

Bildirimler ve Kritik Uyarılar (Critical Alerts): Olası bir yanlış alarmı engellemek için acil durum mesajı gönderilmeden önce kullanıcıya geri sayım (ön uyarı) başlatmak amacıyla kullanılır. Kritik Uyarı izni, telefon sessiz veya Odak modundayken bile kullanıcının ön uyarı sesini duyabilmesi için kullanılır.

4. Üçüncü Taraf Entegrasyonları
Telegram Bot API: Uygulama, acil durum mesajlarını ve Google Maps konum bağlantısını iletmek üzere doğrudan Telegram altyapısını kullanır. Telegram üzerinden paylaşılan mesajlar ve konum verileri, Telegram'ın kendi Gizlilik Politikası'na tabidir. Grubun gizli olması ve davet bağlantılarının kapalı tutulması kullanıcı sorumluluğundadır.

Uygulamada herhangi bir reklam SDK'sı (Google AdMob vb.), analitik izleyici (Firebase, Mixpanel vb.) veya harici hata takip aracı (Sentry vb.) bulunmamaktadır.

5. Veri Güvenliği ve Saklama
Hareket kayıtları ve uygulama içi ayarlar cihazınızın yerel alanında (UserDefaults ve SwiftData) tutulur.

Telegram bot token'ı donanım düzeyinde güvenlik sağlayan Apple Keychain içerisinde barındırılır.

Yüzük ile telefon arasındaki iletişim BLE (Bluetooth Low Energy) üzerinden yerel olarak gerçekleştirilir.

6. Haklarınız ve Veri Kontrolü
Uygulama üzerindeki tüm kontrol tamamen kullanıcıya aittir:

Geçmiş ekranındaki tüm hareket ve alarm loglarını dilediğiniz an silebilirsiniz.

Uygulamayı cihazınızdan kaldırdığınızda, yerel depolamadaki tüm ayarlar, kişi listesi ve geçmiş kayıtları cihazınızdan kalıcı olarak silinir (Keychain verileri sıfırlanır).

7. Tıbbi Sorumluluk Reddi
Güven Yüzüğü onaylı bir tıbbi cihaz veya resmi bir acil çağrı sistemi (112 vb.) değildir. Uygulama ve yüzük, kullanıcının kriz anlarında yakınlarını haberdar etmeye yardımcı olan destekleyici bir kişisel güvenlik aracıdır; profesyonel tıbbi takip, tanı ve tedavinin yerini tutmaz.
