
## this is my note from advanced Computer Vision with TensorFlow

### Object Detection and Sliding Windows

examples:
face recog and verification

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









