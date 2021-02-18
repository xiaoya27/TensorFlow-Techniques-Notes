# OrniSegmentation
This repository implements resnet Unet for semantic segmentation.  


## How to train
In order to train model, you have only to setup config file.  
For example, write config file as below and save it as config/pascal_unet_res18_scse.yaml.

```yaml
Net:
  enc_type: 'resnet18'
  dec_type: 'unet_scse'
  num_filters: 8
  pretrained: True
Data:
  dataset: 'pascal'
  target_size: (512, 512)
Train:
  max_epoch: 20
  batch_size: 2
  fp16: True
  resume: False
  pretrained_path:
Loss:
  loss_type: 'Lovasz'
  ignore_index: 255
Optimizer:
  mode: 'adam'
  base_lr: 0.001
  t_max: 10
```

Then you can train this model by:

```
$ python train.py ../config/pascal_unet_res18_scse.yaml
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
- python: 3.7.0
- pytorch: 1.0.0
- pretrainedmodels: 0.7.4
- albumentations: 0.1.8  


