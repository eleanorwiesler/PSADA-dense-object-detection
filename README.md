# Dense Object Detection - Improving Dense Fish Detection with YOLOv10

## Overview

This project focuses on improving fish detection in natural environments using **YOLOv10** and a **Quasi-Simulated Annealing Data Augmentation (QSADA) Algorithm**. The primary goal is to enhance object detection performance in **crowded fish habitats**, where occlusions and varying water conditions make detection challenging.

We train and test our model using the **DeepFish dataset** and a manually annotated test set from **live-streamed footage in the Florida Keys**. Our approach significantly improves upon traditional YOLO-based models for dense object detection in real-world conditions.

## Key Features

- **YOLOv10-based Fish Detection**: Trained on **DeepFish dataset** with generated bounding box annotations.
- **Quasi-Simulated Annealing Data Augmentation (QSADA)**: Enhances model robustness for crowded object detection.
- **Live Florida Keys Dataset**: Evaluates real-world performance beyond controlled environments.
- **Bounding Box Generation**: Converts segmentation masks from DeepFish into YOLO-compatible annotations.
- **Improved Detection Performance**: QSADA model achieves **higher recall and precision**, detecting more than **double** the fish compared to the baseline.

## Dataset

- **DeepFish Dataset**: Contains images of fish in their natural habitat, including segmentation masks for annotation.
- **Augmented Training Data**: Copy-paste augmentation with **simulated annealing-inspired clustering**.
- **Florida Keys Dataset**: 50 manually annotated images collected from a **public underwater livestream**.

## Methodology

1. **Baseline Model**: Trained YOLOv10 on the **DeepFish dataset** using segmentation mask-based bounding boxes.
2. **Data Augmentation**: Implemented **QSADA**, modifying Deng et al.’s **copy-paste augmentation** with **simulated annealing** for natural fish clustering.
3. **Model Training**:
   - Baseline Model: **50 epochs**, **640x640 image size**.
   - QSADA Model: **28 epochs**, **augmented training data**.
4. **Testing**: Evaluated on **Florida Keys livestream images**, comparing **bounding box detection counts** with ground truth annotations.

## Results

- QSADA model detects **2x more fish** than the baseline model in **real-world crowded scenarios**.
- Achieves higher **Intersection over Union (IoU)** scores, improving **bounding box overlap** with ground truth.
- Faster convergence in training: QSADA model reaches **minimum loss in fewer epochs**.

## Installation & Usage

### Requirements
- Python 3.8+
- PyTorch
- OpenCV
- YOLOv10
- NumPy, Matplotlib

### Setup
```bash
git clone https://github.com/yourusername/dense-object-detection
cd dense-object-detection
pip install -r requirements.txt
