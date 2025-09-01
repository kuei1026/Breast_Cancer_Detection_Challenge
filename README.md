# Breast Cancer Detection Challenge (Kaggle)

This repository contains my solution for the CBIS-DDSM Breast Cancer Image Dataset challenge, focusing on building an end-to-end pipeline for mammography classification.

📊 Dataset

Source: CBIS-DDSM on Kaggle

~10,000 mammography images (CC and MLO views)

Labels: Benign / Malignant

Includes full mammogram, cropped images, and ROI masks

🔧 Approach

Data Cleaning & Alignment

Patient-level split (70/15/15 train/val/test)

CLAHE preprocessing and laterality normalization

Robust label propagation from ROI/crop to full images

Model

EfficientNet-B3 backbone (pretrained)

Dual-head classifier for CC vs. MLO views

Loss: Focal Loss

Stabilization: Exponential Moving Average (EMA)

Training

Phase A: Image size 768, LR=2e-4 (6 epochs)

Phase B: Image size 1536, LR=5e-5 (3 epochs)

📈 Results

Image-level: Test AUC ≈ 0.75, balanced accuracy across sensitivity/specificity

Per-breast aggregation: Improved robustness by combining CC & MLO views

📂 Files

notebooks/ → Full preprocessing, training, and evaluation pipeline
