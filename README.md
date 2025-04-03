# Speech Emotion Recognition (SER) in Real-Time

## Overview
This project implements a **Deep Learning (LSTM) model** using Keras to analyze audio files in real-time, identify emotions, and display the expressed sentiment with high accuracy.

## Objective
The goal of this study is to develop an **Artificial Intelligence (AI) algorithm** that processes an audio signal in real-time and accurately classifies the dominant emotion within it. The system is designed to continuously analyze incoming audio and stop automatically when silence is detected for **2 seconds or more**.

## Model Architecture
The model is based on a **Deep Neural Network (DNN)** optimized for time-series analysis, specifically utilizing a **Long Short-Term Memory (LSTM)** network. LSTM is chosen due to its ability to process sequential data and retain context over time, making it well-suited for speech emotion recognition.

## Dataset
The model is trained using **actor-expressed emotions** from:
- **RAVDESS** (Ryerson Audio-Visual Database of Emotional Speech and Song) - Ryerson University
- **TESS** (Toronto Emotional Speech Set) - University of Toronto

## Key Features & Improvements
### **1. Enhanced Preprocessing Pipeline**
- **Noise Reduction:** Implemented `noisereduce` for improved denoising with correctly structured input parameters.
- **Feature Extraction:** Extracts RMS energy, Zero Crossing Rate (ZCR), and MFCC features.
- **Data Normalization:** Normalized waveform using `pydub.effects.normalize()` for consistent input scaling.

### **2. Optimized Real-Time Processing**
- **Microphone Input Handling:** Audio is analyzed cyclically in real-time.
- **Efficient Silence Detection:** The system stops autonomously when no significant speech is detected for **2+ seconds**.
- **Robust Error Handling:** Added **Quality Assurance (QA) checks** to validate `np.pad()` issues and ensure data integrity.

### **3. Improved Emotion Mapping & Consistency**
- Fixed **labeling issues** in `emotions` dictionary to ensure correct mapping of predictions.
- Emotion classes include:
  ```python
  emotions = {
      0: 'neutral',
      1: 'happy',
      2: 'sad',
      3: 'angry',
      4: 'fearful',
      5: 'disgusted',
      6: 'surprised',
      7: 'calm'
  }
  ```

## Results
- **Achieved 87% accuracy** in speech emotion classification.
- Improved real-time performance and reduced computational overhead.
- Fixed inconsistencies in emotion label predictions for higher reliability.

## Future Enhancements
- **Expand Dataset:** Incorporate additional emotion datasets for increased generalizability.
- **Refine Feature Extraction:** Experiment with advanced spectrogram-based features (e.g., Mel Spectrogram, Chromagram).
- **Deploy as Web Service:** Convert model into an API for integration with real-world applications.

---

This project is continuously evolving, incorporating new optimizations and refinements to improve real-time emotion recognition accuracy and efficiency.

