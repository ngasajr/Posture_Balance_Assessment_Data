# Sleep Posture and Balance Assessment Dataset and Models

## Overview
This repository contains the anonymized dataset and source codes used in our research paper:

**"Textile-based Pressure Sensor Systems for Fall-Risk Detection: Integrating Balance Assessment and Sleep Posture Detection"**  
Shin H., Ngasa E.E., Nam Y., Kim J., Woo J. (2025)

The dataset and models aim to support **human activity recognition** for healthcare applications, focusing on:
- **Sleeping posture classification** (5 classes: supine, left/right log, left/right prone)
- **Balance assessment** (3 tests: eyes open, eyes closed, dynamic tilting)

---

## Dataset
- Collected using **11×11 textile pressure sensor arrays** at 60Hz, downsampled to 1Hz.
- Includes:
  - **Sleep Posture Data** (10 participants, 5 postures, 5 minutes each)
  - **Balance Assessment Data** (19 participants, 3 standardized tests)
- Data is provided as anonymized **pressure maps** with preprocessing applied (thresholding, up-sampling, smoothing, normalization).

Download:  
`dataset/Sleep_Balance_Dataset.zip`

---

## Methods
Two approaches were implemented:
1. **Feature-based ML (SVM)**  
   - Extracted features: COP trajectories, PAS, QLR, CLR, zonal statistics  
   - Achieved **91.9% F1-score** for posture classification and **94%+ accuracy** for balance dynamic vs static

2. **Deep Learning (CNN)**  
   - 2D CNN for posture maps (128×128×3)  
   - 1D ResNet-style CNN for balance time-series  
   - High CV accuracy but overfitting in LOSO validation

---

## Repository Contents
- `dataset/` → Zipped dataset (pressure sensor data)
- `src/` → Source codes (SVM and CNN models)
- `README.md` → This file

---

## Usage
### 1. Clone the repository
```bash
git clone https://github.com/ngasajr/Sleep_Balance_Posture_Dataset.git
cd Sleep_Balance_Posture_Dataset
