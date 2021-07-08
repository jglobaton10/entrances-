# Object Detection in densely populated retail images 

## Objectives
* Recognize the amount of products of each type in densely populated retail images 
    1. Setting up an object detection model able  to recognize products on densely pupolated shelf images.
    2. Develop a clustering model that  segments the detected products into categories based on their similarity  
    
## Data 
The data used for this project is SKU-110K a large collection of densely populated images of shelfs. The dataset weights 49,9 GBs and is conformed by 11,762 images with more than 1.7 million annotated bounding boxes. The data is splitted in train and test  with  a proportion of 80% for the first and 20% for the latest.  The images are in format **.jpg** and the annotations are in a **.csv** file ([Link to the dataset](https://drive.google.com/file/d/1iq93lCdhaPUN0fWbLieMtzfB1850pKwd/edit)).
### Sample images 
![image](https://user-images.githubusercontent.com/47225250/124989887-a2797e80-e00d-11eb-92f0-6bef6c453d12.png)

## Design and development
Down below it can be observed the propused pipeline.


![image](https://user-images.githubusercontent.com/47225250/124990051-d9e82b00-e00d-11eb-99fa-fb3fc962e905.png)
The pipeline is composed mainly of three models:
1. Object detection model: This model will be in charge of outputing the bounding boxes that identify each object in an image. For this part of the project it was used the API of object detection of tensorflow and some specific implementations of some object detectation models. 
2. CNN for feature extraction: This is a convolutional neural network without the classification. This network will be used to extract features from the images and generate a compat representation of the images and for this will be used  VGG16. 
3. Clustering model: This model will group the objects based on their similarity. The model that will be use for this is k-means.  

The first model will be evaluated with the metric mAP, while the last one will be evaluated with silhouette score. 
## Results
At this moment the best result for the first part was achieve by the model CenterNet HourGlass104 Keypoints 1024x1024 which has a mAP of 0.35.
