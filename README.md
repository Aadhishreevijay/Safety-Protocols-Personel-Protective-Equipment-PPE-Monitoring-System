# Safety-Protocols-Personel-Protective-Equipment-PPE-Monitoring-System

PPE (Personal Protective Equipment) detection is crucial for ensuring safety on construction sites. This project leverages YOLOv8, a state-of-the-art deep learning model, to accurately detect and localize PPE such as helmets, face shields, jackets, dust masks, eye wear, gloves, and protective boots in real time.

## Table of Contents:
- Introduction
- Installation
- Dataset
- Image & Object Detection
- Results
- References

## Introduction
This project utilizes YOLOv8, an advanced deep learning model with 218 layers and 25.8 million parameters, to detect PPE items on construction sites. YOLOv8's precision and recall metrics, along with its mAP (mean average precision), make it an effective tool for enhancing safety by ensuring workers are properly equipped with necessary protective gear.

## Objects Detected

The following PPE items are identified:

- Helmets
- Face Shields
- Jackets
- Dust Masks
- Eye Wear
- Gloves
- Protective Boots

## Installation
To run this project, you'll need to install several packages and dependencies. Follow the steps below:

1. Start by cloning the repository and installing the required packages:
   
          git clone https://github.com/Aadhishreevijay/Safety-Protocols-Personel-Protective-Equipment-PPE-Monitoring-System.git
   
          cd Safety-Protocols-Personel-Protective-Equipment-PPE-Monitoring-System
   
          pip install -r requirements.txt
2. Install Python Packages:

          pip install IPython ultralytics==8.0.0 roboflow
3. Check NVIDIA GPU (Optional but recommended for faster training):

          !nvidia-smi
4. Install YOLOv8:
   
          pip install ultralytics==8.0.0
   
5. Set Up Roboflow:
It's recommended to copy the Roboflow code instead of downloading the dataset as a folder. When copying the code, make sure it's in YOLOv5 format:

          from roboflow import Roboflow
          rf = Roboflow(api_key="4hIhYKGrnWHaWXRqZsZg")
          project = rf.workspace("objet-detect-yolov5").project("eep_detection-u9bbd")
          dataset = project.version(1).download("yolov5")

## Dataset

The dataset used for this project is hosted on Roboflow. You can access and download the dataset from the following link:

[EEP Detection Dataset on Roboflow.](https://universe.roboflow.com/eepdatasets-fe5sq/eep_detect/dataset/11)

## For Video & Image Detection

   - For video detection, use [video_detect.py](https://github.com/Aadhishreevijay/Safety-Protocols-Personel-Protective-Equipment-PPE-Monitoring-System/blob/main/video_detect.py)<br />
   - For image detection, use [image_detect.py](https://github.com/Aadhishreevijay/Safety-Protocols-Personel-Protective-Equipment-PPE-Monitoring-System/blob/main/image_detect.py)

## Results

### Metrics:

- Precision: 0.926
- Recall: 0.88
- mAP (IoU=0.5): 0.91
- mAP (0.5:0.95): 0.651

### Visual Results:

Below are some visualizations of the model's performance:

1. Confusion Matrix:
   - This matrix shows the true positive, false positive, true negative, and false negative rates.
     <img width="431" alt="image" src="https://github.com/user-attachments/assets/b6acaa68-580f-4a12-a922-a38b0e8f271c">
     
2. F1 Curve:
   - The F1 curve demonstrates the balance between precision and recall.
     ![image](https://github.com/user-attachments/assets/b5ffa18e-dfd0-4b56-bb4e-7ee254cf294e)
     
3. Precision-Recall (PR) Curve
   - This curve shows the trade-off between precision and recall.
     ![image](https://github.com/user-attachments/assets/d7b285e2-b0fe-43ee-a6d9-1ce36ac6719a)
     
4. Precision Curve (P)
   - Precision curve at various thresholds.
    ![image](https://github.com/user-attachments/assets/8f3b4cc9-6d28-4330-bf57-6e264303f45d)
     
5. Recall Curve (R)
   - Recall curve at different confidence thresholds.
     ![image](https://github.com/user-attachments/assets/d0c2c4c2-6a02-4e1e-98f0-7d101b12cd45)
     
6. Loss Curves:
   
   ![image](https://github.com/user-attachments/assets/56b92edd-13aa-4e73-8936-839168586e76)

8. Sample Image Prediction:
   
   ![image](https://github.com/user-attachments/assets/057bdc86-628e-4df2-a252-08ee746f4712)
   
   ![image](https://github.com/user-attachments/assets/72ba3ae6-3e64-4b28-a447-8a5a71787f92)

## Recommendation: 

 - If running this on Google Colab, it’s recommended to change the runtime to GPU for faster processing.
 - Navigate to Runtime -> Change runtime type and select GPU under Hardware accelerator.
 - Images and Videos are given in [images and videos](https://drive.google.com/drive/folders/1tYeF5XuI3oUtx8FPSVdw0bywM8p0NcHA?usp=sharing)
 - Find the required weights *best.pt*, *last.pt*, *yolov8m.py* in [weights](https://drive.google.com/drive/folders/1dJXYuj2NePk7sxry7UvGel7-YVtnxN33?usp=sharing)

## Reference
- Dataset: [Roboflow EEP Detect Dataset](https://universe.roboflow.com/eepdatasets-fe5sq/eep_detect/dataset/11)
- Ultralytics Documentation: [docs.ultralytics.com](https://docs.ultralytics.com/)
- Ultralytics GitHub Repository: [github.com/ultralytics/ultralytics](https://github.com/ultralytics/ultralytics)
- Roboflow Universe: [universe.roboflow.com](https://universe.roboflow.com/)

   

