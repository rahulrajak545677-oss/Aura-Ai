# AURA AI — Complete Project Archive (Android + Node.js Proxy)

**App Name:** AURA AI (`com.aura.ai`)  
**Tagline:** Think. Understand. Create. Assist.  
**Minimum Android Version:** Android 9 (`minSdk = 28`, `targetSdk = 35`)

## What Is Included
1. **Gradle & Manifest (`settings.gradle.kts`, `build.gradle.kts`, `gradle.properties`, `app/build.gradle.kts`, `AndroidManifest.xml`)**
   - Kotlin + Jetpack Compose + Material 3 + Hilt + Room + DataStore + WorkManager + CameraX + OkHttp/Retrofit.
   - Permissions: `INTERNET`, `ACCESS_NETWORK_STATE`, `SYSTEM_ALERT_WINDOW`, `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_SPECIAL_USE`, `RECORD_AUDIO`, `CAMERA`, `POST_NOTIFICATIONS`.
2. **Design System & Reusable Components (`ui/theme/Theme.kt`, `ui/components/AuraComponents.kt`)**
   - Midnight navy `#080D18`, `#101827`, `#172234`, `#202D40`, electric blue `#299BFF`, teal `#43DCC5`, `#F3F6FC` / `#98A7BC` text, `#26364D` border — zero purple.
   - Reusable components: `AppButton`, `AuraIconButton`, `ChatBubble`, `ChatInput`, `AuraSearchBar`, `FeatureCard`, `ToolCard`, `RecentChatCard`, `MemoryCard`, `ProjectCard`, `LoadingIndicator`, `ErrorCard`, `EmptyState`.
3. **Fixed Personality & Smart Router (`core/AuraPersonality.kt`, `core/SmartRouter.kt`)**
   - Single built-in AURA AI personality applied consistently across every provider and mode.
   - Task classification across Quick Question, General Chat, Complex Reasoning, Coding, Web Research, Image Understanding, Document Analysis, Translation, Summarization, Voice, and Creative Writing, with honest status labels (`Thinking`, `Searching the web`, `Reading your file`, `Preparing your answer`, `Creating image`, `Almost done`).
4. **Room Database, DataStore & Multi-Provider Gateway (`data/local/*`, `data/prefs/*`, `data/remote/*`)**
   - Entities & DAOs for Conversations, Messages, Memories, Projects, Project Notes, Tasks, Generated Images metadata, and Saved Items.
   - Supports Gemini (primary), Groq, OpenRouter, Cloudflare Workers AI, Mistral, plus optional TinyFish / web search / image adapters via backend proxy (and clearly labeled local dev-only options).
5. **Floating Bubble & Mini-Chat Overlay (`overlay/FloatingBubbleService.kt`)**
   - Real `WindowManager` overlay (`SYSTEM_ALERT_WINDOW` + foreground service notification), draggable, edge-snapping, position persisted in DataStore, quick action chips (`Ask AI`, `Search web`, `Voice`, `Translate`, `Summarize`, `Generate image`, `Full chat`), inline mini-chat input/messages, expand-to-full-app, and close action.
6. **Voice, Camera/Image/Document Helpers & WorkManager (`media/VoiceAndMediaHelper.kt`, `workers/TaskReminderWorker.kt`)**
   - Android `SpeechRecognizer` and `TextToSpeech` helpers (speed, language, stop/interrupt, permission handling), document text extractor (`PDF`/`TXT`/`DOCX` fallback honest notice), and WorkManager task reminder notifications.
7. **Complete 5-Destination App (`ui/AuraViewModel.kt`, `ui/Screens.kt`, `MainActivity.kt`)**
   - `Home`, `Chat` (edit, delete, copy, share, pin, rename, search, stop/retry, attachments, timestamps), `Create` (image generation adapter check, tools hub, tasks, projects & notes), `Memory` (search, add, edit, delete, clear all, memory toggle), and `Profile` (theme, bubble controls & permission flow, API/proxy settings with masked key display, privacy & data wipe, about).
8. **Backend Proxy (`backend/server.js`, `backend/package.json`)**
   - Keeps provider keys off the APK, enforces payload validation/limits, routes Gemini/Groq/OpenRouter/Cloudflare/Mistral/TinyFish requests safely, and avoids logging sensitive conversation text.

## Honest Scope & Limitations
- **APK Binary:** This archive delivers complete source code and build scripts; compile `.apk` locally in Android Studio or via Gradle (`./gradlew assembleDebug`).
- **Live Web Citations & Image Generation:** Real web results and generated images require configuring live search/image endpoints on your backend or provider; this project never fabricates citations or fake images.


## Building the APK via GitHub Actions (No Local Android Studio Needed)
1. Create a new repository on GitHub and upload the contents of this folder (`settings.gradle.kts`, `build.gradle.kts`, `app/`, `.github/`, etc. at the repository root).
2. Open the **Actions** tab in your GitHub repository.
3. Click **Build Android APK** (it starts automatically on push, or click **Run workflow**).
4. Once the workflow finishes (~2–4 minutes), scroll down to **Artifacts** and download **`aura-ai-debug-apk`**.
5. Extract the downloaded artifact zip on your Realme 11 Pro and install `app-debug.apk` (note: unsigned release APKs require signing before Android allows installation, whereas `app-debug.apk` installs immediately).
