# رحلة فخر الإمارات — UAE Pride Journey

An offline, bilingual (Arabic / English) app for iPhone, iPad and Android.
Visitors pick an explorer, travel a map of the UAE, read short quick facts, play a mini-game at each destination and collect gold stamps in a digital passport. After all stamps they take the National Day Challenge and unlock the **«سفير فخر الإمارات»** certificate.

**Version 1 (this build):** Space, Emirates Red Crescent and Emirati Heritage are complete. Armed Forces, The Union and Future UAE are on the map as “Coming soon”.

## What's inside

```
UAEPrideJourney/
├── web/www/index.html   ← the whole app (screens, text, games). Shared by both platforms.
├── android/             ← open this folder in Android Studio
└── ios/                 ← open UAEPrideJourney.xcodeproj in Xcode (needs a Mac)
```

Everything is bundled inside the app, so it works with no internet at the event. (With internet it also loads nicer Arabic fonts; without it, the device's own Arabic font is used.)

## Build for Android (tablet or phone)

1. Install **Android Studio** (free) on Windows, Mac or Linux.
2. *File → Open…* and choose the `android` folder. Wait for “Gradle sync” to finish (it downloads the build tools the first time).
3. Plug in the Android device with USB debugging on, then press **Run ▶**.
4. To get an installable file: *Build → Build App Bundle(s) / APK(s) → Build APK(s)*. Copy the `.apk` to other school tablets and install it.
5. For Google Play: *Build → Generate Signed App Bundle*, then upload the `.aab` in the Play Console (one-time USD 25 developer account).

## Build for iPhone / iPad

1. On a Mac, install **Xcode** from the App Store.
2. Open `ios/UAEPrideJourney.xcodeproj`.
3. Select the **UAEPrideJourney** target → *Signing & Capabilities* → choose your **Team** (a free Apple ID works for installing on your own devices). Change the Bundle Identifier if Xcode asks for a unique one.
4. Connect the iPad/iPhone and press **Run ▶**.
5. For the App Store or installing on many school iPads: *Product → Archive*, then distribute through App Store Connect / TestFlight (Apple Developer Program, USD 99 per year), or via your school's device management (MDM).

## Event tips

- **Next visitor** (on the map and certificate screens) clears the nickname, stamps and certificate on that device. The dream wall stays.
- **Dream wall approval:** on the dream wall tap “🔒 Teacher approval” and enter PIN **1971**. Approve or remove messages; only approved dreams are shown. To change the PIN, edit `TEACHER_PIN` near the top of the script in `web/www/index.html`.
- The screen stays awake while the app is open, so devices don't lock between visitors.
- A full visit (3 destinations + challenge) takes about 6–8 minutes.

## Editing text or adding destinations

All text is in `web/www/index.html`, in both languages (`en` / `ar`):

- Facts, intros and official links: the `DEST` list.
- Quiz questions: `QUIZ`.
- Aid-box situations: `AID`.

To finish a “Coming soon” destination, give it `ready:true` plus `intro`, `facts`, `sources` and `game` like the Space entry, and add its mini-game to `GAMES`. The passport, quiz unlock and certificate count the new stamp automatically. Rebuild the app afterwards.
