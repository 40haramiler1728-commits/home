# Home Asistan (Android / iOS uygulaması)

Yapay zekâ sohbet + görsel (SVG) çizim asistanı. Arayüz `www/index.html` içinde, Capacitor ile
Android ve iOS uygulamasına çevrilir.

## Önce: API anahtarı
Uygulama doğrudan Anthropic API'sini kullanır. https://console.anthropic.com adresinden bir API anahtarı oluştur.
Uygulamayı ilk açtığında "API anahtarını ekle" düğmesine dokunup anahtarı yapıştır (⚙ Ayarlar'dan da değiştirebilirsin).
Anahtar yalnızca telefonunda saklanır. Kullanım ücreti kendi hesabından düşer.

## Android APK — Android Studio olmadan (en kolay yol)
1. github.com'da ücretsiz hesap aç, yeni bir **private** depo oluştur.
2. Bu klasörün içindekileri (`.github` klasörü dahil) o depoya yükle.
3. Depoda **Actions** sekmesine gir → "Android APK" iş akışı kendiliğinden çalışır
   (çalışmazsa "Run workflow" de). ~5 dakika sürer.
4. Bittiğinde çalışmaya tıkla, en alttaki **HomeAsistan-APK** dosyasını indir (zip içinde `app-debug.apk`).
5. APK'yı telefona gönder, aç ve "bilinmeyen kaynaklardan yüklemeye izin ver" de.

## Android APK — Android Studio ile
```
npm install
npx cap sync android
npx cap open android      # Android Studio açılır → Build > Build APK(s)
```

## iPhone (Mac + Xcode gerekir)
```
npm install
npm install @capacitor/ios@6
npx cap add ios
npx cap sync ios
npx cap open ios          # Xcode açılır → kendi Apple hesabınla imzala → telefona yükle
```
App Store'a yüklemek için Apple Developer hesabı (yıllık 99 USD) gerekir.
Google Play için ise release imzalı AAB üretmen ve bir geliştirici hesabı (tek seferlik 25 USD) açman gerekir.

## Arayüzü değiştirmek
`www/index.html` dosyasını düzenle, sonra `npx cap sync` çalıştır (GitHub yöntemindeysen dosyayı depoya yüklemen yeter).
