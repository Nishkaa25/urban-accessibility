# Automated Urban Accessibility Mapping

## Overview
Urban navigation systems often ignore sidewalk-level accessibility, making it difficult for people with disabilities to navigate safely. This project uses computer vision to detect accessibility barriers such as potholes, broken pavements, and obstacles from street-level images.


> This project is based on a collaborative repository. My contributions include model training, evaluation, and result visualization.
---

## Objectives
- Detect accessibility barriers from street images  
- Identify obstacles like potholes, uneven surfaces, etc.  
- Build a system that can later be integrated with mapping tools  

---

## Dataset
- Source: Mapillary street-level images  
- Contains urban road and sidewalk images  

> Note: Dataset preprocessing and annotation were performed as part of team collaboration.

---

## Methodology

### 🔹 Preprocessing
- Removed corrupted and non-decodable images  
- Fixed EXIF rotation issues  
- Normalized all images to RGB format  
- Removed duplicates using SHA-256 hashing and perceptual hashing  
- Performed image quality checks:
  - Blur detection (Laplacian method)  
  - Darkness filtering  
- Resized images to **640 × 640**

---

### 🔹 Model
- YOLOv8 (PyTorch-based object detection model)

---

### 🔹 Training
- Dataset split into training and validation sets  
- Training pipeline included:
  - Data loading and resizing  
  - Data augmentation  
  - Forward pass  
  - Loss computation  
  - Backpropagation  

---

### 🔹 Evaluation
- Evaluated using:
  - mAP (Mean Average Precision)  
  - Precision and Recall  
- Monitored overfitting using training vs validation loss  

---

## Results
The model is able to detect accessibility barriers from street-level images.

<img width="640" height="640" alt="1117_jpg rf a1911e63285713373a8d39efad0b5906" src="https://github.com/user-attachments/assets/b67ab688-0c86-41c1-9292-76e679e997e2" />

<img width="640" height="640" alt="2019_jpg rf 29510d5f7a1bc8dab9b1bc340350eb67" src="https://github.com/user-attachments/assets/99edc0f9-061b-4ea8-9534-ad4fccdb8e24" />

<img width="640" height="640" alt="1030_jpg rf d71b1ccf57443c773c66ce25a245eaed" src="https://github.com/user-attachments/assets/8e70a112-6bb7-451f-b224-41f43d7eda1e" />

---

## My Contribution
- Trained and fine-tuned the YOLOv8 model on the accessibility dataset  
- Evaluated model performance using mAP, precision, and recall  
- Visualized detection outputs using OpenCV  
- Worked on understanding and implementing the training pipeline  

---

## Future Work
- GPS tagging of detected barriers  
- Accessibility-aware routing  
- Integration with mapping systems (Leaflet / Google Maps)  

---

## Tech Stack
- Python  
- YOLOv8  
- PyTorch  
- OpenCV  
- NumPy, Pandas  

---

## How to Run

1. Clone the repository:
   git clone https://github.com/Nishkaa25/urban-accessibility.git  
   cd urban-accessibility  

2. Install dependencies:
   pip install ultralytics opencv-python numpy pandas  

3. Run training:
   - Open notebooks/training.ipynb  
   - Execute all cells  

4. View results:
   - Check the results/ folder  

---

## Key Features
- Detects real-world accessibility barriers using computer vision  
- Uses YOLOv8 for object detection  
- Includes preprocessing pipeline for clean training data  
- Designed for future integration with mapping systems  

