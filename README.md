README: VIA-Cervical Cancer Classification & Segmentation
1. Project OverviewGoal: Classify cervical images (Negative, Suspicious, Positive) and segment lesions using EfficientNetB0 and U-Net.Method: Stratified 5-Fold Cross-Validation, Ensembling, and custom image enhancement for lightweight deployment. Key Constraint: Small, imbalanced dataset ($N=300$) using IARC and JHPIEGO data.
2. Setup (Google Colab Recommended)
  2.1 HardwareRequirement: Must use a GPU Accelerator (T4 or V100) for training speed.
  2.2 Data Paths (CRITICAL)The code requires the data folder structure to be set up on Google Drive exactly like this:Mount Drive: Run the standard cell to mount your Google Drive.
   2.3 Organize files like this:
   /content/drive/MyDrive/
    .../AI-ML-Health-Project/data/
        - IARCImageBankVIA/
            - Cases Meta data JH.xlsx
            - Case 001/
        - JH_seg_labels/
            - JHAA1/
   https://drive.google.com/drive/folders/1Cx6ZRlMDUtD5LZSWpY5Y0fvNO48NYoQm?usp=sharing
   ^ the data folder
 2.4 All necessary Python packages are standard in a Colab environment: ```!pip install tensorflow, numpy, pandas, scikit-learn.```

3. How to Run
   3.1 Run The demo for a demonstration, or run IARC classifier to show model selection is optimal with EfficientNetB0
   3.2 Run JHPiego_IARC classifier next for the classification engine.
   3.3 Run JHPiego_segmentation notebook for the segmentation.
