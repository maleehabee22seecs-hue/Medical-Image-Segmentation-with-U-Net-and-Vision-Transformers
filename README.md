# 🩺 Medical Image Segmentation with U-Net and Vision Transformers

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?logo=pytorch)
![Google Colab](https://img.shields.io/badge/Platform-Google%20Colab-F9AB00?logo=googlecolab)
![Medical Imaging](https://img.shields.io/badge/Domain-Medical%20Imaging-success)
![ISIC 2018](https://img.shields.io/badge/Dataset-ISIC%202018-green)
![Vision Transformer](https://img.shields.io/badge/Model-TransUNet-purple)

</p>

---

## 📌 Overview

This project presents a comparative study between a **convolutional U-Net** and a **Transformer-enhanced TransUNet** for automated skin lesion segmentation using the **ISIC 2018 Challenge Dataset**.

While U-Net serves as a strong CNN baseline, TransUNet combines convolutional feature extraction with Vision Transformer self-attention to capture long-range contextual information. This repository investigates whether transformer-based segmentation provides measurable improvements under practical hardware constraints.

---

## ✨ Key Features

- Implementation of **U-Net** from scratch
- Fine-tuned **TransUNet** with ImageNet-21k pretrained encoder
- Progressive unfreezing strategy for stable transformer optimization
- Differential learning rates for encoder and decoder
- Extensive Albumentations-based data augmentation
- Mixed Precision (FP16) training in Google Colab
- Evaluation using Dice Score, IoU, Recall and Specificity
- Comparative performance analysis between CNNs and Vision Transformers

---

## 📊 Results

| Model | Dice | IoU | Recall | Specificity |
|------|------:|------:|------:|------:|
| U-Net | **0.9014** | 0.8206 | 0.8830 | 0.9763 |
| TransUNet | **0.9139** | **0.8415** | **0.9043** | 0.9767 |

### Highlights

- ✅ Dice Score improved from **0.9014 → 0.9139**
- ✅ Higher Recall for improved lesion detection
- ✅ Better boundary segmentation using Vision Transformers
- ✅ Stable optimization through progressive fine-tuning

---

## 🧠 Models Compared

### U-Net

- Encoder-decoder CNN architecture
- Skip connections
- Trained from scratch
- Lightweight and computationally efficient

### TransUNet

- CNN encoder + Vision Transformer
- Global self-attention
- ImageNet-21k pretrained weights
- Progressive unfreezing
- Differential learning rates

---

## 🗂 Dataset

**ISIC 2018 Skin Lesion Segmentation Challenge**

- 2,594 dermoscopic images
- Binary lesion masks
- Images resized to **256×256**
- 90/10 Train-Validation split

---

## ⚙️ Training Strategy

To overcome optimization instability commonly observed in Vision Transformers:

- Stage 1
  - Freeze pretrained encoder
  - Train decoder only

- Stage 2
  - Progressively unfreeze encoder
  - Apply differential learning rates
  - Fine-tune the complete network

This strategy significantly improved convergence and validation performance.

---

## 🛠 Tech Stack

- Python
- PyTorch
- Torchvision
- Transformers
- timm
- Albumentations
- NumPy
- OpenCV
- Matplotlib
- Google Colab

---

## 📁 Repository Structure

```
Medical-Image-Segmentation-with-U-Net-and-Vision-Transformers/

│── notebooks/
│   └── unet_vs_transunet_isic2018.ipynb

│── docs/
│   └── paper.pdf

│── images/

│── README.md
│── requirements.txt
│── LICENSE
```

---

## 🚀 Getting Started

Clone the repository

```bash
git clone https://github.com/maleehabee22seecs-hue/Medical-Image-Segmentation-with-U-Net-and-Vision-Transformers.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```bash
jupyter notebook notebooks/unet_vs_transunet_isic2018.ipynb
```

or simply open it directly in **Google Colab**.

---

## 📷 Sample Results

> *(Add screenshots here)*

Suggested images:

- Original Image
- Ground Truth Mask
- U-Net Prediction
- TransUNet Prediction

---

## 📈 Future Improvements

- Swin-UNet implementation
- Attention U-Net comparison
- Lightweight Vision Transformers
- Knowledge Distillation
- Real-time inference optimization
- ONNX/TensorRT deployment

---

## 📄 Paper

The complete IEEE-style paper describing the methodology, experiments and analysis is available in:

```
IEEE_deep learning, image segmentation.pdf
```

---

## 👥 Authors

**Maleeha**
**Rayyan Naeem**

Electrical Engineering

National University of Sciences and Technology (NUST)

Islamabad, Pakistan

---

## ⭐ If you found this repository useful

Please consider giving it a ⭐ on GitHub.
