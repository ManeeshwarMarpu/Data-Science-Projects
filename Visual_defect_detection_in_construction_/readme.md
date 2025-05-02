# Visual Defect Detection – Cracked vs. Non-Cracked Classification

An end-to-end deep-learning pipeline that automates concrete crack detection using transfer learning, comprehensive EDA, and clear reporting.

---

## 📑 Table of Contents

1. [Project Overview](#project-overview)  
2. [Prerequisites](#prerequisites)  
3. [Installation](#installation)  
4. [Dataset Acquisition & Extraction](#dataset-acquisition--extraction)  
5. [Running the Project](#running-the-project)  
   - [Via Jupyter Notebooks](#via-jupyter-notebooks)  
   - [Via Command-Line Script](#via-command-line-script)  
6. [Outputs & Reports](#outputs--reports)  
7. [Results Summary](#results-summary)  
8. [Future Work](#future-work)  
9. [License & Acknowledgments](#license--acknowledgments)

---

## 1. Project Overview

Manual inspection of concrete (decks, walls, pavements) is slow, costly, and error-prone. This project:

- **Ingests & wrangles** the SDNET2018 dataset (56 000+ images).  
- **Performs EDA** to uncover class balance, lighting and texture challenges.  
- **Builds a CNN** classifier (frozen ResNet50 backbone + custom head).  
- **Trains** with data augmentation, mixed precision and early stopping.  
- **Evaluates** via accuracy, ROC AUC, confusion matrix, and misclassification analysis.  
- **Generates** PDF & PPTX reports for stakeholders.

---


### 2. Prerequisites

    Git (≥ 2.0)

    Python 3.8–3.12

    pip

    (Optional) Kaggle CLI for dataset download

    (Optional) virtualenv or venv

### 3. Installation

    Clone the repository

    git clone https://github.com/ManeeshwarMarpu/visual-defect-detection.git
    cd visual-defect-detection

    Create & activate a virtual environment

        macOS/Linux

    python3 -m venv venv
    source venv/bin/activate

    Windows

        python -m venv venv
        venv\Scripts\activate

    Install dependencies

        pip install --upgrade pip
        pip install -r requirements.txt

### 4. Dataset Acquisition & Extraction
    Option A: Kaggle CLI

        Place your kaggle.json in ~/.kaggle/ (Linux/macOS) or %USERPROFILE%\.kaggle\ (Windows).

        Download & unzip:

        mkdir -p data/raw
        kaggle datasets download -d seymurhasanov/annotated-sdnet2018 -p data/raw
        unzip data/raw/annotated-sdnet2018.zip -d data/extracted

    Option B: Manual Download (Zenodo)

        Download from Zenodo: https://zenodo.org/record/1274594

        Place ZIPs in data/raw/ and run:

        mkdir -p data/extracted
        unzip 'data/raw/SDNET2018_*.zip' -d data/extracted

    After extraction, you should see:

    data/extracted/
    ├── Decks/
    │   ├── Cracked/
    │   └── Non-cracked/
    ├── Walls/
    │   ├── Cracked/
    │   └── Non-cracked/
    └── Pavements/
        ├── Cracked/
        └── Non-cracked/

### 5. Running the Project
    Via Jupyter Notebooks

        Launch Jupyter:

        jupyter notebook

        Execute in order:

            01_data_wrangle_eda.ipynb (data wrangling & EDA)

            02_model_train_eval.ipynb (model training & evaluation)

    Plots and reports will be saved automatically under output/.
    Via Command-Line Script

    python src/visual_defect_detection.py \
    --data-dir data/extracted \
    --output-dir output

    This single script will:

        Load & split data

        Perform EDA & save figures

        Train & evaluate the model

        Generate PDF and PPTX reports

### 6. Outputs & Reports

    Figures: output/figures/

        class_distribution.png

        pixel_histograms.png

        confusion_matrix.png

        roc_curve.png

    Project Report: output/project_report.pdf

    Presentation: output/presentation.pptx

### 7. Results Summary

    Test Accuracy: 84%

    ROC AUC: 0.92

    Precision / Recall (macro): > 0.83

    False Negatives (missed cracks): 14%

    False Positives (false alarms): 18%

### 8.  Future Work

    Segmentation: Pixel-wise crack detection (e.g., U-Net)

    Edge Detection: Integrate classical filters as auxiliary inputs

    Data Enrichment: More lighting/material scenarios

    Deployment: Mobile/web app for field use

    ERP Integration: Automated maintenance scheduling in asset-management systems

### 9. License & Acknowledgments

    License: MIT

    Dataset: SDNET2018 (Zenodo)

    Frameworks: Keras, TensorFlow, python-pptx, ReportLab

😊Thank you to the SDNET2018 creators, the TensorFlow/Keras teams, and all open-source contributors.

