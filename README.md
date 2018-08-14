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
* Skipped Connections
* Transfer Learning

#### 1x1 Convolutions
These are basically normal convolutions with size = (1,1), and strides=(1,1). Their operation is not very different as compared to fully dense layers, and they may seem rather redundant, however they have many benefits:
  * They are very computationally cheap to use.
  * They may be used for any size of images, as compared to dense layers which require a certain fixed input size to work.
  * 1x1 Convolutions are the simplest method for dimensionality reduction.
  
#### Transposed Convolutions
Transposed Convolutions must be considered as nothing more than the opposite of normal convolutions. They upscale the images to a larger size, so that the output images may be formed from upsampling dense layers into full sized images.

#### Skipped Connections
Skipped Connections are used to reuse any information lost in the downsampling process of the network.
![skipped](https://user-images.githubusercontent.com/26694585/44086229-8400944c-9fd9-11e8-823c-34a51c0e19da.png)
In the above image the output of Predict2 and DeConv1 are added to give the result of DeConv2, this method regains information lost from the convolutions to give more accurate results. The downsampling part is called the encoder and the upsampling part is called the decoder

#### Transfer Learning
Lastly in this project I have used Transfer Learning. This uses pretrained weights from the VGG model. I have initialized the weights in the encoder part to those of the already trained vgg model. This way I save time in training by only having to train the decoder weights of the model.

### My outputs:
Due to lack of computing power I have not used the CityScapes dataset but have rather used the KITTI dataset. This only consists of one single class of the image that is the drivable partion of the road. Here are a few examples of my test outputs:

![um_000017](https://user-images.githubusercontent.com/26694585/44086996-0390089e-9fdc-11e8-879d-a7a4e33ae722.png)
![um_000087](https://user-images.githubusercontent.com/26694585/44086999-0427b4aa-9fdc-11e8-93be-1d73df0f08cb.png)
![umm_000010](https://user-images.githubusercontent.com/26694585/44087003-0497599a-9fdc-11e8-85e6-e8f3e89fda40.png)
![uu_000084](https://user-images.githubusercontent.com/26694585/44087005-04e6f5fe-9fdc-11e8-9b6a-a23e0e301ae5.png)
![um_000010](https://user-images.githubusercontent.com/26694585/44087007-060ef292-9fdc-11e8-9fca-81201a139c7a.png)


