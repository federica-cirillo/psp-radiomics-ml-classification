# Radiomics-Based Classification of PSP Phenotypes via Machine Learning

**University Exam:** Biomedical Signal and Image Processing

**Type:** Teamwork

## Overview

This project addresses the classification of Progressive Supranuclear Palsy (PSP) phenotypes from brain MRI scans. PSP is a rare neurodegenerative disease with 5 clinical phenotypes; the most common is Richardson's syndrome (PSP-RS), while the others are grouped as **variant PSP (vPSP)**.

**Goal:** distinguish PSP-RS from vPSP patients by extracting radiomic features from MRI images and classifying them using Machine Learning algorithms.

## Task 1 – Radiomic Feature Extraction

Features were extracted from MRI ROIs using three different tools, for comparison:
- **Matlab** – using the SERA algorithm
- **Python** – using the PyRadiomics package
- **3D Slicer** – using the Radiomics extension (also based on PyRadiomics)

**107 features** were extracted per patient, across categories: Shape, First Order, GLCM, GLRLM, GLSZM, NGTDM, GLDM.

Cross-validation showed strong agreement between features extracted via Python and 3D Slicer (both using PyRadiomics), while some discrepancies emerged when comparing Matlab (SERA) results with PyRadiomics-based ones, due to differences in feature computation.

## Task 2 – Classification via Machine Learning

**Dataset:** 26 patients × 107 features (14 PSP-RS, 12 vPSP)

**Workflow:** data preparation → algorithm selection → model training → testing, using k-fold cross-validation (k = 3 to 7) in Matlab's Classification Learner App.

**Algorithms implemented:**
- **Cosine KNN** – distance based on 1 − cosine similarity between feature vectors
- **Weighted KNN** – closer neighbors weighted more heavily than farther ones

## Results

| Model | Best Accuracy | k (folds) | NumNeighbors |
|---|---|---|---|
| Cosine KNN | 0.88 | 5 | 5 |
| Weighted KNN | **0.92** | 5 | 5 |

The Weighted KNN model achieved the best overall performance, correctly classifying PSP-RS vs vPSP patients with 92% accuracy.

## Skills & Tools

- **Matlab** (SERA, Classification Learner App, KNN implementation)
- **Python** (PyRadiomics)
- **3D Slicer** (Radiomics extension)
- Radiomics feature extraction, Machine Learning classification (KNN), k-fold cross-validation

## Repository Contents

- `Presentazione_PW/` – slide deck 
- `README.md` – this file
