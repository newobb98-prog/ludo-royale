# Ludo Royale 🎲👑

An original, mobile-first online Ludo gaming application with classic rules, smooth animations, multiplayer lobbies, private rooms, AI bots, and a Firebase-ready architecture.

---

## 📱 Technology Stack
- **Android Runtime:** Kotlin, Jetpack Compose (`AndroidView`), Edge-to-Edge window insets, Android JavascriptInterface hardware bridge (`Vibrator`, `Toast`).
- **Frontend Engine:** HTML5, modern CSS3, responsive portrait layout, SVG procedural board renderer.
- **Sound Engine:** Web Audio API synthesizer for realistic dice clatter, token stepping hops, explosive capture booms, safe star shimmers, and victory fanfare (zero external audio file failures).
- **Backend Preparation:** Firebase Authentication wrapper (Guest session, Email/Password, Google Sign-in hooks) & Firestore server-authoritative schemas.
- **Anti-Cheat & Compliance:** Server-authoritative roll verification pattern; test-only virtual chip wallet with real-money transactions strictly disabled.

---

## 🕹️ Included Screens (All 12 Fully Functional)
1. **Splash Screen:** Animated 3D dice & crown branding with asset preloading.
2. **Login & Registration:** Guest instant play, email auth forms, and Firebase transition readiness.
3. **Home Dashboard:** Hero championship banner, 4 game modes, currency counters, and quick navigation.
4. **Play with Friends:** Hub to create or join private rooms.
5. **Online Multiplayer Lobby:** Animated radar matchmaking queue with 3-second bot fallback so you are never stuck in an empty queue.
6. **Create Private Room:** Choose 2P/4P, pick token color (Red, Green, Yellow, Blue), generate 6-digit room code (`LR-XXXX`), copy code button, and match launcher.
7. **Join Private Room:** Interactive code boxes with custom on-screen numeric keypad and code validation.
8. **Ludo Game Board:** 
   - 15x15 classical cross board with 4 colored yard bases.
   - 8 safe zones (Star squares and starting arrows) where tokens cannot be captured.
   - 3D animated rolling dice with face dots.
   - Hop-by-hop stepping token animations along track and colored home runways.
   - Capture mechanics knocking opponent tokens back to their yard.
   - Bonus turns on rolling a 6, capturing an enemy, or reaching center Home.
   - Turn timer ring with auto-move or pass.
   - Intelligent AI bot decision logic.
9. **Player Profile:** 8 selectable royal avatars, editable display name, win rate %, trophies, and career stats.
10. **Leaderboard:** Global and Weekly tabs with top 3 podium crowns and sticky current-player ranking.
11. **Match History:** Chronological log of recent matches, outcomes, token captures, duration, and coin rewards.
12. **Settings:** Sound Effects (SFX) toggle, Background Music (BGM) toggle, Haptic Vibration toggle, Auto-Move single token switch, Illustrated Rules guide, and reset account.

---

## 🛡️ Regulatory Notice on Virtual Wallet
In compliance with Google Play and app store developer policies:
- Real-money wagering, betting, deposits, and cashouts are **disabled**.
- The wallet functions as a preview test interface with free daily virtual chips (+1,000) for testing gameplay.

---

## 📲 How to Test the App on an Android Phone

### Method 1: In the AI Studio Browser Streaming Emulator
1. The app compiles and installs automatically in the browser's Android emulator window on the right.
2. You can tap on screen, roll dice, create rooms, join matches, and customize your profile directly.

### Method 2: Export APK and Install on Physical Android Device
1. In the AI Studio top navigation bar, open the **Settings** or **Project Export** menu.
2. Select **Export as APK** or run `gradle :app:assembleRelease`.
3. Transfer the generated `.apk` file to your Android phone (via USB, Google Drive, or direct download).
4. On your Android phone, enable *Install Unknown Apps* for your browser or file manager.
5. Tap the `.apk` file to install and play!

---

## 🚀 Firebase Backend Setup (When Moving to Cloud)
The app is pre-configured with the complete Firestore schema in `js/firebase-prep.js`:
- `users/{uid}`: Profile, coins, stats, trophies.
- `rooms/{roomId}`: Private lobby synchronization, host verification, and turn states.
- `matches/{matchId}`: Server-validated match results.

To link your live Firebase project:
1. Replace `FirebaseConfig` in `app/src/main/assets/www/js/firebase-prep.js` with your Firebase project credentials.
2. Deploy the pre-written `firestore.rules` security rules to ensure client anti-cheat protection.
