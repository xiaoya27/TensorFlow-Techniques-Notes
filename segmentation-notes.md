#### FCN's encoder decoder structure explain:

Conv+Downsampling ----> a loe res tensor with high-level info ( a lot channels ) 

------> conv + upsampling -----> increase res & decrease channel 

![img](https://divamgupta.com/assets/images/posts/imgseg/image5.png?style=centerme)


To deal with loss of low level info ----> skip connection(Intermediate outputs of the encoder are added/concatenated with the inputs to the intermediate layers of the decoder at appropriate positions.)


![img](https://divamgupta.com/assets/images/posts/imgseg/image6.png?style=centerme)

Transfer learning--> re-use the convolution layers of the pre-trained models in the encoder layers of the segmentation model.

Using Resnet or VGG pre-trained on ImageNet dataset is a popular choice.

#### ! Caution: 

For the segmentation maps, do not use the jpg format as jpg is lossy and the pixel values might change. Use bmp or png format instead. 


#### Data augmentation

We can change the color properties like hue, saturation, brightness, etc of the input images. We can also apply transformations such as rotation, scale, and flipping.

#### Choosing the model

The model architecture shall be chosen properly depending on the use case. There are several things which should be taken into account:

1. The number of training images
2. Size of the images
3. The domain of the images

A standard model such as ResNet, VGG or MobileNet is chosen for the base network usually.


#### Choosing Segementation Architecture

[ref](https://divamgupta.com/image-segmentation/2019/06/06/deep-learning-semantic-segmentation-keras.html)

1. For images containing indoor and outdoor scenes, PSPNet is preferred, as the objects are often present in different sizes. 
Here the model input size should be fairly large, something around 500x500.

2. For the images in the medical domain, UNet is the popular choice. Due to the skip connections, UNet does not 
miss out the tiny details. UNet could also be useful for indoor/outdoor scenes with small size objects.

3. For simple datasets, with large size and a small number of objects, UNet and PSPNet could be an overkill. 
Here simple models such as FCN or Segnet could be sufficient.

It is best advised to experiment with multiple segmentation models with different model input sizes.




For many applications, choosing a model pre-trained on ImageNet is the best choice.

