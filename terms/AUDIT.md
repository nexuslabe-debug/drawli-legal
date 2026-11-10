# Drawli — factual audit for the Terms of Service

Audit date: 11 November 2026  
Scope: repository source and bundled assets. This document is not legal advice.

## Executive conclusion

The generated Terms reflect the current application as audited. Drawli is an ad-supported Flutter drawing game with local AI recognition, local progression, optional rewarded ads, guided lessons, daily activities, cosmetic unlocks, and mini-games. The audited code contains no user account system, cloud save, multiplayer, real-money payment, subscription, or in-app purchase flow.

The Terms must remain marked as a draft until the developer confirms the items in `DEVELOPER_CONFIRMATION.md`. The most important blockers are the exact publisher identity, governing law/jurisdiction, declared target audience, and a broken contact link in the published Privacy Policy.

## Verified facts

## Principal source evidence

| Area | Audited source files |
|---|---|
| App identity/version/dependencies | `pubspec.yaml`, `android/app/build.gradle.kts`, `android/app/src/main/AndroidManifest.xml` |
| AI model and preprocessing | `lib/core/services/ai_service.dart`, `lib/core/services/drawing_preprocessor.dart`, `assets/models/README.md`, `assets/models/drawli_v7_2_universal_sketch_80_quality.onnx` |
| Game modes/categories | `lib/screens/modes/modes_screen.dart`, `lib/core/models/game_mode.dart`, `lib/core/data/category_repository.dart`, `lib/screens/game/game_screen.dart` |
| Drawing journeys and access | `lib/core/models/drawing_journey.dart`, `lib/screens/journey/drawing_journey_screen.dart`, `lib/core/services/drawing_journey_access_service.dart`, `lib/core/services/drawing_journey_progress_service.dart` |
| Academy | `lib/core/data/academy_lesson_repository.dart`, `lib/screens/academy/academy_screen.dart`, `lib/core/services/academy_access_service.dart` |
| Daily Path/challenge | `lib/screens/challenge/daily_path_screen.dart`, `lib/core/services/daily_path_progress_service.dart`, `lib/core/services/daily_challenge_service.dart` |
| Mini-games | `lib/screens/logic_games/logic_games_screen.dart`, `lib/screens/logic_games/mini_game_levels_screen.dart`, `lib/screens/size_rush/size_rush_screen.dart`, `lib/core/services/mini_game_progress_service.dart` |
| User-selected/exported images | `lib/screens/creative/free_draw_studio_screen.dart`, `lib/screens/special/copy_challenge_screen.dart` |
| Ads and consent | `lib/core/services/ad_service.dart`, `lib/main.dart`, `android/app/src/main/AndroidManifest.xml` |
| Local progress and rewards | `lib/core/services/progress_service.dart`, `lib/core/services/avatar_service.dart`, `lib/screens/store/store_screen.dart` |
| Voice/audio | `lib/core/services/voice_service.dart`, `lib/core/services/piper_voice_engine.dart`, `lib/core/services/audio_service.dart`, `assets/piper/`, `assets/audio/` |
| Privacy/support links | `lib/screens/settings/settings_screen.dart`, the hosted Privacy Policy at `https://nexuslabe-debug.github.io/drawli-privacy/` |
| Third-party notices | `LICENSE`, `assets/icons/academy/LICENSE.txt`, in-app license page reached from `lib/screens/settings/settings_screen.dart` |

### Identity and distribution

- Product name: Drawli.
- Android application ID and namespace: `com.nexuslabe.drawli`.
- Current repository version at audit: `0.2.2+14`.
- Publisher name used in current legal materials: `Nexuslabe`.
- Current privacy URL: `https://nexuslabe-debug.github.io/drawli-privacy/`.
- Displayed support email in that Privacy Policy: `nexus.labe@gmail.com`.

### Core experience

- Drawing gameplay uses an ONNX model bundled in the app.
- Recognition is performed on-device for the audited drawing flow; drawings are not uploaded to an AI server for classification.
- The model has a finite supported-category set, so its guesses can be wrong or incomplete.
- Academy contains guided drawing lessons using watch/trace/copy/create-style activities.
- The app contains drawing journeys and modes including Classic, Question, Precision, timed/survival/creative modes, Daily Path, Color Lab, Category Spy, Size Rush, and Memory Flip.
- Daily Challenge and local progress systems include scores, coins, streaks, level/lesson access, and unlocks.

### Accounts, storage, and user content

- No account, authentication, user profile backend, cloud-save system, public posting, multiplayer, chat, or user-to-user sharing system was found.
- Progress, settings, coins, streaks, purchases/unlocks made with virtual currency, and most state are stored locally through `shared_preferences`.
- Free Draw can export a PNG to local storage.
- Copy Challenge can let a user select an image from the gallery. The selection is user-initiated and processed for the feature.
- The main Android manifest declares Internet and network-state permissions; it does not declare camera, microphone, or broad storage permissions.

