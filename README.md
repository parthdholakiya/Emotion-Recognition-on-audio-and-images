# Speech-Emotion-Recognition

Emotional speech recognition aims at automatically identifying the emotional or physical state of a human being from his or her voice. The emotional and physical states of a speaker are known as emotional aspects of speech and are included in the so-called paralinguistic aspects.

Speech Emotion Recognition, abbreviated as SER, is the act of attempting to recognize human emotion and affective states from speech. This is capitalizing on the fact that voice often reflects underlying emotion through tone and pitch. This is also the phenomenon that animals like dogs and horses employ to be able to understand human emotion.

***Speech Emotion Recognition – Objective***

To build a model to recognize emotion from speech using the librosa and sklearn libraries and the TESS dataset.

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
    
#### NOTE-  The data is colacted by two age group (aged 26 and 64 years) so here, " OAF_ means older peaple and YAF_ mean younger peaple. " 

### MFCC

Mel-frequency cepstral coefficients (MFCCs) are coefficients that collectively make up an MFC. They are derived from a type of cepstral representation of the audio clip (a nonlinear "spectrum-of-a-spectrum").








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

![image](https://user-images.githubusercontent.com/94167271/210097460-af571950-818d-4440-8624-c67412a0d245.png)
![MARVEL](https://user-images.githubusercontent.com/94167271/210097817-f35aaf8e-d868-4f56-908e-8e1bcfb89729.gif)


#### After training and testing model predicted emotion in MARVEL famous dialogue like "I am Groot”, "I am iron man" ," he's friend from work"  it went very well.

![Screenshot (360)](https://user-images.githubusercontent.com/94167271/191084474-75892963-abcc-468e-be0d-368af9bcab5b.png)


