# 🐦 Feathra

Feathra is a mobile-first bird identification app that uses machine learning to recognize birds by their sounds—and eventually, their appearance. Initially focused on fast, on-device bird call recognition, Feathra also supports rich sighting logs, filtering tools, and field guide browsing.

Built with Flutter and designed to run smoothly on both Android and iOS, Feathra emphasizes practical, local-first functionality in its early stages. Core features work without accounts or network access, while ads and optional upgrades help sustain long-term development and enable future server-supported capabilities.

---

## 📲 Key Features

- 🎙️ **Birdsong ID**: Record a 3–5 second clip to identify birds by their calls
- 📒 **Flexible Journaling**: Save detailed sightings with notes, behavior, weather, and photos
- 🌍 **Field Guide**: Browse bird details with images, regional context, and spectrograms
- 📊 **Local Analytics**: Track species counts, seasonal patterns, and trip history
- 🧭 **Advanced Filters**: Search by color, size, location, time of year, or tags
- 🔗 **Shareable Logs**: Export logs as CSV or `.fthlog` files for backup or cross-device sharing
- 💵 **Non-intrusive Monetization**: Includes banner ads and optional upgrades (e.g. remove ads, expand species content)

---

## 🧠 Why Feathra?

Feathra is designed for nature lovers who want a reliable bird ID tool without unnecessary barriers. Whether you're identifying birds by sound in remote areas or building a custom sighting log over time, Feathra offers flexibility and speed. Its architecture also allows for future enhancements—like image-based identification or cloud syncing—once user needs justify expansion.

---

## 🚀 Feature Comparison

| Feature                | Merlin | eBird | iBird/Sibley | Feathra |
|------------------------|--------|-------|--------------|---------|
| ML Sound ID            | ✓      | ✗     | ✗            | ✓       |
| Works Without Login    | ✗      | ✗     | ✓            | ✓       |
| Customizable Logging   | ✗      | ✓     | ✗            | ✓       |
| Local Analytics        | ✗      | ✗     | ✗            | ✓       |
| Export/Share Logs      | ✗      | ✓     | ✗            | ✓       |
| Optional Monetization  | ✗      | ✗     | Paid app     | Ads + Upgrades |

---

## 🧠 Machine Learning Stack

- **Architecture**: MobileNetV3 + 2D CNN + LSTM with softmax output
- **Input**: 128-band mel spectrograms from 32kHz mono WAVs
- **Frameworks**: TensorFlow or PyTorch for training, TFLite/Core ML for deployment
- **Optimization**: Pruned + quantized to <10MB for mobile use
- **Training Data**: Xeno-canto, BirdCLEF 2024, TweetyNet (for validation)

---

## 🗂️ Repository Structure

```plaintext
feathra/
├── README.md
├── LICENSE
├── NOTICE
├── .gitignore
├── .github/              # CI/CD configs
├── docs/                 # Planning and architecture
├── data_pipeline/        # Phase 1: Dataset preparation
│   ├── scripts/
│   ├── raw_data/         # [ignored]
│   ├── processed/        # [ignored]
│   └── notebooks/
├── model_dev/            # Phase 2: ML model training
│   ├── training/
│   ├── models/
│   ├── utils/
│   └── experiments/
├── mobile_app/           # Flutter codebase
│   ├── android/
│   ├── ios/
│   ├── lib/
│   ├── assets/
│   └── pubspec.yaml
├── scripts/              # CLI, test, dev tools
└── tests/                # App and ML test cases
````

---

## 🧭 Project Plan

Feathra is being developed in focused stages to remain practical, testable, and extensible.

### ✅ Phase 1: Data Collection & Preprocessing

* Collect and clean data from Xeno-canto, BirdCLEF, TweetyNet
* Convert audio to 32kHz mono WAVs
* Generate 128-band mel spectrograms
* Apply augmentation (pitch/time)
* Create clean/overlapping/noisy data tiers

### ✅ Phase 2: Model Development

* Build MobileNetV3 + LSTM model
* Quantize and prune for TFLite/Core ML export
* Validate with diverse bird call samples

### ✅ Phase 3: App Framework & Integration

* Build core UI in Flutter
* Integrate on-device model
* Implement audio capture and inference

### ✅ Phase 4: App Features

* Develop SQLite-based sighting journal
* Add field guide and advanced search
* Implement `.fthlog` and CSV export options
* Add non-intrusive ads and upgrade paths

### ✅ Phase 5: Platform Policies & UX

* Add app store privacy disclosures
* Ensure clear prompts for any location use
* Keep data local unless user explicitly shares

### ✅ Phase 6: Testing & Launch Prep

* Run automated + field-based testing
* Build out platform assets (icons, screenshots, descriptions)
* Prepare Play Store and App Store submissions

### ✅ Phase 7: Maintenance & Future Expansion

* Add user feedback loop
* Patch and refine audio model
* Introduce **image-based bird ID**
* Evaluate need for server-backed sync, photo guides, or community features

---

## 🔐 Monetization & Future Services

Feathra is intended to be usable as a free app without requiring accounts or subscriptions. That said, building and maintaining an app—even one that runs mostly locally—takes time and money. To support ongoing development, Feathra includes non-intrusive banner ads. I dislike disruptive ads just as much as you do, so I’ll be doing my best to keep them as minimal and respectful as ad platforms allow—no popups, no full screens, no noise.

If you enjoy the app and want to support its continued development, you’ll be able to remove ads through a small, optional in-app purchase. Think of it like buying me a cup of coffee once a month. Pricing is currently estimated at:
- $6.99/month (billed monthly), or
- $4.99/month (billed annually)

As the user base grows, Feathra may begin offering additional server-based features—only if there's enough interest to justify the cost. These could include:
- Community features like emoji-based reactions on sightings
- Gamified goals or streaks
- Cloud-based log sharing and comparisons
- Optional social feed limited to verified, model-validated photos or calls (to reduce moderation needs)

Access to these future features would likely be offered through a minimal subscription, priced based on actual server and development costs. All paid tiers will automatically remove ads by default. Users will always have control over what they choose to share, and no image or audio will be uploaded unless the app is confident it’s a valid bird capture.

---

## 📝 Attributions

Feathra uses open data and model architecture contributions from:

* **Xeno-canto** — CC-licensed bird recordings ([xeno-canto.org](https://xeno-canto.org))
* **BirdCLEF 2024** — Annotated bird sound dataset ([Kaggle](https://www.kaggle.com/competitions/birdclef-2024))
* **TweetyNet** — Canary song model reference ([GitHub](https://github.com/yardencsGitHub/tweetynet))
* **MobileNetV3** — Lightweight CNN backbone ([GitHub](https://github.com/xiaochus/MobileNetV3))

---

## 👤 Author

Created by **George Jieh**, combining machine learning, nature tech, and mobile design into a practical tool for birders and explorers of all levels.

---

## 💡 License

Feathra is open source under the **Apache 2.0 License**.