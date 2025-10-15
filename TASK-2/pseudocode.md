Ad soyad: Ebrar Sude Yıldırım
Öğrenci no:250541104
BAŞLAT

# Kullanıcı giriş veya kayıt işlemi
KULLANICI_GİRİŞ_YAP_VEYA_KAYIT_OL()

DO
    EKRANDA "Ana Menü"
    SEÇİM = KULLANICIDAN_GİRDİ_AL()
    
    EĞER SEÇİM == 1 İSE
        DOKTOR_LISTESİNİ_GÖSTER()
        SEÇİLEN_DOKTOR = KULLANICIDAN_DOKTOR_SEÇİMİ_AL()
        
        RANDEVU_TARİH_SAAT = KULLANICIDAN_RANDEVU_TARİH_SAAT_SEÇİMİ_AL()
        
        RANDEVUYU_ONAYLA(SEÇİLEN_DOKTOR, RANDEVU_TARİH_SAAT)
    
    DEĞİLSE EĞER SEÇİM == 2 İSE
        RANDEVULARI_GÖSTER()
        
        EKRANDA "Randevu iptal etmek istiyor musunuz? (Evet/Hayır)"
        CEVAP = KULLANICIDAN_GİRDİ_AL()
        
        EĞER CEVAP == "Evet" İSE
            İPTAL_EDİLECEK_RANDEVUYU_SEÇ()
            RANDEVUYU_İPTAL_ET()
    
    DEĞİLSE EĞER SEÇİM == 3 İSE
        ÇIKIŞ_YAP()
        DÖNGÜYÜ_KIR()
    
    DEĞİLSE
        EKRANA "Geçersiz seçim, tekrar deneyin."

WHILE TRUE

BİTİR
