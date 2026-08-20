# RAP LIFE TR — iOS / Android Release

Bu branch, mevcut `rap-life-tr/index.html` uygulamasını Capacitor ile iOS ve Android uygulamasına dönüştürmek için hazırlanmıştır.

## Gereksinimler

- Node.js 22+
- npm
- iOS için macOS + güncel Xcode
- Android için Android Studio + güncel Android SDK
- Apple Developer hesabı
- Google Play Console hesabı

## İlk kurulum

```bash
npm install
npm run cap:add:ios
npm run cap:add:android
npm run cap:sync
```

> `ios/` ve `android/` klasörleri ilk `cap:add` komutlarıyla yerel makinede oluşturulur. Bunları oluşturduktan sonra projeye commit edebilirsiniz.

## iOS

```bash
npm run cap:ios
```

Xcode içinde:

1. Signing & Capabilities bölümünde Apple takımını seçin.
2. Bundle Identifier: `com.flowend.raplifetr`
3. Version ve Build numarasını ayarlayın.
4. Gerçek cihazda test edin.
5. Product > Archive ile arşiv oluşturun.
6. Organizer üzerinden App Store Connect'e gönderin.

## Android

```bash
npm run cap:android
```

Android Studio içinde:

1. Application ID: `com.flowend.raplifetr`
2. Release signing anahtarı oluşturun ve güvenli saklayın.
3. Target SDK'yı Google Play'in güncel şartına göre ayarlayın.
4. Build > Generate Signed Bundle / APK > Android App Bundle ile `.aab` üretin.
5. Play Console'a yükleyin.

## Store için eksik kalabilecek şeyler

Bu repo şu an cihazda tutulan yerel kayıt mantığına sahip. Gerçek çevrimiçi sosyal özellikler için backend, kimlik doğrulama, sunucu tabanlı veri silme, moderasyon/şikâyet, engelleme, güvenlik ve veri politikaları ayrıca uygulanmalıdır.

Yayın öncesi ayrıca şunları hazırlayın:

- 1024x1024 App Store ikonu
- Android adaptive icon
- iPhone ve Android ekran görüntüleri
- Uygulama açıklaması ve anahtar kelimeler
- Destek URL'si
- Yayında erişilebilir gizlilik politikası URL'si
- Yaş derecelendirmesi
- Veri güvenliği / App Privacy beyanları

## Web dosyası

Capacitor `webDir` olarak `rap-life-tr` klasörünü kullanır. Mevcut `index.html` doğrudan uygulama içinde paketlenir.
