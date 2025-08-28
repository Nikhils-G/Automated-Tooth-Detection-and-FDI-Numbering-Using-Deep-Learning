# Automated-Tooth-Detection-and-FDI-Numbering-Using-Deep-Learning

## Project Overview

This project focuses on detecting and numbering teeth in dental X-ray or oral images using a **YOLO-based deep learning model**.
The goal is to help automate dental image analysis, making it easier for dentists and researchers to quickly identify, label, and analyze teeth.

The trained model achieved the following evaluation metrics:

* **Precision**: 0.8579
* **Recall**: 0.8886
* **mAP\@50**: 0.7861
* **mAP\@50-95**: 0.6329

These results show that the model performs reliably in detecting most teeth and can serve as a strong baseline for further improvements.

---

## Objectives

1. Detect individual teeth in dental images.
2. Assign numbering to each detected tooth using the **FDI World Dental Federation system**.
3. Build a foundation for future clinical or research applications in dental imaging.

---

##  Workflow

### 1. Data Preparation

* Dental images were collected and annotated for bounding boxes of teeth.
* Annotations were stored in YOLO format for training.

### 2. Model Training

* YOLOv8 model was trained on the dataset.
* Achieved good precision and recall scores, showing effective tooth detection.

### 3. Evaluation

* Model was evaluated using **Precision, Recall, and mAP** scores.
* Results show strong performance in detecting teeth correctly.

### 4. Post-Processing (Planned)

* Separate upper vs. lower arch (Y-axis clustering).
* Divide left vs. right quadrants (X-midline).
* Assign sequential FDI numbering within quadrants.
* Handle missing teeth by detecting large gaps.

 Due to GPU limitations, the **post-processing stage is not yet implemented**, but the logic and plan are clearly defined for future work.

---

##  Technologies Used

* **Python**
* **YOLOv8 (Ultralytics)**
* **PyTorch**
* **OpenCV** (for image handling and visualization)
* **NumPy, Pandas, Matplotlib** (for evaluation and analysis)

---

## Results

Confusion matrix and detection results show that the model successfully detects most teeth.

**Best Scores Achieved:**

* Precision → 0.8579
* Recall → 0.8886
* mAP\@50 → 0.7861
* mAP\@50-95 → 0.6329

---

## How to Run the Project

1. Clone this repository

   ```bash
   git clone https://github.com/your-username/dental-tooth-detection.git
   cd dental-tooth-detection
   ```

2. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```

3. Train the model (if needed)

   ```bash
   yolo detect train data=data.yaml model=yolov8s.pt epochs=100 imgsz=640
   ```

4. Run inference on new images

   ```bash
   yolo detect predict model=runs/detect/train/weights/best.pt source=your_test_images/
   ```

---
##  Conclusion
This project proves that deep learning can be applied successfully for dental image analysis and lays a strong foundation for the next steps, which would include implementing post-processing logic, refining detection results, and testing on larger datasets for improved accuracy.
