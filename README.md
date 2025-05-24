
## 🔍 Project Overview

This project focuses on detecting audio deepfakes — distinguishing between real human speech and AI-generated voices using the **ASVspoof2019-LA** dataset. Leveraging deep learning models, including a custom **CNN-LSTM** hybrid, we achieved **99% accuracy** in classifying audio as *bonafide* (real) or *spoof* (fake).

🎧 **Live Demo:** [Streamlit App](https://siliconvsvocalchords.streamlit.app/)

---

## 📌 Motivation

With the rise of AI voice cloning, audio-based fraud is becoming a real threat. Incidents such as a $35M fraudulent bank transfer highlight the urgency to develop **audio spoofing detection** systems.

Our goal is to provide a practical solution for identifying fake audios in real-time through machine learning.

---

## 📂 Dataset

- **Dataset:** [ASVspoof2019-LA](https://www.asvspoof.org/)
- **Source:** VCTK corpus (107 speakers)
- **Labelled Classes:** 
  - `1` – Bonafide (real)
  - `0` – Spoof (AI-generated)
- **Preprocessing:**
  - Resampled to 16,000 Hz
  - Padded/truncated to 5 seconds
  - Mel Spectrogram, MFCCs, Chroma, Spectral Contrast, Tonnetz features

---

## 🧠 Methodology

### 1. Raw Audio Input (TSSD Model)
- Based on ResNet architecture
- Uses raw waveform directly
- 93% Accuracy

### 2. Feature-based Input

#### Extracted Features:
- **Mel Spectrogram**
- **MFCCs**
- **Chroma STFT**
- **Spectral Contrast**
- **Tonnetz**

#### Models:
| Model          | Architecture Highlights                          | Accuracy |
|----------------|--------------------------------------------------|----------|
| Base CNN       | 2 conv layers + dropout                          | 70%      |
| Enhanced CNN   | 3 conv layers + batch norm + dropout             | 87%      |
| **CNN-LSTM**   | CNN for spatial + LSTM for temporal features     | **99%**  |

---

## 🧪 Results

- **Best Model:** CNN-LSTM Hybrid
- **Performance:** 99% accuracy, high precision/recall
- **Confusion Matrix:** Strong diagonal, minimal false positives/negatives

---

## 🌐 Web Application

Built with **Streamlit**, this interactive app allows users to:
- Upload `.flac`, `.ogg`, `.mp3` files
- Get real-time classification (avg. < 500ms per file)
- Provide feedback for future model improvements

🖥️ [Launch the Web App](https://siliconvsvocalchords.streamlit.app/)

---


