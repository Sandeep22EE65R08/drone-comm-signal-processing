#JUPYTER NOTEBOOK
# 🛰️ Drone Signal Analysis & Pattern Detection Framework

A comprehensive end-to-end Python framework for analyzing **drone communication signals** captured using SDR (Software Defined Radio). This system supports raw signal processing, filtering, burst detection, pattern extraction, and statistical analysis using Python.

---

## 📌 Features

- 📡 Spectrogram and frequency spectrum visualization  
- ⚙️ Bandpass filtering & energy-based burst detection  
- 🎯 Frequency offset estimation and correction  
- 🧠 DFT-based low-pass filtering  
- 📈 Power Spectral Density (PSD) analysis  
- 🔍 Pattern detection using matched filtering  
- 📊 Statistical feature extraction (Energy, Power, Mean, Variance, Skewness, Kurtosis)  
- 🧬 KDE plots for pattern shape visualization  

---

## 🚀 Getting Started

### 📁 Prerequisites

Ensure Python 3.8+ and the following packages are installed:

```bash
pip install numpy scipy matplotlib seaborn
```

### 📂 Dataset

Place your `.dat` files (raw complex64 baseband signal captures) into a local directory and update the paths accordingly in your processing scripts.

---

## 🔧 Working Procedure

### **Step 1: Spectrogram Visualization**
- Read raw signal using NumPy.
- Plot time-frequency spectrogram using `matplotlib.pyplot.specgram()`.

### **Step 2: Power Spectral Density (PSD) Analysis**
- Apply Welch’s method using `scipy.signal.welch()`.
- Print and plot PSD values for each packet.

### **Step 3: Frequency Spectrum via FFT**
- Apply FFT with `np.fft.fft()` and `fftshift()` to analyze dominant frequencies.

### **Step 4: Bandpass Filtering & Energy-Based Packet Detection**
- Filter signal using a Butterworth bandpass filter.
- Use sliding energy window to detect signal bursts above adaptive threshold.

### **Step 5: Frequency Offset Estimation & Correction**
- Estimate carrier frequency offset via PSD peaks.
- Correct the signal using complex exponential mixing (`fshift` method).

### **Step 6: DFT-Based Filtering of Corrected Packets**
- Apply low-pass filtering in the frequency domain to reduce out-of-band noise.

### **Step 7: Pattern Detection**
- Detect patterns using matched filtering with a known reference.
- Apply adaptive thresholding to refine detection.

### **Step 8: Statistical Feature Extraction**
- For each extracted pattern, compute:
  - Energy, Power, Mean, Variance
  - Moment-based Skewness and Excess Kurtosis
- Generate KDE plots for signal shape distribution.

---

## 📈 Outputs

- **Spectrograms** of full signals and filtered packets  
- **PSD plots** showing spectral power  
- **Extracted signal bursts** with start, end, and duration  
- **Skewness & Kurtosis classification** for signal patterns  
- **KDE and waveform plots** for visual inspection  

---

## 📊 Sample Output

```bash
Packet 1: Start Time = 0.0075 s, End Time = 0.0092 s, Duration = 1.752 ms
Packet 1: Estimated Frequency Offset = -12031.25 kHz
Mean PSD Value for Packet 1: 5.06e-09 V²/Hz
Pattern 1: Energy = 1400.00, Skewness = 0.74 (Positive), Kurtosis = 2.11 (Platykurtic)
```

---

## 📂 Folder Structure

```bash
drone-signal-analysis/
├── data/
│   └── your_raw_signal.dat
├── scripts/
│   ├── spectrogram.py
│   ├── psd_analysis.py
│   ├── fft_spectrum.py
│   ├── energy_detection.py
│   ├── freq_offset.py
│   ├── dft_filtering.py
│   └── pattern_analysis.py
├── README.md
└── requirements.txt
```

---

## 🧠 Applications

- Drone communication signal decoding  
- RF burst and packet detection  
- SDR-based wireless signal analysis  
- Signal classification and anomaly detection  

---

## 📜 License

MIT License

---

