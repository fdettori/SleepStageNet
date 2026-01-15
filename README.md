# Deep Learning Pipeline for Automatic Sleep Stage Classification  
### EEG/ECG-based Sleep Staging using the Sleep-EDF Dataset  

This project implements a **deep learning pipeline** for **automatic sleep stage classification** based on **EEG** and **ECG** recordings from the [Sleep-EDF Expanded dataset](https://physionet.org/content/sleep-edfx/1.0.0/). It provides an end-to-end reproducible framework — from data preprocessing to model evaluation — for exploring and benchmarking neural architectures on physiological time series for sleep analysis.

---

## Overview

Accurate sleep stage classification is crucial for diagnosing sleep disorders and assessing sleep quality. Manual annotation by experts is time-consuming and prone to variability.  
This project automates the process using **deep learning models trained on raw or minimally processed EEG and ECG signals**.

---

## Features

- Automated preprocessing of Sleep-EDF signals (EEG, ECG, hypnograms)  
- Segmentation into fixed-length epochs with stage labeling  
- Signal normalization and artifact filtering  
- Flexible model architecture definition (CNN, RNN, Transformer-based, etc.)  
- End-to-end training and evaluation pipeline  
- Support for cross-validation and subject-wise splitting  
- Visualization tools for metrics, confusion matrices, and stage transitions  

---

## Project Structure

.
├── data/                     # Raw and processed data (not included)

├── notebooks/                # Exploratory and preprocessing notebooks

├── src/

│   ├── data_preprocessing/   # EEG/ECG loading, filtering, segmentation

│   ├── models/               # Model architectures (CNN, LSTM, etc.)

│   ├── training/             # Training loop, loss functions, metrics

│   ├── evaluation/           # Model evaluation and visualization

│   └── utils/                # Utility functions

├── configs/                  # Training configuration files (YAML/JSON)

├── results/                  # Saved models, logs, and figures

├── requirements.txt

├── README.md

└── LICENSE

---

## Dataset

**Sleep-EDF Expanded**  
- Source: [PhysioNet](https://physionet.org/content/sleep-edfx/1.0.0/)  
- Subjects: 78 healthy individuals  
- Signals: EEG (Fpz-Cz, Pz-Oz), EOG, EMG, ECG  
- Sampling frequency: 100 Hz  
- Labels: Wake (W), N1, N2, N3, REM  

Data usage follows the **PhysioNet** license. You must agree to their terms before downloading.

---

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/<user>/sleep-stage-classification.git
cd sleep-stage-classification
pip install -r requirements.txt
```

---

## Usage

### 1. Preprocess data
```bash
python src/data_preprocessing/preprocess.py --data_dir ./data/raw --output_dir ./data/processed
```

### 2. Train model
```bash
python src/training/train.py --config configs/cnn.yaml
```
### 3. Evaluate performance
```bash
python src/evaluation/evaluate.py --model_path results/best_model.pth
```
### 4. Visualize results
```bash
python src/evaluation/plot_confusion_matrix.py
```

---

## License

This project is released under the MIT License. See the LICENSE file for details.