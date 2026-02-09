
# **Costa Rican Spanish Deepfake Detection**

## **About the Project**

**CR-FakeSpeech** is an open-source research initiative by the **LAPA (Audio Processing Lab)** in Costa Rica. Our goal is to address the lack of audio forensic resources for Central American Spanish.

While state-of-the-art Deepfake detection models exist for English and Chinese, they often underperform when analyzing specific Latin American dialects due to prosody, accent, and vocabulary differences. This repository aims to build the first robust **Fake Speech Detection System optimized for Costa Rican Spanish.**

> **Mission:** To protect the integrity of our digital ecosystem by distinguishing between natural Costa Rican speech and AI-generated synthetic voices.

---

## **Research Lines & Student Participation**

This project is modular. Students can join different "Task Forces" depending on their skills and interests.

### **Track 1: The Dataset Builders (Red Team & Blue Team)**

*Objective:* Build `CR-Spoof-v1`, a dataset containing pairs of real and fake audio.

* **Blue Team (Real Audio):** Crowdsourcing voice recordings from students, faculty, and diverse demographics in Costa Rica to capture the "Tico" accent (voseo, rhotic pronunciation, etc.).
* **Red Team (Attacks):** Using state-of-the-art TTS (Text-to-Speech) and VC (Voice Conversion) tools to generate "attacks" (fake audio) based on the real recordings.
* *Tools used:* Coqui TTS, VITS, ElevenLabs, RVC (Retrieval-based Voice Conversion).



### **Track 2: Acoustic Analysis**

*Objective:* Understand *why* an audio is fake.

* Analyzing spectral artifacts in high frequencies.
* Visualizing Mel-spectrograms to find synthesis glitches.
* *Tools used:* Librosa, Python, Audacity.

### **Track 3: The Detector (Machine Learning)**

*Objective:* Train the classifier.

* Implementing baseline models (GMM, CNNs) and advanced models (RawNet2, Wav2Vec 2.0).
* Fine-tuning pre-trained models on our `CR-Spoof` dataset.

---

## **📂 Repository Structure**

```bash
TicoSpoof/
├── data/
│   ├── raw_audio/          # Unprocessed recordings (do not commit large files)
│   ├── metadata/           # CSVs linking audio files to Speaker ID, Age, Gender
│   └── protocols/          # Scripts for standardized recording
├── synthesis/
│   ├── generation_scripts/ # Python scripts to generate TTS audio
│   └── notebooks/          # Colab notebooks for RVC/VITS experiments
├── detection/
│   ├── features/           # Feature extraction scripts (MFCC, LFCC)
│   ├── models/             # PyTorch/TensorFlow model architectures
│   └── training/           # Training loops and validation scripts
├── docs/                   # Research papers and reading list
└── README.md

```

---

## **Getting Started**

### **Prerequisites**

We rely on open-source libraries to keep the project accessible.

```bash
pip install numpy librosa torch soundfile scipy

```

### **For New Students: Your First Contribution**

We need data! Follow these steps to contribute to the **Blue Team**:

1. **Clone the repo:**
```bash
git clone https://github.com/YourLab/TicoSpoof.git

```


2. **Record yourself:**
Go to `data/protocols/recording_script.txt`. Read the 10 phonetically balanced sentences using your natural accent.
3. **Upload:**
Place your files in the shared drive (link in internal wiki) or submit a Pull Request with the metadata CSV update.

---

## **Tech Stack & Tools**

* **Language:** Python 3.8+
* **Audio Processing:** Librosa, Torchaudio, ffmpeg
* **Deep Learning:** PyTorch
* **Generative Models:**
* *Tortoise-TTS* (High quality, slow)
* *VITS* (Fast, end-to-end)
* *RVC* (Voice Conversion)



---

## **Ethical Guidelines**

This laboratory operates under strict ethical standards.

1. **Consent:** No voices are cloned without the explicit, written consent of the speaker.
2. **Usage:** The synthesized audio is used **strictly** for training detection models.
3. **No Harm:** We do not generate content intended to deceive, defame, or impersonate individuals for malicious purposes.

All contributors must sign the `ETHICS_PLEDGE.md` before accessing the synthetic generation tools.

---

## **Roadmap**

* [ ] **Phase 1:** Collect 5 hours of diverse Costa Rican speech (Real data).
* [ ] **Phase 2:** Generate 5 hours of corresponding deepfakes (Synthetic data).
* [ ] **Phase 3:** Train a baseline ResNet classifier.
* [ ] **Phase 4:** Publish the dataset `CR-Spoof-v1` on HuggingFace.
* [ ] **Phase 5:** Develop a simple Web Demo where users upload audio to check if it's real or fake.

---

## **Contributing**

We welcome issues and pull requests! If you are a student at **Universidad de Costa Rica**, please check the "Good First Issue" tab to find tasks suitable for beginners.

**Contact:** Marvin Coto - marvin.coto@ucr.ac.cr

---

<!--### **Would you like me to:**

1. Create the **`ETHICS_PLEDGE.md`** template mentioned in the Readme?
2. Draft a Python script for the **"Blue Team"** that students can run to record audio directly from their terminal?
3. Move on to the README for the next project (e.g., The "Voice Banking" project)?-->
