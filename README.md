# Speech Emotion Recognition Project

## Overview

This project focuses on Speech Emotion Recognition (SER) using Convolutional Neural Networks (CNN) and Mel-frequency cepstral coefficients (MFCCs). It involves training a model to recognize emotions in speech audio files, and it achieved remarkable accuracy on the Toronto Emotional Speech Set (TESS) dataset.

## Project Structure

- **Audio Processing and Feature Extraction:** The initial part of the project involves loading audio files, extracting Mel-frequency cepstral coefficients (MFCCs), and preparing the data for training.

- **Model Training:** A CNN architecture is employed for training the emotion recognition model. The model is compiled with categorical crossentropy loss and Adam optimizer.

- **Model Checkpoint:** The ModelCheckpoint callback is utilized to save the model with the highest validation accuracy during training.

- **Training History Plotting:** The training history, including accuracy and validation accuracy, is plotted to visualize the model's learning progress over epochs.

- **Model Evaluation:** The model is evaluated on a test set, and the confusion matrix and classification report are generated to assess its performance.

- **Prediction on New Audio Files:** The trained model is validated on new audio files, showcasing its ability to predict emotions in unseen data.

## Requirements

- Python libraries: librosa, numpy, matplotlib, IPython, tensorflow, scikit-learn
- Additional dependencies: py7zr (for unzipping 7z files)

## Getting Started

1. Install the required dependencies:

   ```bash
   pip install librosa numpy matplotlib IPython tensorflow scikit-learn py7zr

## Model Performance

The trained model achieves exceptional performance on the test set, demonstrating its capability to accurately recognize emotions in speech. The classification report provides insights into precision, recall, and F1-score for each emotion category.

## Predictions on New Audio Files

The model is tested on various audio files containing different emotional expressions, showcasing its versatility in recognizing emotions in real-world scenarios.

## Conclusion

This Speech Emotion Recognition project serves as a valuable tool for understanding and implementing emotion recognition in speech audio. The combination of CNN architecture and MFCC feature extraction proves effective in capturing emotional patterns in speech.


# Facial Emotion Detection using YOLOv8

Facial emotion detection is a crucial tool in various fields such as psychology, marketing, and law enforcement. This project guides you through the process of building a facial emotion detection model using YOLOv8.

## Overview

Facial emotion detection has become an important tool in various fields like psychology, marketing, and law enforcement. It involves using computer algorithms to analyze facial expressions in images or videos and detect emotional states such as happiness, sadness, anger, and surprise. This project utilizes YOLOv8, a popular object detection algorithm, to achieve facial emotion recognition.

## Table of Contents

- [Step 1: Downloading Images](#step-1-downloading-images)
- [Step 2: Labeling Images](#step-2-labeling-images)
- [Step 3: Training on YOLOv8 on Google Colab](#step-3-training-on-yolov8-on-google-colab)
- [Step 4: Real-Time Video Predictions](#step-4-real-time-video-predictions)
- [Conclusion](#conclusion)
- [References](#references)

## Step 1: Downloading Images

To start, gather a dataset of facial images. Use tools like the "Download All Images" Chrome extension to download multiple images at once from sources like Google Images. Search for images related to different emotional states (e.g., happy face, sad face, angry face).

## Step 2: Labeling Images

Label the downloaded images using a tool like Roboflow. Manually annotate facial features (eyes, nose, mouth, eyebrows) and assign emotional states to each face (e.g., happy, sad, angry). Roboflow provides a user-friendly interface and various labeling tools.

After labeling, download your data as a zip file.

## Step 3: Training on YOLOv8 on Google Colab

Train your facial emotion detection model using YOLOv8. YOLOv8 is an object detection algorithm utilizing a deep neural network to identify objects in images and videos. Use Google Colab for free GPU-based training.

```bash
!pip install ultralytics
from google.colab import drive
drive.mount('/content/drive')

# Unzip dataset
!unzip /content/drive/Face-emotion-detection-YOLO-v8/yolov8.zip

# YOLOv8 requires a YAML file, luckily Roboflow generates one
!yolo task=detect mode=train model=yolov8x.pt data=/content/data.yaml epochs=100 imgsz=640 batch=8 project=/content/drive/report "save=True"



Training will take time depending on your system. Training metrics and results will be saved in the specified project destination.

# Step 4: Real-Time Video Predictions

Congratulations on training your model! Now, predict emotions in real-time video streams. Use Python and OpenCV to detect faces in real-time video. Integrate the Haar Cascade Classifier to identify faces, then pass each face through your YOLOv8 model for emotion prediction.

!yolo task=detect mode=predict model=/content/drive/MyDrive/best.pt conf=0.55 source=/content/drive/video save=True




# Conclusion

Building a facial emotion detection model with YOLOv8 is a complex but rewarding process. This model has practical applications in computer vision. Follow these steps to create your model and contribute to the exciting field of facial emotion recognition.

# References

Download All Images Chrome Extension
