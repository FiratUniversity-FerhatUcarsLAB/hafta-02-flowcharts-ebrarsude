Ad soyad:Ebrar Sude Yıldırım
Öğrenci no:250541104
digraph AlisverisSistemi {
    rankdir=LR;
    node [shape=box, style=rounded, fontname="Helvetica"];

    Baslat [label="Sistem Başlat", shape=ellipse]
    KullaniciKontrol [label="Kullanıcı Kayıtlı mı?"]
    KayitOl [label="Kayıt Ol"]
    GirisYap [label="Giriş Yap"]

    AnaMenu [label="Ana Menü\n1. Ürünleri Görüntüle\n2. Sepeti Görüntüle\n3. Sipariş Geçmişi\n4. Çıkış", shape=diamond]

    UrunleriGor [label="Ürünleri Listele"]
    UrunSec [label="Ürün Seç ve Adet Belirle"]
    SepeteEkle [label="Sepete Ekle"]

    SepetiGor [label="Sepeti Görüntüle"]
    OdemeYapilsinMi [label="Ödeme Yapılsın mı?", shape=diamond]
    OdemeYap [label="Ödeme Yap"]
    SiparisiKaydet [label="Siparişi Kaydet"]
    SepetiTemizle [label="Sepeti Temizle"]

    SiparisGecmisi [label="Sipariş Geçmişini Gör"]

    Cikis [label="Çıkış", shape=ellipse]

    // Akışlar
    Baslat -> KullaniciKontrol
    KullaniciKontrol -> KayitOl [label="Hayır"]
    KullaniciKontrol -> GirisYap [label="Evet"]
    KayitOl -> GirisYap
    GirisYap -> AnaMenu

    AnaMenu -> UrunleriGor [label="1"]
    UrunleriGor -> UrunSec
    UrunSec -> SepeteEkle
    SepeteEkle -> AnaMenu

    AnaMenu -> SepetiGor [label="2"]
    SepetiGor -> OdemeYapilsinMi
    OdemeYapilsinMi -> OdemeYap [label="Evet"]
    OdemeYap -> SiparisiKay
