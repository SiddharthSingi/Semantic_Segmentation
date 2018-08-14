# Semantic_Segmentation
Using the KITTI Dataset to perform pixelwise classification of road images.

Object detection in images has been continously advancing with more efficient and accurate research papers being released every year. One of the most famous types of object detection is semantic segmentation, which involves alligning every pixel with a particuar class of object. To explain this further look at the example below: every pixel in the ouput is given different color depending on whether that pixel is a road, vehicle, traffic sign, tree, human, etc. This pixel wise classification of images into different classes is known as semantic segmentation.

![qualitative-evaluation-on-cityscapes-input-image-on-the-right-and-output-labels-from](https://user-images.githubusercontent.com/26694585/44083549-e5cbc366-9fd1-11e8-8994-524a282a06d0.png)


### Comparision with conventional object detection
Conventional Object Detection involves creating a box around the desired object as shown in the example below:
![test4](https://user-images.githubusercontent.com/26694585/44083834-b3be315a-9fd2-11e8-9e1d-8b628a6e6037.jpg)

1) If the goal of the classification is to identify the drivable portion of the road, creating a box around it would not make any sense as it will not be able to incorporate the actual part of the image where the drivable road is present.

2) Sometimes normal object detection may get too crowded and incomfortable to be read a shown here: 

Solarized dark             |  Solarized Ocean
:-------------------------:|:-------------------------:
![convod](https://user-images.githubusercontent.com/26694585/44084247-d29c8cd8-9fd3-11e8-9ad6-d447089f5d67.png)  |  
![semanicod](https://user-images.githubusercontent.com/26694585/44084252-d5bb3f90-9fd3-11e8-9201-72703a3c3b2a.png)
