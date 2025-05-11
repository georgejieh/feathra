# 🐦 Feathra

Feathra is a sleek, mobile-first bird song identification app designed for nature enthusiasts, citizen scientists, and casual birders alike. It uses machine learning to analyze short audio snippets and identify bird species in real time — even in noisy environments.

Built with Flutter and optimized for on-device inference, Feathra works seamlessly across both Android and iOS, preserving user privacy while enabling powerful offline bird recognition features.

---

## 📲 Key Features

- Record 3–5 second audio clips to identify bird species by sound
- Lightweight deep learning model trained on real-world bird calls
- Top prediction results with confidence scores
- Journaling with location, photos, and user notes
- Fully functional offline support with local model
- Approximate location filtering to improve prediction accuracy

---

## 🧠 Machine Learning Stack

- Model Architecture: MobileNetV3 + 2D CNN + LSTM + Softmax
- Frameworks: TensorFlow (with TFLite), Core ML (for iOS), PyTorch (optionally)
- Training Data: Xeno-canto, BirdCLEF 2024, TweetyNet
- Preprocessing: 128-band mel spectrograms (32kHz mono WAV input)

---

## 📁 Repository Structure

```plaintext
feathra/
├── README.md
├── .gitignore
├── LICENSE
├── .github/
│   └── workflows/           # CI/CD (GitHub Actions later)
├── docs/                    # Documentation, diagrams, usage, etc.
├── data_pipeline/           # Phase 1: Data Collection & Preprocessing
│   ├── scripts/             # Python scripts for downloading and cleaning data
│   ├── raw_data/            # Unprocessed downloads
│   ├── processed/           # Spectrograms & transformed data
│   └── notebooks/           # Jupyter/Colab notebooks
├── model_dev/               # Phase 2: Model Training and Export
│   ├── training/            # Model training scripts
│   ├── models/              # Saved models (.h5, .pt, .tflite, .mlmodel)
│   ├── utils/               # Helper functions
│   └── experiments/         # Logs, metrics, test runs
├── mobile_app/              # Phase 3+: Flutter App Codebase
│   ├── android/             # Native Android configs
│   ├── ios/                 # Native iOS configs
│   ├── lib/                 # Dart source files
│   ├── assets/              # Images, icons, model files
│   └── pubspec.yaml         # Flutter package config
├── scripts/                 # Dev scripts: setup, lint, tests
└── tests/                   # Unit and integration tests
````

---


# 🐦 Feathra

[...existing overview section...]

---

## 🧭 Project Plan

Feathra is being built in 7 clear phases:

### ✅ Phase 1: Data Collection & Preprocessing

* **Sources:**

  * Xeno-canto (CC-licensed global bird recordings)
  * BirdCLEF 2024 (annotated datasets)
  * TweetyNet (canary songs for validation)

* **Preprocessing Steps:**

  * Convert all audio to 32kHz mono WAV
  * Generate 128-band mel spectrograms (0.5–10kHz)
  * Apply time stretching and pitch shifting
  * Organize training into three stages:

    1. Clean calls (single bird)
    2. Overlapping calls (multi-species)
    3. Noisy environments (background traffic, wind)

### ✅ Phase 2: Model Development

* **Architecture:**

  * MobileNetV3 + 2D CNN + LSTM (lightweight, temporal-aware)
  * Softmax output with species probability distribution

* **Optimization:**

  * Quantization to FP16 or INT8
  * Pruning to reduce model size <10MB
  * On-device inference via TFLite (Android), Core ML (iOS)

* **Accuracy Enhancements:**

  * Temporal attention pooling
  * Location-aware filtering using static migration tables (e.g., eBird)

* **Tools:**

  * Python + TensorFlow or PyTorch
  * Model conversion: `tf.lite.TFLiteConverter` and `coremltools`

### ✅ Phase 3: App Framework & Integration

* **Framework: Flutter (preferred for ML support + ease of UI)**

  * Android: TFLite integration
  * iOS: Core ML integration

* **IDE Stack:**

  * Visual Studio Code (main)
  * Android Studio (build/deploy Android)
  * Xcode (build/deploy iOS)

### ✅ Phase 4: App Features

* **Core MVP:**

  * 3–5s audio recording
  * Spectrogram processing + model inference
  * Display top 3–5 predictions + confidence scores

* **Secondary Features:**

  * Journaling (SQLite): add photos, timestamps, notes
  * Location-based filtering (approx. 100 km² grid, on-device only)
  * Offline support (model and data preloaded)
  * Bird cards (basic info, images, calls)

### ✅ Phase 5: Privacy & Compliance

* **Location Data:**

  * Opt-in prompt with justification
  * On-device processing, no GPS stored/transmitted
  * Approximate location only (coarse grids)

* **Policy:**

  * GDPR/CCPA-compliant privacy policy
  * Clear in-app disclosures
  * App Store & Play Store privacy labels

### ✅ Phase 6: Testing & Deployment

* **Testing:**

  * Unit tests (audio, inference, UI)
  * Integration testing (end-to-end flow)
  * Field testing (urban noise, rural areas)

* **Deployment:**

  * Phase 1: North America (300 species)
  * Prepare app assets (icons, screenshots, descriptions)
  * Submit to Google Play + App Store with required disclosures

### ✅ Phase 7: Maintenance & Growth

* **Feedback Loop:**

  * In-app feedback, email support
  * Prioritize common bug reports or feature requests

* **Model Update Strategy:**

  * Periodic retraining
  * Trigger app update if model changes significantly
  * Explore lightweight dynamic updates via cloud (if allowed)

* **Future Ideas:**

  * Bird photo recognition model
  * Migration visualization overlay
  * Social features or gamified sightings

---

## 📄 Attributions

This project uses open-source datasets and model architectures, including:

* **Xeno-canto** (Creative Commons licenses, [https://xeno-canto.org/](https://xeno-canto.org/))
* **BirdCLEF 2024** (Terms of use via Kaggle competition)
* **TweetyNet** (BSD 3-Clause, [https://github.com/yardencsGitHub/tweetynet](https://github.com/yardencsGitHub/tweetynet))
* **MobileNetV3** (Apache 2.0, [https://github.com/xiaochus/MobileNetV3](https://github.com/xiaochus/MobileNetV3))

See `NOTICE` for full license and attribution details.

---

## 👤 Author

Feathra is developed by George Jieh as a solo project.