### Advertising and monetization

- Google Mobile Ads and Google User Messaging Platform consent functionality are integrated.
- The code contains rewarded and interstitial ad units. No banner implementation was found.
- Debug builds use Google test ad-unit IDs; release builds use production IDs.
- Rewarded ads can be offered for optional benefits such as additional lessons/levels, hints, continuation or extra time, coins, and unlock progress.
- Interstitial ads are placed at gameplay breaks/completions and are also protected by central session/cooldown logic.
- The ad request configuration uses a `G` maximum content rating and an age-restricted-treatment setting intended for child-directed handling.
- Ad availability and reward completion depend on Google/third-party callbacks and network availability.
- No Google Play Billing, subscription, real-money IAP, or active permanent ad-removal purchase flow was found.

### Virtual economy

- Coins and other progression items are virtual gameplay values.
- The current Store unlocks cosmetic content using locally stored coins and/or rewarded-ad progress.
- Active avatar choices found in the catalog are Drawli, Lucky, and King Frog.
- Virtual progress has no audited server-side restoration mechanism and may be lost when application data is cleared, the app is uninstalled, or the device changes.

### Voice, network, and third parties

- English and French voice assets/models are bundled locally in the audited project.
- Arabic may use an online Edge voice path with Android/device TTS fallback; availability and quality can vary.
- Some remote profile imagery uses DiceBear URLs with a local fallback.
- External links include the Play Store, legal pages, and support/review destinations.
- Cleartext network traffic is denied generally, with a localhost exception used by local 3D/model-viewer behavior.
- Major third-party components include Google Mobile Ads/UMP, ONNX runtimes, Flutter TTS/Edge TTS, Piper/Sherpa tooling, model viewer functionality, audio playback, image picker, URL launcher, in-app review, local preferences, and SVG rendering.

### Licensing and attribution

- The repository root contains an MIT license naming Hamza Taki (2026).
- Game Icons/Iconify attribution indicates CC BY 3.0.
- Sherpa ONNX materials indicate Apache 2.0.
- Bundled voice-model metadata includes third-party dataset/model licensing; French Siwis is identified as CC BY 4.0 in available metadata.
- The application exposes an open-source licenses screen.

## Legal and product risks found

### Critical before publication

1. **Broken Privacy Policy contact link.** The visible email is `nexus.labe@gmail.com`, but the current page’s `mailto:` target is `YOUR_SUPPORT_EMAIL` and the page still includes a replacement reminder. Correct the hosted Privacy Policy before publishing these Terms.
2. **Publisher identity is not legally verified.** “Nexuslabe” appears in materials, while older store materials may show “Nexus Labe.” Confirm the exact individual/company legal name and contact address.
3. **Governing law and jurisdiction are unknown.** The Terms intentionally leave this to developer confirmation instead of inventing it.
4. **Target audience/age declaration is not established by source code.** Child-directed ad settings do not themselves prove the Google Play target-age declaration. Confirm the Play Console selection and ensure the Privacy Policy, Data safety form, ads setup, content rating, and Terms are consistent.

### Important review items

5. Verify that all active 3D avatars, illustrations, sounds, music, icons, fonts, voice models, and training/reference assets have commercial-use rights and required attribution. In particular, active avatar assets should have explicit provenance records.
6. Confirm the legal and operational acceptability of the unofficial/third-party Edge TTS integration and describe its data flow consistently in the Privacy Policy.
7. Ensure the Play Console Data safety answers cover Google Mobile Ads/UMP and every network-enabled SDK, not only first-party collection.
8. Ensure rewarded-ad labels clearly state the reward before playback, grant it only on successful completion, and provide a non-deceptive way to exit.
9. Verify that local progress-loss behavior is acceptable and communicated; there is no audited cloud restore.
10. Re-check localized legal translations with a qualified native legal reviewer before publication.

## Statements deliberately not made in the Terms

- No claim that Drawli is fully offline.
- No claim that AI recognition is always correct.
- No claim that rewards or ads are always available.
- No claim of cloud backup or cross-device restoration.
- No fixed minimum age was invented.
- No governing country, court, company registration number, postal address, or effective publication date was invented.
- No claim that Drawli provides professional education.

## Recommended re-audit triggers

Review and update the Terms and Privacy Policy before adding any of the following:

- accounts, cloud saves, analytics, login, or a backend;
- public sharing, chat, multiplayer, leaderboards, or user-generated content hosting;
- subscriptions, in-app purchases, paid content, or ad removal;
- server-side AI recognition or upload of drawings/images/audio;
- microphone, camera, precise location, contacts, or broader storage access;
- new advertising or mediation providers;
- a new country of establishment, legal entity, target audience, or materially different business model.

