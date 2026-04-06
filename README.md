# 🦟 Mosquito Species Object Detection with YOLOv8

Fine-tuning **YOLOv8m** to detect and classify mosquitoes into 6 species from images, using bounding box prediction and confidence-based submission.

## 📌 Overview

This project tackles a multi-class object detection task where mosquitoes must be located and identified by species. Built on YOLOv8 (medium variant) with custom augmentations and AdamW optimization, trained on the DLP Week 10 competition dataset.

## 🧠 Approach

- **Model:** YOLOv8m (pretrained on COCO, fine-tuned on mosquito data)
- **Classes:** 6 mosquito species — `aegypti`, `albopictus`, `anopheles`, `culex`, `culiseta`, `japonicus/koreicus`
- **Split:** 80% train / 20% validation (stratified by random seed)
- **Inference:** Highest-confidence detection per image selected for submission; fallback to `albopictus` if no detection

## 📁 Project Structure

```
mosquito-object-detection/
├── code.ipynb           # Main training & inference notebook 
└── README.md
```

## 🛠️ Tech Stack

- Python, PyTorch
- Ultralytics YOLOv8
- OpenCV (image dimension handling)
- scikit-learn (train/val split)
- Kaggle T4 GPU

## ⚙️ Key Training Parameters

| Parameter | Value |
|---|---|
| Model | YOLOv8m |
| Epochs | 50 |
| Batch size | 16 |
| Image size | 512×512 |
| Optimizer | AdamW |
| Learning rate | 0.0005 |
| Weight decay | 0.0005 |
| Early stopping patience | 5 |
| Mosaic augmentation | 0.8 |
| Mixup augmentation | 0.1 |
| Copy-paste augmentation | 0.1 |
| Horizontal flip | 0.5 |
| Vertical flip | Disabled (orientation matters) |

## 📊 Results

| Metric | Score |
|---|---|
| **Kaggle Test Score** | **0.81** |

