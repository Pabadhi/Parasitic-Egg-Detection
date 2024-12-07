# Parasitic Egg Detection using RTMDet in MMDetection

This repository contains the code and resources for a machine learning model designed to detect parasitic eggs in microscopic images. The model is built using **RTMDet** within the **MMDetection** framework.

---

## Problem Description

Intestinal parasitic infections are a leading cause of morbidity worldwide, particularly in tropical and subtropical regions. According to the **World Health Organization (WHO)**:
- Around **1.5 billion people** (24% of the global population) were infected with soil-transmitted helminth infections (STH) in 2020.
- Over **800 million children** required preventive chemotherapy for STH in the same year.

These infections often lead to:
- Diarrhea
- Malnutrition
- Anemia
- Growth failure in children

Traditional diagnostic methods rely on direct examination in laboratories, which are:
- **Time-consuming**
- **Low in sensitivity**
- **Heavily dependent** on skilled medical technologists

This project addresses these challenges by automating parasitic egg detection in images using machine learning.

---

## Approach

### Custom Configuration
The detection model is customized using **RTMDet** within MMDetection. Key modifications include:
- **Dataset Root**: The dataset is stored at `/content/output_directory/5-fold/fold-0/`.
- **Batch Size & Workers**: Adjusted for optimal performance during training.
- **Learning Rate**: Fine-tuned for better convergence.
- **Classes & Color Palette**: The model detects **11 classes** of parasitic eggs, each with a unique color representation in the output.

The custom configuration script is saved as `config_parasitic` at:
`/content/mmdetection/configs/rtmdet/rtmdet_tiny_1xb4-20e_.py`.

---

## Preprocessing

Before training, the dataset is preprocessed using the **Sahi** slicing library. This step ensures:
- Proper splitting of images and labels.
- Effective training of the model on smaller slices of data.

---

## Training

To train the model with the prepared configuration, use the following command:
```bash
python tools/train.py /content/mmdetection/configs/rtmdet/rtmdet_tiny_1xb4-20e_.py

