
# Multimodal Brain Tumor Segmentation using Deep Learning

## 📌 Overview
This repository presents a deep learning-based approach to brain tumor segmentation using multimodal MRI scans. We implement and compare two fusion strategies—Input-Level Fusion and Feature-Input Fusion—based on a U-Net architecture. The project utilizes the BraTS 2020 dataset for training and evaluation.

## 🧠 Motivation
Brain tumor segmentation is essential for treatment planning and clinical decision-making. Manual annotation is labor-intensive and subjective, motivating the need for automated methods. This project addresses the challenges of tumor heterogeneity and modality differences by leveraging multimodal data fusion.

## 📁 Dataset
- **Source:** [BraTS 2020 Challenge](https://www.med.upenn.edu/cbica/brats2020/)
- **Modalities:** T1, T1ce, T2, FLAIR
- **Classes:**
  - 0: Background
  - 1: Necrotic Core
  - 2: Edema
  - 3: Enhancing Tumor
 
  ![image](https://github.com/user-attachments/assets/d9391ee9-3aca-4d3f-b28f-aa9ef28db908)


## ⚙️ Preprocessing
- Skull Stripping using Otsu’s method and morphological operations
- Intensity Normalization (Min-Max scaling)
- Data Augmentation (rotation, flipping)
- Slice-wise preparation for 2D segmentation

## 🏗️ Model Architecture
- **Base:** U-Net
- **Fusion Strategies:**
  - **Input-Level Fusion:** Stack all modalities as 4-channel input
  - **Feature-Input Fusion:** Extract features separately and merge at bottleneck

![image](https://github.com/user-attachments/assets/29dba2e6-fe42-4eb0-ba56-6ce575bc488e)


## 🧪 Training Details
- **Loss Function:** Categorical Crossentropy + Dice Coefficient
- **Optimizer:** Adam (LR=0.0001)
- **Epochs:** 20
- **Batch Size:** 8
- **Metrics:** Dice Score, Precision, Sensitivity, Specificity

## 📊 Results
- Quantitative metrics and qualitative results provided in the notebook
- Visualizations include Dice score comparisons and segmentation overlays

      Final Scores:
        - Training Accuracy: 0.99, Validation Accuracy: 0.99
        - Training Loss: 0.042, Validation Loss: 0.038
        - Training Dice Coeff: 0.401, Validation Dice Coeff: 0.407

![image](https://github.com/user-attachments/assets/b86e19d3-d5c3-44b1-94a6-705591a682f3)


## 🔍 Future Work
- Incorporate transformer-based models (e.g., Swin UNET)
- Evaluate performance on other datasets (BraTS 2021, TCIA)
- Integrate clinical feedback for further validation

## 🙌 Acknowledgments
- BraTS Challenge organizers for dataset access
- Keras & TensorFlow for model development
- Research inspiration from literature on multimodal fusion in medical imaging
