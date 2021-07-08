# Object detection in street view images
## Objective
Recognize electric components and other objects in street view images.
  - Manually generate bounding boxes for all the images
  - Setting up an object detection model using the tensorflow API and specific implementations of other algorithms.


## Data
The dataset has 1200 street view images which were taken in real time on a road trip. The data is splitted in train and test with 70% and 30% respectively and it has not annotations.

## Sample data

![New Picture (2)](https://user-images.githubusercontent.com/47225250/124990331-364b4a80-e00e-11eb-98eb-05faa013f961.png)

## Development 

The first step in the development of this project was to tag all the images using **labelme**. The output of this step  were individual annotation files in format **.xml**. The second step consisted on setting up the object detection models for this project were used the models YOLOv4, Keras_retinanet and  different models implemented in the object detection API of tensorflow.  

## Results 

* The YOLOv4 model only reached **19% mAP** 
* The keras_retinanet got **25% mAP**
* The results of the Object detection API are shown down below


![New Picture (4)](https://user-images.githubusercontent.com/47225250/124990386-4fec9200-e00e-11eb-997c-8d733380386c.png)

As shown in the previous graph the best model is **centered_resnet50_v2_512x512_coco17_tpu-8**.

![image](https://user-images.githubusercontent.com/47225250/124990429-5b3fbd80-e00e-11eb-9c11-66451c573151.png)
