# Diabetic Retinopathy using CNN and Transfer Learning:

- Diabetic retinopathy is the leading cause of blindness in the working-age population of the developed world. It is estimated to affect over 93 million people.
The US Center for Disease Control and Prevention estimates that 29.1 million people in the US have diabetes and the World Health Organization estimates that 347 million people have the disease worldwide. Diabetic Retinopathy (DR) is an eye disease associated with long-standing diabetes. Around 40% to 45% of Americans with diabetes have some stage of the disease. Progression to vision impairment can be slowed or averted if DR is detected in time, however this can be difficult as the disease often shows few symptoms until it is too late to provide effective treatment.
Currently, detecting DR is a time-consuming and manual process that requires a trained clinician to examine and evaluate digital color fundus photographs of the retina. By the time human readers submit their reviews, often a day or two later, the delayed results lead to lost follow up, miscommunication, and delayed treatment.

## This project contains the followind directories
	data
		-> images
				-> sampleimage0.jpeg
		-> trainLabels.csv
    DiabeticRetinopathy.ipynb

- The project has been taken from Kaggle which was hosted 4 years back, for reference please look at 
https://www.kaggle.com/c/diabetic-retinopathy-detection/overview
- The training data can be downloaded from Kaggle itself, using this command 
   - kaggle competitions download -c diabetic-retinopathy-detection 
- once you accept the Late submission you'll be allowed to download the data.

- Everything else w.r.t the code is in the DiabeticRetinopathy.ipynb

## CNN Architecture

- This project used Transfer learning using InceptionV3 as pretrained model as base model.

 
    Layer (Type)           Output Shape              Param #   
    _________________________________________________________________
    input_1 (InputLayer)         (None, 512, 512, 3)       0         
    _________________________________________________________________
    inception_v3 (Model)         (None, 14, 14, 2048)      21802784  
    _________________________________________________________________
    flatten_1 (Flatten)          (None, 401408)            0         
    _________________________________________________________________
    dropout_1 (Dropout)          (None, 401408)            0         
    _________________________________________________________________
    dense_1 (Dense)              (None, 500)               200704500 
    _________________________________________________________________
    batch_normalization_95 (Batc (None, 500)               2000      
    _________________________________________________________________
    dense_2 (Dense)              (None, 5)                 2505
   

## Accuracy

- Accuracy obtained by training and testing above model is as follows:

- 400/400 [==============================] - 2s 32ms/step

    Accuracy on Test Data: 0.78%
                  precision    recall  f1-score   support

               0       0.82      0.95      0.88        39
               1       0.25      0.25      0.25         4
               2       1.00      0.14      0.25         7

        accuracy                           0.78        50
       macro avg       0.69      0.45      0.46        50
    weighted avg       0.80      0.78      0.74        50

			