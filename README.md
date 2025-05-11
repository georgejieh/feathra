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
├── LICENSE
├── NOTICE
├── README.md
├── data_pipeline/        # Scripts + notebooks for data collection & preprocessing
├── model_dev/            # Model training, evaluation, conversion scripts
├── mobile_app/           # Flutter codebase for cross-platform mobile app
├── scripts/              # Utility/dev scripts
└── tests/                # Unit and integration tests
````

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
