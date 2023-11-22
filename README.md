# Speech Emotion Recognition Project 🎧 🎤 🎶🎵 🔊🔉 🔈 🎼 🎸 🎷 

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


# Facial Emotion Detection using YOLOv8  😊 😢 😠 😲 😄 😭 😎 😕 😴🥳

Facial emotion detection has become a vital tool in psychology, marketing, and law enforcement. This project utilizes the YOLOv8 model to analyze facial expressions and detect emotional states such as happiness, sadness, anger, and surprise.

## Steps

## 1. Downloading Images

Begin by gathering a dataset of facial images. Use tools like the "Download All Images" Chrome extension to download images related to various emotional states (e.g., happy face, sad face, angry face).

## 2. Labeling Images

Label the downloaded images using a tool like Roboflow. Manually annotate facial features and assign emotional states to each face. Roboflow provides a user-friendly interface and various labeling tools. After labeling, download the data as a zip file.

## 3. Training on YOLOv8 on Google Colab

Train your facial emotion detection model using YOLOv8 on Google Colab, a free platform with GPU support. Follow these steps:

            !pip install ultralytics
            from google.colab import drive
            drive.mount('/content/drive')
         
             # Unzip dataset
            !unzip /content/drive/Face-emotion-detection-YOLO-v8/yolov8.zip
         
            # YOLOv8 requires a YAML file (Roboflow generates one)
            !yolo task=detect mode=train model=yolov8x.pt data=/content/data.yaml epochs=100 imgsz=640 batch=8 project=/content/drive/report "save=True"


Training results will be saved in the specified project destination.

## 4. Real-Time Video Predictions

After training your model, predict emotions in real-time video streams using Python and OpenCV. Integrate the Haar Cascade Classifier to detect faces and pass each face through your YOLOv8 model for emotion prediction.

         !yolo task=detect mode=predict model=/content/drive/MyDrive/best.pt conf=0.55 source=/content/drive/video save=True

## 5. Integration into Real-World Application
Integrate your model into a real-world application by creating a user interface tailored to your specific use case. Design a captivating user experience for an immersive emotional journey.

## 6. Test with Video Collection
Download a collection of videos to test your model in action. Witness your YOLOv8 model predicting emotions in real-time with the provided videos.

## Note: The code snippets assume a Google Colab environment. Adjust paths and configurations accordingly for other setups.

## Conclusion

Building a facial emotion detection model using YOLOv8 is a complex but rewarding process with practical applications in computer vision. Follow these steps to create your model and contribute to the exciting field of facial emotion recognition.
