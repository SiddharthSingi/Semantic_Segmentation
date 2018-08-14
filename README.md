# Semantic_Segmentation
Using the KITTI Dataset to perform pixelwise classification of road images.

Object detection in images has been continously advancing with more efficient and accurate research papers being released every year. One of the most famous types of object detection is semantic segmentation, which involves alligning every pixel with a particuar class of object. To explain this further look at the example below: every pixel in the ouput is given different color depending on whether that pixel is a road, vehicle, traffic sign, tree, human, etc. This pixel wise classification of images into different classes is known as semantic segmentation.

![qualitative-evaluation-on-cityscapes-input-image-on-the-right-and-output-labels-from](https://user-images.githubusercontent.com/26694585/44083549-e5cbc366-9fd1-11e8-8994-524a282a06d0.png)


### Comparision with conventional object detection
Conventional Object Detection involves creating a box around the desired object as shown in the example below:

<img src="https://user-images.githubusercontent.com/26694585/44083834-b3be315a-9fd2-11e8-9e1d-8b628a6e6037.jpg" width="400"/>

1) If the goal of the classification is to identify the drivable portion of the road, creating a box around it would not make any sense as it will not be able to incorporate the actual part of the image where the drivable road is present.

2) Sometimes normal object detection may get too crowded and incomfortable to be read a shown here: 

<img src="https://user-images.githubusercontent.com/26694585/44084247-d29c8cd8-9fd3-11e8-9ad6-d447089f5d67.png" width="400"/>

3) Semantic Segmentation has the power to obtain more accurate dimensions of the identified object which makes it easier to persorm any further computer vision techniques on it, for example: SnapChat Filters.


### How does it work
As compared to normal convolutions in deep learning models, semantic segmentation also makes use of:
* 1x1 Convolutions
* Transposed Convolutions
* Transfer Learning

#### 1x1 Convolutions
These are basically normal convolutions with size = (1,1), and strides=(1,1). Their operation is not very different as compared to fully dense layers, and they may seem rather redundant, however they have many benefits:
  * They are very computationally cheap to use.
  * They may be used for any size of images, as compared to dense layers which require a certain fixed input size to work.
  * 1x1 Convolutions are the simplest method for dimensionality reduction.
  
#### Transposed Convolutions
