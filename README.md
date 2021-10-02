# About Datasets

### Content
The dataset contains 2 folders

- Infected
- Uninfected
And a total of 27,558 images.

### Acknowledgements
This Dataset is taken from the official NIH Website: https://ceb.nlm.nih.gov/repositories/malaria-datasets/
And uploaded here, so anybody trying to start working with this dataset can get started immediately, as to download the
dataset from NIH website is quite slow.
Photo by Егор Камелев on Unsplash
https://unsplash.com/@ekamelev

### Inspiration
Save humans by detecting and deploying Image Cells that contain Malaria or not!

# Malaria-Cell-image-classification-CNN

Malaria is caused by Plasmodium parasites. The parasites are spread to people through the bites of infected female Anopheles mosquitoes, called "malaria vectors." There are 5 parasite species that cause malaria in humans, and 2 of these species – P. falciparum and P. vivax – pose the greatest threat.  

source : https://www.who.int/news-room/fact-sheets/detail/malaria  

In this kernel, I have shown the stepwise process of creating Convolution Neural Network Model using keras library for classifying images of Normal and Malaria parasite infected human blood sample.

## EDA -> Checking sample images
In this step we will check the actual sample images of both infected and normal blood sample

**Parasite Infected Blood Sample Images**

![image](https://user-images.githubusercontent.com/64974149/135708117-8944630c-885e-4fcc-897b-7a9438669bb8.png)

**Observation:**
As we can see from above images that in infected sample there is small dot in almost every image which may be the critical mark while recognizing the imfected image. the model has to learn this pattern during training stage.

**Normal Blood Sample Images (Un-infected)**
![image](https://user-images.githubusercontent.com/64974149/135708175-08080b41-fc8c-4bd6-ac1c-5f30eb0a71b7.png)

**Observation:**
As we can see normal images are clear with no mark to show.

## Data Preprocessing 
We're doing some Labeling & Resizing of images, Normalization Data and Label Encoding

## Model Building: CNN
![image](https://user-images.githubusercontent.com/64974149/135708213-d9d3a148-cd59-4e3e-9583-9ff0774407a4.png)
- Compiling the model
- Setting Callbacks
- Model Fitting

## Plot loss, Accuracy, Classification report and Confusion Matrix

**Confusion Matrix:**

![image](https://user-images.githubusercontent.com/64974149/135708245-cbedee00-75eb-4418-aea0-7898b8f223bb.png)

**History of Model:**

![image](https://user-images.githubusercontent.com/64974149/135708249-6602aa08-a993-4214-b950-09e573581271.png)

**classification Report:**

![image](https://user-images.githubusercontent.com/64974149/135708287-ac665759-170c-43c3-a4ac-a88d3e250479.png)

## Plotting ROC AUC Curve
In this step we will first compute Are Under Curve (AUC) based on which we plot ROC curve. The result of Computing Area Under Curve (AUC) is : **0.9562569934969698**
![image](https://user-images.githubusercontent.com/64974149/135708313-054af22f-7e01-4382-9efc-7a5586fcef79.png)

## Plotting Sample Prediction (Groundtruth vs Predicted)
In this step we will test our model by plotting 12 random prediction in which ground truth is in brackets and predicted value is outside the bracket if both match then the color will be blue whereas incorrect or misclassified instances will show in orange color.
![image](https://user-images.githubusercontent.com/64974149/135708323-c20fd888-f413-45ef-b850-18ce46a353eb.png)

## Conclusion & Future Improvements
- As we have seen our model is giving approx 97% recall nd auc of around 96.36 which is good overall.
- Further, we can also do data augmentation to increase the dataset and improve the accuracy
- The only misclassified instance shown in our random sample plotting has seems to have a small mark but in real its not which our - Model errorneously understand as a mark and therefore predicted as infected sample.

