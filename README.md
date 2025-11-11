# Project: Bike Helmet Detection using YOLOv8
  Description: >
    A computer vision project that detects whether a person is wearing a helmet or not
    using a custom-trained YOLOv8 model. Developed in Google Colab as part of an internship
    project with a custom bike helmet dataset.
# Author:
  Name: Debdut Nandy 
  Role: AI & ML Enthusiast 
  Email: debdut937@gmail.com 
  GitHub: https://github.com/Deb124-source 
  license: MIT License © 2025 Debdut Nandy 

# Features:
  - Detects "Helmet" and "No Helmet" in images and videos.
  - Supports real-time webcam and video inference.
  - Custom-trained YOLOv8 model using bike helmet dataset.
  - Runs efficiently on Google Colab (Tesla T4 GPU).

# Model:
  type: "YOLOv8" 
 
  framework: "Ultralytics"
  
  parameters:
    classes: ["Helmet", "No Helmet"]
    epochs: 10
    image_size: 640
    device: "Tesla T4 GPU"
 
  metrics:
    - class: "With Helmet"
      mAP50: 0.858
      precision: 0.78
      recall: 0.84
    - class: "Without Helmet"
      mAP50: 0.640
      precision: 0.77
      recall: 0.54
    - overall:
        mAP50: 0.749
        precision: 0.776
        recall: 0.695

# Structure:
   Helmet-Detection/:
   
    1. Helmet_Detection.ipynb: "Main Colab notebook for training, testing, and inference"
    
    2. dataset/:
        data.yaml: "YOLO dataset configuration file"
        train/: "Training images and labels"
        val/: "Validation images and labels"
        test/: "Optional test images and labels"
   
    3. models/:
        best.pt: "Trained YOLOv8 model weights"
 
    4. runs/:
        detect/: 
          train6/: "Training outputs (metrics, graphs, weights)"
          predict/: "Predictions from test images/videos"
    
    5. requirements.txt: "Dependencies list"
    
    6. README.md: "Project overview and documentation"
    
    7. .gitignore: "Ignored files and folders for GitHub"

# Requirements:
 
  - ultralytics==8.3.223
 
  - torch>=2.0
 
  - opencv-python
 
  - matplotlib
 
  - numpy
 
  - pandas

# Commands:
  setup:
   
    - "git clone https://github.com/<your-username>/Helmet-Detection.git"
    
    - "cd Helmet-Detection"
   
    - "pip install -r requirements.txt"
 
  inference:
   
    image: "!yolo detect predict model=models/best.pt source='test_image.jpg' save=True"
    
    video: "!yolo detect predict model=models/best.pt source='test_video.mp4' save=True"


colab:
 
  usage:
   
    - "Upload Helmet_Detection.ipynb to Google Colab"
   
    - "Mount Google Drive: drive.mount('/content/drive')"
   
    - "Run cells step by step to train, validate, and test the model"
  
  outputs:
   
    - "Training metrics and graphs in runs/detect/train6/"
   
    - "Predicted outputs in runs/detect/predict/"

# Technologies:
  
  - Python
  
  - Ultralytics YOLOv8
 
  - PyTorch
  
  - OpenCV
  
  - Google Colab

