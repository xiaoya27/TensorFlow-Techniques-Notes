# OrniSegmentation

This is implementation of resnet Unet for binary semantic segmentation.  


## How to train

First, 

```
$ python png_to_json_annot.py
```

Modify the following variables if needed:

```
name
data_path
raw_image_dir
anno_seg_json_dir
train_prob
val_prob
```
```
$ python scripts/initialise_dataset_homemap.py
```

In order to train model, you have only to setup config file.  
For example, modify config file /config_files/dgx_config_generic_gan.json on the following variables if needed.

```
n_gpu
batch_size
data_dir
dataframe_name
input_folder_name
annotation_folder_name
epochs
save_dir

```


or if your image is too large , you can use scripts/tile_and_initialize_dataset.py for split your image 

Modify the following variables if needed:

```
$ python scripts/tile_and_initialize_dataset-homemap.py
```
or 

```
$ python scripts/tile_and_initialize_dataset-homemap.py
```

Then you can train this model by:

```
$ CUDA_VISIBLE_DEVICES=1 python train.py --config config_files/dgx_config_generic_gan.json --gpu
```

To test the model: 


Modify the following variables if needed:



```
 $ CUDA_VISIBLE_DEVICES=1 python test.py --config config_files/dgx_config_generic_gan.json --resume checkpoint-epoch1.pth --gpu
 
```

## Directory tree
```
.
├── config
├── data
│   ├── cityscapes
│   │   ├── gtFine
│   │   └── leftImg8bit
│   └── pascal_voc_2012
│        └── VOCdevkit
│            └── VOC2012
│                ├── JPEGImages
│                ├── SegmentationClass
│                └── SegmentationClassAug
├── logs
├── model
└── src
    ├── dataset
    ├── logger
    ├── losses
    │   ├── binary
    │   └── multi
    ├── models
    └── utils
```

## Environments
- OS: Ubuntu18.04
- python: 3.7.9
- pytorch: 1.3.1
- pretrainedmodels: 0.7.4 


