# Easy Language — Android starter project

## ZIP-এ কী আছে
- Android WebView wrapper + HTML/CSS/JavaScript UI
- Dark/purple mobile design
- Home, lessons, Smart Dictionary, translation, AI Tutor demo, progress, settings
- Android Text-to-Speech bridge এবং microphone speech-recognition bridge
- GitHub Actions workflow দিয়ে debug APK build

## গুরুত্বপূর্ণ
- AI Tutor এখন **ডেমো**; এটি আসল AI মডেলের উত্তর দেয় না।
- সত্যিকারের natural/live AI voice conversation-এর জন্য secure backend ও real-time voice AI service যোগ করতে হবে।
- API secret key কখনো HTML/JavaScript বা APK-তে রাখবেন না।
- Translation-এর জন্য internet দরকার। Offline-এ কেবল অন্তর্ভুক্ত কিছু সাধারণ শব্দ/পাঠ কাজ করে।
- Android speech recognition/TTS ফোনের service ও installed language-এর ওপর নির্ভর করে।
- এই ZIP-এর APK এখানে build/test করা হয়নি। GitHub Actions-এ build সফল হলে APK artifact পাওয়া যাবে।

## Android ফোন থেকে GitHub-এ দিয়ে APK বানানো
1. ZIP extract করুন।
2. GitHub-এ নতুন repository তৈরি করুন।
3. ZIP-এর ভেতরের সব ফাইল repository root-এ upload করুন। `settings.gradle.kts`, `app/`, `.github/` root-এ থাকতে হবে।
4. Commit করুন।
5. Repository-এর **Actions** tab খুলুন এবং `Build Easy Language APK` workflow-এর run সম্পন্ন হতে দিন। প্রয়োজনে workflow নির্বাচন করে **Run workflow** চাপুন।
6. সফল run খুলে **Artifacts** থেকে `EasyLanguage-debug-apk` download করুন।
7. Artifact ZIP extract করে `app-debug.apk` বের করুন; ফোনে install করুন।

## মূল ফাইল
- `app/src/main/assets/www/index.html` — UI
- `app/src/main/assets/www/style.css` — design
- `app/src/main/assets/www/app.js` — app logic
- `app/src/main/java/com/easy/language/MainActivity.kt` — Android wrapper, TTS, speech recognition
- `.github/workflows/build-apk.yml` — build workflow

এটি একটি শুরু করার মতো project, production-ready app নয়। Release করার আগে AI backend, privacy policy, error handling, testing এবং release signing যোগ করতে হবে.
