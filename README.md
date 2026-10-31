# Real-Time Traffic Density Estimation Using YOLOv8

## Project Overview

This project focuses on **Real-Time Traffic Density Estimation using YOLOv8**. It uses computer vision and deep learning techniques to detect vehicles in images and videos, count vehicles in selected road lanes, and estimate traffic intensity.

The YOLOv8 object detection model is fine-tuned on a vehicle-specific dataset to improve vehicle detection from top-view images.

The system classifies traffic intensity into two categories:

- **Heavy Traffic**
- **Smooth Traffic**

## Project Objectives

- Detect vehicles using YOLOv8.
- Fine-tune a pretrained YOLOv8 model on a vehicle dataset.
- Estimate traffic density by counting vehicles in selected road regions.
- Analyze traffic intensity lane-wise.
- Perform vehicle detection on images and videos.
- Evaluate model performance using different metrics.
- Export the trained model into ONNX format.

## Technologies Used

- Python
- YOLOv8 (Ultralytics)
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- PyYAML
- PIL
- Weights & Biases (WandB)
- Kaggle Notebook

## Dataset

**Top-View Vehicle Detection Image Dataset**

The project uses a vehicle detection dataset containing:

| Dataset | Number of Images |
|---|---:|
| Training | 536 |
| Validation | 90 |
| Total | 626 |

- Image resolution: 640 × 640 pixels
- Dataset format: YOLOv8
- Class: Vehicle
- Includes vehicles such as cars, trucks, and buses.

Dataset Link: [Top-View Vehicle Detection Image Dataset](https://www.kaggle.com/datasets/farzadnekouee/top-view-vehicle-detection-image-dataset)

## Project Workflow

1. Install and import required libraries.
2. Load the pretrained YOLOv8 Nano model (`yolov8n.pt`).
3. Perform initial vehicle detection using the COCO pretrained model.
4. Explore and prepare the vehicle detection dataset.
5. Fine-tune YOLOv8 using transfer learning.
6. Train the model for 100 epochs.
7. Evaluate the model using learning curves, confusion matrix, precision, recall, and mAP.
8. Perform inference on validation images, an unseen test image, and an unseen test video.
9. Estimate traffic density by counting vehicles in selected road lanes.
10. Export the trained model into ONNX format.

## Model Training Parameters

| Parameter | Value |
|---|---|
| Model | YOLOv8 Nano |
| Pretrained Weights | yolov8n.pt |
| Epochs | 100 |
| Image Size | 640 |
| Batch Size | 32 |
| Optimizer | Auto |
| Initial Learning Rate | 0.0001 |
| Dropout | 0.1 |
| Patience | 50 |
| Random Seed | 0 |

## Model Performance

The notebook reports the following validation metrics:

| Evaluation Metric | Result |
|---|---:|
| Precision | 91.6% |
| Recall | 93.8% |
| mAP@50 | 97.5% |
| mAP@50-95 | 74.2% |
| Fitness | 76.5% |

These values are the reported validation results in the notebook.

## Traffic Density Estimation

The project estimates traffic intensity by counting detected vehicles inside predefined road-lane regions.

- Detect vehicles frame by frame.
- Count vehicles in the left and right lane regions.
- Use a threshold of 10 vehicles to identify heavy traffic.
- Display vehicle counts and traffic intensity on video frames.
- Save the annotated traffic analysis video.

## Model Evaluation

The project includes:

- Training and validation loss curves.
- Box loss analysis.
- Classification loss analysis.
- Distribution Focal Loss analysis.
- Confusion matrix visualization.
- Precision and recall.
- Mean Average Precision (mAP).

## Model Export

The trained YOLOv8 model is exported into **ONNX format** for cross-platform deployment.

```python
best_model.export(format='onnx')
```

## Installation

Install the required libraries:

```bash
pip install ultralytics opencv-python numpy pandas matplotlib seaborn pyyaml pillow
```

## How to Run

1. Download or clone this repository.
2. Open the notebook in Kaggle or Google Colab.
3. Download the dataset from Kaggle.
4. Configure the dataset paths.
5. Run the notebook cells sequentially.
6. Train and evaluate the YOLOv8 model.
7. Test the model on images and videos.
8. View the traffic density estimation output.

## Applications

- Smart traffic management systems.
- Traffic congestion monitoring.
- Smart city development.
- Road traffic analysis.
- Vehicle counting and monitoring.
- Urban planning and transportation management.

## Author

**PRAJAKTA SUNIL BIDRE**
