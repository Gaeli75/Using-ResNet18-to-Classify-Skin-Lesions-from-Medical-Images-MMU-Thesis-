# Skin Lesion Classification using Deep Learning & XAI

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0-ee4c2c)
![Streamlit](https://img.shields.io/badge/Streamlit-App-ff4b4b)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📄 Project Overview
This project explores the application of Deep Learning (CNNs) to automate the classification of pigmented skin lesions into seven diagnostic categories. The study utilizes the **HAM10000** dataset and focuses on balancing high predictive accuracy with clinical interpretability.

To bridge the gap between "black-box" AI and clinical trust, the project integrates **Grad-CAM (Gradient-weighted Class Activation Mapping)** to visualize the specific lesion regions influencing the model's predictions. The final model was deployed as a user-friendly web application using **Streamlit**.

> **Note:** This project was submitted as a Master's Dissertation at Manchester Metropolitan University (2025).

## 🎯 Key Objectives
* **Fine-tune CNN Architectures:** Adapt **ResNet18**, **DenseNet121**, and **EfficientNet-B0** via transfer learning for dermatological classification.
* **Address Class Imbalance:** Mitigate the bias toward Melanocytic Nevi (majority class) using data augmentation and stratified sampling.
* **Explainable AI (XAI):** Implement Grad-CAM to generate heatmaps that validate if the model focuses on medically relevant features (e.g., borders, pigmentation).
* **Deployment:** Develop a prototype interface for real-time inference on upload or camera capture.

## 📊 Methodology & Results

### Dataset: HAM10000
The model was trained on 10,015 dermoscopic images across 7 classes:
* Melanocytic nevi (nv)
* Melanoma (mel)
* Benign keratosis-like lesions (bkl)
* Basal cell carcinoma (bcc)
* Actinic keratoses (akiec)
* Vascular lesions (vasc)
* Dermatofibroma (df)

### Performance Comparison
All three models were evaluated on a held-out test set. **DenseNet121** achieved the highest overall performance, while **ResNet18** offered the best balance of speed and accuracy.

| Model | Accuracy | Precision | Recall | F1-Score | Training Time (20 Epochs) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **ResNet18** | **97.19%** | 96.61% | 94.66% | 95.59% | ~2 hours |
| **DenseNet121** | **97.43%** | 96.20% | 94.90% | 95.70% | ~1 hour |
| **EfficientNet-B0**| **97.27%** | 94.90% | 94.70% | 94.80% | ~4 hours (Colab) |

### Visual Interpretability (Grad-CAM)
The project validated that the models were learning correct pathological features rather than background noise.
* **ResNet18:** Focused accurately on lesion borders.
* **DenseNet121:** Showed the tightest, most localized focus on lesion cores.
* **EfficientNet-B0:** Captured broader contextual features including perilesional skin.

*(Place a screenshot of your Grad-CAM comparison here, e.g., `assets/gradcam_comparison.png`)*

## 🛠️ Tech Stack
* **Deep Learning:** PyTorch, Torchvision
* **Data Processing:** Pandas, NumPy, OpenCV
* **Visualization:** Matplotlib, Seaborn
* **Deployment:** Streamlit, Hugging Face Spaces
* **Architecture:** ResNet18, DenseNet121, EfficientNet-B0 (Pre-trained on ImageNet)

## 💻 Application Demo
A Streamlit application was developed to allow users to upload images or scan a QR code for mobile capture. The app outputs:
1.  Predicted Diagnostic Category.
2.  Confidence Score & Probability Distribution.
3.  Grad-CAM Heatmap overlay.
4.  Clinical recommendation (Educational only).


## 🔒 Code Availability
This repository contains the documentation, results analysis, and visual assets of the project.
**Full source code for the pipeline and model training is available upon request** for academic or recruitment verification purposes.

## ⚠️ Disclaimer
This application and model are for **educational and research purposes only**. It is not a certified medical diagnostic tool and should not be used as a substitute for professional medical advice.

## 👤 Author
**Fundo Fernando**
* Data Analyst | Data Engineer
* MSc Data Science Candidate, Manchester Metropolitan University
* Chevening Scholar
