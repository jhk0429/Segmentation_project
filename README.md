# Segmentation_project

##### Testing inference time of various backbones and models on segmentation task


All training and Inference was done on [128 x 128 x 3] image

## Unet

| Model  | Resnet34 + Unet (no gpu)  | Resnet34 + Unet (with gpu)  | Resnet101 + Unet  |
| ------------- | :-------------: | :-------------: | :-------------: | 
| Training Time |  na | 6mins    | 20mins  |
| Inference Time  | 82ms  | 2ms | na  |



## PSPNet
