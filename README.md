# Cervia: VIA-Cervical Cancer Classification & Segmentation

## 1. Project Overview
Classify cervical images (Negative, Suspicious, Positive) and segment lesions using EfficientNetB0 and U-Net.

## 2. Method
Stratified 5-Fold Cross-Validation, Ensembling, and custom image enhancement for lightweight deployment. **Key Constraint:** Small, imbalanced dataset (N=300) using IARC and JHPIEGO data.

## 3. Setup (Google Colab Recommended)

### 3.1 Hardware Requirement
Must use a GPU Accelerator (T4 or V100) for training speed.

### 3.2 Data Paths (CRITICAL)
The code requires the data folder structure to be set up on Google Drive exactly like this:

**Mount Drive:** Run the standard cell to mount your Google Drive.

### 3.3 Organize files like this:
```
/content/drive/MyDrive/
  .../AI-ML-Health-Project/data/
      - IARCImageBankVIA/
          - Cases Meta data JH.xlsx
          - Case 001/
      - JH_seg_labels/
          - JHAA1/
```

[Data location](https://drive.google.com/drive/folders/1Cx6ZRlMDUtD5LZSWpY5Y0fvNO48NYoQm?usp=sharing)

### 3.4 Package Installation
All necessary Python packages are standard in a Colab environment:
```bash
!pip install tensorflow numpy pandas scikit-learn
```

## 4. How to Run

### 4.1 Demo
Run **demo.ipynb** for example input/outputs of the final classifier and segmentation models.

### 4.2 IARC Classification
Run **IARC_classifier.ipynb** for classification on IARC dataset (shows EfficientNetB0 is optimal).

### 4.3 Combined Classification
Run **jhpiego_iarc_classifier.ipynb** for the combined JHPiego and IARC classification engine.

### 4.4 Segmentation
Run **jhpiego_segmentation.ipynb** for lesion segmentation.
