# Segmentation_project

##### Testing inference time of various backbones and models on segmentation task


All training and Inference was done on [128 x 128 x 3] image

## Unet

| Model  | Resnet34 (no gpu)  | Resnet34 (with gpu)  | Resnet101  |
| ------------- | :-------------: | :-------------: | :-------------: | 
| Training Time |  na | 6mins    | 20mins  |
| Inference Time  | 82ms  | **2ms** | 7.5ms  |
| Accuracy  | na  | 93.7% | 94%  |



## PSPNet
