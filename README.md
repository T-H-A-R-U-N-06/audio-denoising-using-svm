# Adaptive Audio Denoising using SVD (MATLAB)

## Overview

This project implements an **adaptive audio denoising system using Singular Value Decomposition (SVD)** in MATLAB.
The system records audio, converts it into overlapping frames, performs SVD-based filtering to remove noise, and reconstructs the denoised signal using the **Overlap-Add method**.

The goal is to remove mild background noise while preserving the speech signal.

---

## Features

* Records audio using MATLAB
* Frame-based signal processing
* Singular Value Decomposition for noise reduction
* Energy-based singular value thresholding
* Signal reconstruction using overlap-add
* Visualization of original and denoised signals

---

## Methodology

### 1. Audio Recording

The system records audio using MATLAB's `audiorecorder` function.

### 2. Signal Framing

The audio signal is divided into overlapping frames using a buffer.

* Window Size: 1024 samples
* Overlap: 512 samples

This helps analyze the signal locally in time.

### 3. Singular Value Decomposition

Each framed matrix is decomposed as:

[
A = U S V^T
]

Where:

* **U** → left singular vectors
* **S** → singular values
* **V** → right singular vectors

Singular values represent the **energy of signal components**.

### 4. Adaptive Thresholding

The algorithm keeps the singular values that preserve **91% of total signal energy** and removes the rest.

This suppresses noise components.

### 5. Signal Reconstruction

The denoised frames are reconstructed using the **Overlap-Add (OLA) technique**.

---

## Project Structure

```
Audio-Denoising-SVD
│
├── audio_denoising_svd.m
├── original_audio.wav
├── denoised_audio.wav
├── report.pdf
└── README.md
```

---

## Requirements

* MATLAB
* Signal Processing Toolbox

---

## Output

The system produces:

* Original recorded audio
* Denoised audio
* Time-domain plots comparing both signals

---

## Results

The algorithm effectively removes mild background noise while maintaining speech clarity.

---

## Applications

* Speech enhancement
* Audio preprocessing
* Voice communication systems
* Signal processing research

---

## License

This project is released under the MIT License.

