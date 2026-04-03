Component
Recommended Technology Stack
Why This is the Best Choice (Efficiency, Scalability, Cost, Performance)
Alternatives (if multiple)
Mobile App (Frontend)
Flutter (Dart) + Impeller renderer + FlutterFire plugins
Single codebase for iOS + Android. Best-in-class real-time camera + ML performance (Impeller = buttery-smooth 60fps overlays). Excellent camera plugin ecosystem. Fastest development velocity for UI coaching overlays, pose guidance arrows, match % UI.
React Native (if you prefer JS, but slower camera/ML perf in 2026). Native (Kotlin/Swift) only if you need extreme optimization later.
Backend
Firebase (Cloud Functions + Firebase Auth + Storage)
Serverless, zero-ops scaling. Official Flutter integration (FlutterFire). Handles auth, reference photo upload/download, usage analytics. Free tier easily supports 1000+ concurrent + 50k MAUs with no throttling for your light workload.
Supabase (open-source Postgres + Edge Functions) — if you want full ownership and cheaper long-term scaling. Firebase wins for Flutter speed.
Database
Firestore (NoSQL, real-time)
Real-time sync for user profiles/references. Offline-first (works without internet). Scales effortlessly to thousands of users. Built-in security rules.
Supabase Postgres (if relational queries needed later). Firestore is simpler and more mobile-native.
AI/ML (Core Intelligence)
Google ML Kit (Pose Detection plugin) + TensorFlow Lite (tflite_flutter) + MediaPipe Pose (via plugins)
On-device only — no API calls, zero rate limits, works offline, sub-50ms inference on modern phones. ML Kit/MediaPipe = gold standard for real-time pose (33+ keypoints, 3D depth). TFLite for custom models (pose similarity scoring, brightness analysis).
PyTorch Mobile (for advanced custom training) or ONNX Runtime. ML Kit/TFLite combo is fastest to integrate in Flutter.
Camera Integration & System Camera
Flutter camera package + platform channels (for full native controls) + sensors plugin (IMU/gyro)
Direct access to system camera (no custom SDK needed). startImageStream feeds live frames to ML Kit/TFLite for real-time guidance. Auto-adjust brightness/exposure/ISO/focus/white-balance via native APIs. On-install: permissions + onboarding flow auto-enables camera mode.
Native Camera2 (Android) / AVFoundation (iOS) via platform channels if ultra-fine control needed (Flutter package already covers 95%).
Real-time Pose/Angle/Position Assist + 97% Match
MediaPipe/ML Kit Pose + custom TFLite Siamese network (or keypoint distance scoring) + device sensors
Detects live pose → compares to uploaded reference (pre-compute keypoints once). Computes angle/position similarity + overlay arrows/guidance. 97% threshold triggers auto-capture. Fully on-device = instant feedback, no latency.
MoveNet Lightning (lighter alternative for older phones). MediaPipe is the 2026 leader for mobile speed/accuracy.
Post-Processing (Contrast, Saturation, Color Grading, Exposure, Highlights, Shadows, Vibrance, Temperature, Tone, Sharpness, Fading, Vignette, Enhance, Dehaze)
TensorFlow Lite (pre-trained enhancement models) + OpenCV (via FFI or flutter_opencv package) + GPU delegates
Lightweight quantized models + OpenCV filters handle every listed adjustment in <200ms after capture. Dehaze/enhance use restoration models from TF Hub. All on-device = instant, private, free.
Built-in Flutter image package for basics + GPUImage (iOS)/RenderScript (Android) via channels. TFLite + OpenCV is most flexible/powerful.
Scalability & 1000 Concurrent Users
On-device AI (100%) + Firebase serverless
On-device = infinite horizontal scaling (each phone does its own AI). Firebase handles any shared features (auth/storage) with zero extra cost at this scale. No cold starts or limits hit.
Self-hosted Supabase on cheap VPS (if you outgrow free tier). Not needed here.
Development & Deployment (to keep it 100% free while building)
VS Code + GitHub (free) + GitHub Actions (CI/CD) + Firebase free tier (Spark plan) + Flutter free
All open-source. No paid tools. Firebase Spark covers everything for 1000 users (storage, reads, functions). Publish to Google Play ($25 one-time) + Apple ($99/year — minimal).
Render/Heroku free tiers for any custom functions (rarely needed). Supabase free if switching backend.



