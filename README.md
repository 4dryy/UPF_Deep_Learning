# 🧘‍♀️ Yoga Pose Classification with Deep Learning

This repository presents our deep learning project for **automated yoga pose classification** using modern computer vision techniques. The system is designed to classify **47 distinct yoga poses** from images, leveraging powerful pretrained architectures like **ConvNeXt-Tiny** and **ResNet34**.

---

## 👨‍💻 Project Authors

This project was developed by:
- **Adrià Cortés Cugat** - Undergraduate Mathematical Engineering in Data Science Student 
- **Joan Company Company** - Undergraduate Mathematical Engineering in Data Science Student

As part of the Deep Learning course in the 3rd year of the **Data Science Engineering** degree.

---

## 📂 Dataset Access

Due to GitHub’s size constraints, the full dataset (~500MB) is hosted on Google Drive.

📥 **[Download Yoga Pose Dataset (Google Drive)](https://drive.google.com/drive/folders/1FDCsXx5FC060RfOw34LKfFCRmd2lI4jW?usp=drive_link)**

**Usage:**
1. Open the link above and download the dataset folder.
2. Place the folder inside the root of this repository under `./data/`.

---

## 📁 Model Results and Checkpoints

All trained model weights and evaluation results (~500MB) are also hosted externally.

📥 **[Download Yoga Pose Model Results (Google Drive)](https://drive.google.com/drive/folders/15a2QuPL4ylWzYovGuqFvU_sHW7a8u4em?usp=drive_link)**  

---

## 🎯 Project Objective

Our goal is to build an accurate and efficient deep learning model that can automatically recognize yoga poses from RGB images. We explore various CNN architectures and training strategies to:

- Handle **multi-class classification** for 47 yoga poses
- Compare **lightweight vs. heavyweight models**
- Leverage **transfer learning** for performance and efficiency
- Evaluate real-world usability based on **accuracy**, **inference time**, and **model size**

---

## 🔍 Pipeline Overview

The project follows a complete and modular pipeline:

1. **Data Exploration & Augmentation**
   - Load and analyze yoga image dataset
   - Visualize class balance and apply transforms (resize, crop, flip, etc.)

2. **Baseline Model: SimpleCNN**
   - Implement a small custom CNN to set a baseline

3. **Transfer Learning with Pretrained CNNs**
   - Test multiple architectures (e.g. ResNet, DenseNet, EfficientNet, ConvNeXt)
   - Evaluate accuracy, precision, F1-score, and inference speed

4. **Lightweight Architectures**
   - Explore MobileNet, ShuffleNet, and SqueezeNet
   - Trade-off analysis: speed vs. accuracy

5. **Custom Lightweight CNNs**
   - Design and test small networks using depthwise separable convolutions
   - Assess feasibility for real-time use

6. **Classifier-Only Fine-Tuning**
   - Freeze feature extractors and tune the classifier head
   - Run grid search over optimizers, learning rates, dropout, and smoothing

7. **Final Evaluation**
   - Load best checkpoints and compare on train/val/test
   - Generate confusion matrices and F1-score plots
   - Save final results for reproducibility

---

## 🧠 Best Architectures

After a full evaluation of over 20 pretrained and custom CNN configurations, the top-performing models are:

- 🏆 **ConvNeXt-Tiny (FT_C6)**  
  - **Highest test accuracy: 93.48%**, F1-score: 0.93  
  - Excellent training stability and generalization  
  - Ideal for high-accuracy applications with moderate resource availability

- ⚖️ **ResNet34 (FT_R6)**  
  - Strong accuracy (87.92%) and F1-score (0.87)  
  - Lower inference time (0.00074 s/img) with robust results  
  - Best trade-off between speed, size, and performance among ResNets

🎖️ **Honorable Mentions**:
- **EfficientNet-B1** – 86.23% accuracy with only 6.6M parameters  
- **MobileNetV2** – 82.61% accuracy, extremely lightweight (2.28M params), and fast (0.00040 s/img)

---

## 📊 Final Results Summary

| Model              | Test Accuracy | F1-Score | Parameters | Inference Time |
|-------------------|---------------|----------|------------|----------------|
| ConvNeXt-Tiny      | **93.48%**    | **0.93** | 27.9M      | 0.00040 s/img  |
| ResNet34 (FT_R6)   | 87.92%        | 0.87     | 21.3M      | 0.00074 s/img  |
| EfficientNet-B1    | 86.23%        | 0.86     | **6.6M**   | 0.00098 s/img  |
| MobileNetV2        | 82.61%        | 0.83     | 2.28M      | **0.00040 s/img** |
| ShuffleNet V2      | 44.93%        | 0.40     | **1.3M**   | 0.00060 s/img  |

---

## ⚙️ Technologies Used

- Python 3.11
- PyTorch
- Torchvision
- Matplotlib, Seaborn
- Google Colab
- Google Drive (for data/results)

---

## 🧩 How to Reproduce the Pipeline

1. Download and unzip the dataset into the `./data/` directory.
2. Open and run the full notebook: `DL_Yoga_Pose_Recognition.ipynb`
3. Optional: Download model results and run final evaluation cells.
4. Explore results, train your own models, or modify architectures.

---

## 📌 Why This Matters

Yoga pose classification is a fine-grained visual task that demands **generalization**, **speed**, and **efficiency**. This project shows how modern transfer learning techniques and CNN design strategies can be combined to tackle such tasks effectively.

✅ From naive baselines to state-of-the-art models, we offer a clear, reproducible path for deep learning research in image classification.

---
