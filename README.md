# CerVIA
Contains the code for the model selection, classification, and segmentation
README: VIA-Cervical Cancer Classification & SegmentationMinimalist student project using EfficientNet for cervical cancer screening on resource-constrained devices.
1. Setup and InstallationThis project was developed using Google Colaboratory (Colab), as it requires a GPU accelerator for model training and benefits from direct integration with Google Drive for data storage.
1.1 Prerequisites (Local or Colab)Make sure you have a Python environment with these packages installed. If using Colab, most are pre-installed.Bash# Required libraries
pip install numpy pandas scikit-learn tensorflow matplotlib scipy openpyxl
1.2 Hardware RequirementGPU: Training the models (especially the segmentation U-Net) requires a CUDA-compatible GPU. We used a T4 GPU on Colab.1.3 Data Setup (Crucial!)The code depends on a specific folder structure within your Google Drive.Mount Google Drive: Run the drive mounting cell in the notebook:Pythonfrom google.colab import drive
drive.mount('/content/drive')
Organize Data: Create the base directory and place the data from the shared link:Place the IARCImageBankVIA folder and the JH_seg_labels folder into a directory named data.Ensure your directory structure matches the path in the notebook:/content/drive/MyDrive/

Verify Paths: Update the BASE_DIR variable in the first code cell of the notebook to match your exact data location.
2. How to Run the Code
The primary code is in jhpiego_model_3 (2).ipynb.Step 1: Data Loading & PreprocessingRun the first two cells to load the data, define mappings, and perform the stratified split.Key Action: This is where the custom image enhancement happens in the process_path function: all images are permanently boosted with $1.8\text{x}$ Contrast and $1.5\text{x}$ Saturation.Step 2: Training the Classification Models (K-Fold Ensemble)This process uses Stratified 5-Fold Cross-Validation to train 5 separate EfficientNetB0 models.Run Cell 7 (the large ensemble loop) to train all 5 models and accumulate their predictions on the final held-out test set ($N=60$).Time: This step will take the longest (many minutes) as it trains 5 separate models for 15 epochs each.Step 3: Generating Final ResultsRun Cell 8 and Cell 9 to print the final ensemble metrics (Accuracy and F1 Score) and visualize the confusion matrix.
