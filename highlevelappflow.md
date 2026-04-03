flowchart TD
    A[Start: App Launch / Install] --> B[Onboarding + Permissions\nCamera + Sensors + Storage]
    B --> C[Main Screen: Upload Reference Photo\nor Choose from Gallery]
    C --> D[Process Reference: Extract Pose Keypoints\nusing ML Kit / TFLite (basic stub)]
    D --> E[Enter Live Camera Coach Mode\nFull-screen preview with AR overlays]
    E --> F[Real-time Loop: Capture Preview Frame\nEvery 3-5 frames for battery]
    F --> G[Detect Live Pose + Device Angle\nusing ML Kit Pose + sensors_plus]
    G --> H[Compute Similarity Score\nBasic keypoint distance for now]
    H --> I{Similarity >= 97% ?}
    I -->|No| J[Provide Real-time Guidance\nBasic skeleton overlay + simple arrows/text]
    J --> F
    I -->|Yes| K[Auto-Capture Photo]
    K --> L[Apply Basic Post-Processing\ncontrast, brightness, sharpness, saturation, vignette (stub)]
    L --> M[Show Preview of Final Image]
    M --> N[Save to Gallery + Firebase]
    N --> O{Opt-in to Help Improve App? (stub)}
    O -->|Yes| P[Upload Anonymized Data stub]
    O -->|No| R[Continue]
    R --> S[Check for New Model Version stub]
    S --> T{New Model Available? (stub)}
    T -->|Yes| U[Download & Replace TFLite Model stub]
    T -->|No| V[End Session / Return to Main Screen]