## Cassava Leaf Disease Classification

**Overview:** 
Developed a method utilising [EfficientNet](https://arxiv.org/abs/1905.11946) model to accurately classify images of Cassava plants to distinguish between healthy and diseased crops. 
<br><br>
Link to the TensorFlow implementation on [GitHub](https://github.com/leomuckley/cassava-leaf-disease-classification).
<br><br>
### 1. Problem

The Cassava leaf disease classification competition presents 21,367 labeled images, where the majority of the images were crowdsourced from farmers. These images were subsequently annotated by experts at the National Crops Resources Research Institute (NaCRRI) in collaboration with the AI lab at Makerere University, Kampala. As an added challenge, effective solutions for farmers must perform well under significant constraints, since African farmers may only have access to mobile-quality cameras with low-bandwidth. Therefore a successful method will allow farmers to be able to quickly identify diseased plants, potentially saving their crops before they inflict irreparable damage.

The goal of this competition is to classify each cassava image into four disease categories or a fifth category indicating a healthy leaf. The following image contains examples of the various diseased/healthy plants:
<img src="images/cassava.png?raw=true"/>


### 2. Modelling

Before training the model, we establish some data augmentation techniques to be utilised. The specific augmentation techniques are carefully chosen so the image adds too much noise or distorts the image beyond recognition. Each of the following techniques are randomly selected within the pre-defined limits:
* Rotation range; rotate the input image within 45 degrees
* Width shift range; specifies the upper bound of the fraction of the total width by which the image is to be randomly shifted, either towards the left or right
* Height shift range; specifies the upper bound of the fraction of the total height by which the image is to be randomly shifted, either up or down
* Shear range; distorted along an axis to represent views from different angles.
* Horizontal flip; flip the image horizontally
* Vertical flip; flip the image vertically

The model chosen was an adaptation of an [EfficientNet](https://arxiv.org/abs/1905.11946). A pre-trained variant of the available EfficientNet models was used, namely the B4 variant using *image-net* weights. The image size utilised is *380x380* as this is the recommended size for the B4 variant . Subsequent layers were then appended to the (frozen) pre-trained layers for the model to learn additional features specific to the leaf disease problem.



### 3. Results
The resulting model achieved an an accuracy of 88.5% on a test set.
