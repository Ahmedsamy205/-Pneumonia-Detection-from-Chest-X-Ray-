# 🫁 Pneumonia Detection from Chest X-Rays

A Computer Vision project that detects pneumonia in chest X-ray images using Transfer Learning with MobileNetV2, achieving **~95% training accuracy** and **87.6% test accuracy**.

---

📌 Problem Statement

Pneumonia is a life-threatening lung infection that affects millions worldwide. Early and accurate detection from chest X-rays is critical but requires trained radiologists. This project automates the detection process using deep learning to classify X-ray scans as either **PNEUMONIA** or **NORMAL**.

---

 📊 Dataset

- **Source:** [Chest X-Ray Images (Pneumonia) — Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)
- **Size:** 5,863 X-Ray images
- **Classes:** `PNEUMONIA` / `NORMAL`
- **Split:** Train / Validation / Test

> Dataset is not included in this repo. Download it via Kaggle API using the setup instructions below.

---

 🧠 Model

**MobileNetV2 with Transfer Learning**

| Component | Detail |
|-----------|--------|
| Base Model | MobileNetV2 (ImageNet weights, frozen) |
| Head | GlobalAveragePooling2D → Dense(128, ReLU) → Dropout(0.5) → Sigmoid |
| Optimizer | Adam |
| Loss | Binary Crossentropy |
| Epochs | 5 |
| Input Size | 128 × 128 × 3 |

---

 📈 Results

| Metric | Score |
|--------|-------|
| Training Accuracy | ~95% |
| Validation Accuracy | ~93.75% |
| Test Accuracy | **87.6%** |

---

 🔧 Tech Stack

- **Language:** Python 3
- **Deep Learning:** TensorFlow / Keras
- **Pretrained Model:** MobileNetV2 (ImageNet)
- **Data Augmentation:** ImageDataGenerator
- **Platform:** Google Colab (GPU T4)

---

⚙️ How It Works

1. **Setup** — Kaggle API used to download the dataset directly into Colab
2. **Preprocessing** — Images resized to 128×128, normalized, augmented with flips and zoom
3. **Model Building** — MobileNetV2 base (frozen) + custom classification head
4. **Training** — 5 epochs with Adam optimizer on GPU (T4)
5. **Evaluation** — Tested on held-out test set (624 images)

---

 🚀 Getting Started

### 1. Open in Google Colab
Open `Pneumonia_Detection.ipynb` in Google Colab and enable GPU runtime (Runtime → Change runtime type → T4 GPU).

### 2. Setup Kaggle API
Upload your `kaggle.json` when prompted to automatically download the dataset.

### 3. Run All Cells
The notebook will download the data, build the model, train it, and evaluate on the test set.

---

 📁 Project Structure

```
pneumonia-detection-chest-xray/
│
├── Pneumonia_Detection.ipynb   # Main notebook
└── README.md                   # Project documentation
```

---

 🔮 Future Improvements

- Fine-tune MobileNetV2 layers for better test accuracy
- Add Grad-CAM to visualize which regions indicate pneumonia
- Try EfficientNet or ResNet architectures
- Handle class imbalance with weighted loss or oversampling
- Deploy as a web app using Flask or Streamlit

---

 👨‍💻 Author

**Ahmed Samy Sobhi**  
AI & Machine Learning Engineering Student — Menofia National University  
📧 ahmedsamyy224@gmail.com

---
