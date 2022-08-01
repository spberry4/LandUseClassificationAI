# LandUseClassificationUsingCNN

Final Project at SNHU for a Masters in Data Analytics

Data retrieved from AVIRIS and can be located here:

http://www.ehu.eus/ccwintco/uploads/a/a3/Salinas_corrected.mat 
http://www.ehu.eus/ccwintco/uploads/f/fa/Salinas_gt.mat

There are 16 land classes that are being used as follows:

Brocoli_green_weeds_1
Brocoli_green_weeds_2
Fallow
Fallow_rough_plow
Fallow_smooth
Stubble
Celery
Grapes_untrained
Soil_vinyard_develop
Corn_senesced_green_weeds
Lettuce_romaine_4wk
Lettuce_romaine_5wk
Lettuce_romaine_6wk
Lettuce_romaine_7wk
Vinyard_untrained
Vinyard_vertical_trellis

Project Name: Land Usage Classification AI

Project Description: Land Usage classification is extremely important in our ever evolving world to keep track on how people/companies are using land and to monitor global land usage for science. The data comes from the JPL project AVIRIS which consists of 224 bands of hyperspectral imagery. This type of data can be used to determine many different things including identifying vegetation, determining agricultural uses, snow and ice coverage, and ground atmospheric data. This type of data is only increasing in volume therefore automatic classification can save time and be more efficient. The use of a Convolutional Neural Net has become commonplace when classifying images and can be used in this case to accurately identify the different land classes.

Model Baselines: The model was trained on 38,303 observations and achieved a 91% accuracy rating. The model was then validated on 5,000 observations and achieved approximately 92% accuracy with the validation data. The closeness of these two accuracy ratings indicated that the model is not overfitting and will generalize well with any new data that is read into the model.

Model Performance: On 10,826 observations the testing data achieved a 92% accuracy. While accuracy tells us about the overall accuracy of the model we can delve deeper into the accuracy using a confusion matrix. See below for the confusion matrix:

![confusion matrix](https://user-images.githubusercontent.com/95090904/182252064-8eb10d6a-dc78-40fb-94bf-4ea85af430fe.png)

We can clearly see that the model does a great job at classifying almost all the different classes except for 15 and 8 which are grapes and a vineyard. These two are very similar to each other so it's no surprise that this is happening. Further training would be needed to correct this but an accuracy of 92% is already quite high therefore this may not be needed.
