
# this is my note from advanced Computer Vision with TensorFlow
# course 2
### Object Detection and Sliding Windows methodologies


examples:
1. face recog and verification
2. vehicle counting
3. etc.

methodologies: 
1. sliding window: 
* multi box of diff size ; ( how to combine multiple prediction: Highest IOU , aka Non-maximum suppresion) 
* rescaling image (advantage-- quick with less memory)  ( calcuate union of various scale)
2. selective search 
* make num of proposals of region of interest


R-CNN(2013) region with cnn features

steps: 
1. input image 
2. extract region proposals
3. compute CNN features( with alexnet ) 
4. SVM- classification; regression- bounding box

Fast R-CNN (2015)

Steps: 
1. input image + region ( with conv net ) 

Faster R-CNN ()

RPN ( region proposal network) ---fast way of finding AOI

### Model training 
steps

1. get faster r-cnn model from TensorflowHub
* copy the url , saved as string to 

    `module_handle = "https://tfhub.dev/tensorflow/faster_rcnn/inception_resnet_v2_640x640/1" `


2. find a random image link , download and preprocess, stored in a tensor 
``
``
`converted_img`
the model is desgined to take multi images 
`ccc`
The result would be 
possibities


## course 3 Image segmentation
category
* sementic 
* instance

basic architecture

Encoder( feature extraction) --downsampled feature map--> Decoder( up sample feature map, generate pixel-wise label map )  ---> n*n*classes


Popular Architectures

* Fully-convnet(FCN) 
** Decoder part : FCN-32s, FCN-16s,FCN-8s ( stride size, smaller the better accuracy)

** popular encoder : VGG_16, Res50, Mobilenet

* SegNet ( encoder and decoder is symmetric) 

* Unet ( symmetric structure too) 
* Mask R-CNN

















