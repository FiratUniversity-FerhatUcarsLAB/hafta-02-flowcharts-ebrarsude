Ad soyad: Ebrar Sude Yıldırım
Öğrenci no: 250541104

BAŞLAT

# Öğrenci giriş veya kayıt işlemi
ÖĞRENCİ_GİRİŞ_YAP_VEYA_KAYIT_OL()

TEKRARLA
    EKRANA "Ana Menü"
    SEÇİM = KULLANICIDAN_GİRDİ_AL()
    
    EĞER SEÇİM = 1 İSE
        DERS_LISTESİNİ_GÖSTER()
        SEÇİLEN_DERSLERİ_AL()
        
        KONTENJAN_DURUMU = KONTENJAN_KONTROL(SEÇİLEN_DERSLER)
        ÇAKIŞMA_DURUMU = SAAT_CAKIŞMASI_KONTROL(SEÇİLEN_DERSLER)
        
        EĞER KONTENJAN_DURUMU = UYGUN VE ÇAKIŞMA_DURUMU = YOK İSE
            DERS_KAYDINI_ONAYLA(SEÇİLEN_DERSLER)
            EKRANA "Ders kaydı başarıyla tamamlandı."
        DEĞİLSE
            EKRANA "Kontenjan dolu veya saat çakışması var, lütfen tekrar deneyin."
        
    DEĞİLSE EĞER SEÇİM = 2 İSE
        KAYITLI_DERSLERİ_GÖSTER()
        EKRANA "Ders iptal etmek ister misiniz? (Evet/Hayır)"
        CEVAP = KULLANICIDAN_GİRDİ_AL()
        
        EĞER CEVAP = "Evet" İSE
            İPTAL_EDİLECEK_DERSİ_SEÇ()
            DERS_İPTAL_ET()
            EKRANA "Ders iptali başarıyla tamamlandı."
    
    DEĞİLSE EĞER SEÇİM = 3 İSE
        ÇIKIŞ_YAP()
        DÖNGÜYÜ_KIR()
    
    DEĞİLSE
        EKRANA "Geçersiz seçim, lütfen tekrar deneyin."

SON

