Ad soyad:Ebrar Sude Yıldırım
Öğrenci no:250541104
BAŞLAT

KULLANICI_GİRİŞ_YAP()

TEKRARLA
    EKRANA "Ana Menü"
    EKRAN_YAZ("1. Güvenlik Sistemini Aktif Et")
    EKRAN_YAZ("2. Güvenlik Sistemini Pasif Et")
    EKRAN_YAZ("3. Kamera Canlı İzleme")
    EKRAN_YAZ("4. Çıkış")
    
    SEÇİM = KULLANICIDAN_GİRDİ_AL()
    
    EĞER SEÇİM = 1 İSE
        GÜVENLİK_SİSTEMİNİ_AKTİF_ET()
        
        SÜREKLİ_KONTROL
            HAREKET_VAR_MI = HAREKET_ALGILAMA()
            EĞER HAREKET_VAR_MI = EVET İSE
                ALARMI_ÇALIŞTIR()
                KULLANICIYA_BİLDİRİ_GÖNDER()
            SON
        SON
        
    DEĞİLSE EĞER SEÇİM = 2 İSE
        GÜVENLİK_SİSTEMİNİ_PASİF_ET()
        
    DEĞİLSE EĞER SEÇİM = 3 İSE
        KAMERA_CANLI_İZLEME()
        
    DEĞİLSE EĞER SEÇİM = 4 İSE
        ÇIKIŞ_YAP()
        DÖNGÜYÜ_KIR()
        
    DEĞİLSE
        EKRANA "Geçersiz seçim, lütfen tekrar deneyin."
SON
