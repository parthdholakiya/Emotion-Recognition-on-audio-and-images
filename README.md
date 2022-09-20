# Speech-Emotion-Recognition
Speech Emotion Recognition, abbreviated as SER, is the act of attempting to recognize human emotion and affective states from speech. This is capitalizing on the fact that voice often reflects underlying emotion through tone and pitch. This is also the phenomenon that animals like dogs and horses employ to be able to understand human emotion.

***Speech Emotion Recognition – Objective***

To build a model to recognize emotion from speech using the librosa and sklearn libraries and the TESS dataset.

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
    
#### NOTE-  The data is colacted by two age group (aged 26 and 64 years) so here, " OAF_ means older peaple and YAF_ mean younger peaple. " 

### MFCC

Mel-frequency cepstral coefficients (MFCCs) are coefficients that collectively make up an MFC. They are derived from a type of cepstral representation of the audio clip (a nonlinear "spectrum-of-a-spectrum").




![image](https://user-images.githubusercontent.com/94167271/191076729-b6a3ff9b-ee44-4f26-8e7a-b4b226bcc691.png)



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

#### Confusion_matrix

![image](https://user-images.githubusercontent.com/94167271/191081282-a7d2cde0-d194-4fba-98f1-203fbd60a76e.png)

#### After training and testing model predicted emotion in MARVEL famous dialogue like "I am Groot”, "I am iron man" ," he's friend from work"  it went very well.

![Screenshot (360)](https://user-images.githubusercontent.com/94167271/191084474-75892963-abcc-468e-be0d-368af9bcab5b.png)


