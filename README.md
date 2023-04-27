# Speech-Emotion-Recognition
![image](https://user-images.githubusercontent.com/94167271/234299174-e0514f9a-f82f-4f01-9734-33a17da85e63.png)



Emotional speech recognition aims at automatically identifying the emotional or physical state of a human being from his or her voice. The emotional and physical states of a speaker are known as emotional aspects of speech and are included in the so-called paralinguistic aspects.

Speech Emotion Recognition, abbreviated as SER, is the act of attempting to recognize human emotion and affective states from speech. This is capitalizing on the fact that voice often reflects underlying emotion through tone and pitch. This is also the phenomenon that animals like dogs and horses employ to be able to understand human emotion.

***Speech Emotion Recognition – Objective***

#### To build a model to recognize emotion from speech using the librosa and sklearn libraries on the TESS dataset.

#### dataset from kaggle https://www.kaggle.com/datasets/ejlok1/toronto-emotional-speech-set-tess

#### Content

There are a set of 200 target words were spoken in the carrier phrase "Say the word _' by two actresses (aged 26 and 64 years) and recordings were made of the set portraying each of seven emotions (anger, disgust, fear, happiness, pleasant surprise, sadness, and neutral). There are 2800 data points (audio files) in total.

The dataset is organised such that each of the two female actor and their emotions are contain within its own folder. And within that, all 200 target words audio file can be found. The format of the audio file is a WAV format

#### The data content is 

    OAF_angry
    OAF_disgust
    OAF_Fear
    OAF_happy
    OAF_neutral
    OAF_Pleasant_surprise
    OAF_Sad
    YAF_angry
    YAF_disgust
    YAF_fear
    YAF_happy
    YAF_neutral
    YAF_pleasant_surprised
    YAF_sad
    
#### NOTE- The data is collected by two age group (aged 26 and 64 years) so here, " OAF_ means older people and YAF_ mean younger people. "

### MFCC

MFCCs are a way to analyze and describe the unique characteristics of an audio signal, such as speech or music. They are commonly used in speech recognition, music genre classification, and speaker identification systems.

### CNN MODEL

        Model: "model"
        _________________________________________________________________
         Layer (type)                Output Shape              Param #   
        =================================================================
         input_1 (InputLayer)        [(None, 2400, 1)]         0         

         conv1d (Conv1D)             (None, 2388, 8)           112       

         max_pooling1d (MaxPooling1D  (None, 796, 8)           0         
         )                                                               

         dropout (Dropout)           (None, 796, 8)            0         

         conv1d_1 (Conv1D)           (None, 786, 16)           1424      

         max_pooling1d_1 (MaxPooling  (None, 262, 16)          0         
         1D)                                                             

         dropout_1 (Dropout)         (None, 262, 16)           0         

         conv1d_2 (Conv1D)           (None, 254, 32)           4640      

         max_pooling1d_2 (MaxPooling  (None, 84, 32)           0         
         1D)                                                             

         dropout_2 (Dropout)         (None, 84, 32)            0         

         conv1d_3 (Conv1D)           (None, 78, 64)            14400     

         max_pooling1d_3 (MaxPooling  (None, 26, 64)           0         
         1D)                                                             

         dropout_3 (Dropout)         (None, 26, 64)            0         

         flatten (Flatten)           (None, 1664)              0         

         dense (Dense)               (None, 256)               426240    

         dropout_4 (Dropout)         (None, 256)               0         

         dense_1 (Dense)             (None, 128)               32896     

         dropout_5 (Dropout)         (None, 128)               0         

         dense_2 (Dense)             (None, 14)                1806      

        =================================================================
        Total params: 481,518
        Trainable params: 481,518
        Non-trainable params: 0
        
        
#### Model result

#### After training model reach up to 99 % of accuracy on test data.

![image](https://user-images.githubusercontent.com/94167271/191080873-8642e19f-b03d-45dc-98f9-fb375517aa9e.png)


#### classification_report on Test  

                      precision    recall  f1-score   support

                   0       1.00      1.00      1.00        34
                   1       1.00      0.98      0.99        59
                   2       1.00      1.00      1.00        44
                   3       1.00      1.00      1.00        53
                   4       1.00      1.00      1.00        55
                   5       0.98      1.00      0.99        48
                   6       1.00      1.00      1.00        58
                   7       1.00      0.96      0.98        52
                   8       1.00      1.00      1.00        55
                   9       0.98      1.00      0.99        54
                  10       0.98      1.00      0.99        53
                  11       1.00      1.00      1.00        49
                  12       1.00      1.00      1.00        45
                  13       1.00      1.00      1.00        41

            accuracy                           1.00       700
           macro avg       1.00      1.00      1.00       700
        weighted avg       1.00      1.00      1.00       700

#### Confusion_matrix

![image](https://user-images.githubusercontent.com/94167271/191081282-a7d2cde0-d194-4fba-98f1-203fbd60a76e.png)

### validate model on famous MARVEL dialogue

![MARVEL](https://user-images.githubusercontent.com/94167271/210097817-f35aaf8e-d868-4f56-908e-8e1bcfb89729.gif)


#### Live demo on MARVEL famous dialogue like 

        Groot--"I am Groot”
        Tony stark--"I am iron man" 
        Antman - "oh my god"
        Loki-"I am falling for thirty minutes"

![Screenshot (385)cap](https://user-images.githubusercontent.com/94167271/210166724-f2c2b3d0-1a4f-4887-a122-980c38777d01.png)

# Face-emotion-detection-project

In a face emotion detection project, the goal is to build a system that can automatically identify and classify the emotion being expressed by a person in a given image or video frame. This can be used in a variety of applications, such as detecting emotions in customer service interactions, detecting emotions in social media posts, or detecting emotions in marketing research.

dataset-- https://www.kaggle.com/datasets/msambare/fer2013

The data consists of 48x48 pixel grayscale images of faces. The faces have been automatically registered so that the face is more or less centred and occupies about the same amount of space in each image.

The task is to categorize each face based on the emotion shown in the facial expression into one of seven categories (0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral). The training set consists of 28,709 examples and the public test set consists of 3,589 examples

#### Validation result

![image](https://user-images.githubusercontent.com/94167271/211168903-0ff9c624-8825-4f06-9aa4-ac521a064ea9.png)
Best Validation Accuracy Score 0.66520

use TestEmotionDetector.py to test model on video or webcam

#### webcam result on video

![Screenshot (emotion](https://user-images.githubusercontent.com/94167271/211168986-30826bd7-6dfd-47d1-9bd8-42c03fdf3629.png)

### Emotion detaction using Images (YOLO V8)

![image](https://user-images.githubusercontent.com/94167271/234352632-e079229e-4fa8-4874-af7a-8edc0b56f61a.png)
