# Segmentation_project

##### Testing inference time of various backbones and models on segmentation task


- Training and Inference were done on *[128 x 128 x 3]* image (Batch = 64)
    - Training and Inference time likely to increase when using larger images.

## Model 1. Unet
- Both *resnet34* and *resnet101* were trained up to 20 epochs.
    - May need more epochs for *resnet101* to converge

| Model  | Resnet34 (no gpu)  | Resnet34 (with gpu)  | Resnet101  |
| ------------- | :-------------: | :-------------: | :-------------: | 
| Training Time |  na | 6mins    | 20mins  |
| Inference Time  | 82ms  | **2ms** | 7.5ms  |
| Accuracy  | na  | 93.7% | 94%  |


#### Resnet 34 Samples
![resnet34_unet](https://user-images.githubusercontent.com/53849669/133183544-117019e6-5f09-449c-87d4-3ecca423c146.png)
![resnet34_unet2](https://user-images.githubusercontent.com/53849669/133184006-bf0f7450-5cbe-432e-80d3-9b7bcb4d2125.png)

#### Resnet 101 Samples
![resnet101_unet](https://user-images.githubusercontent.com/53849669/133184010-f01f3a3a-ee9c-4500-8f48-bf10e42729f2.png)
![resnet101_unet2](https://user-images.githubusercontent.com/53849669/133184013-e944815e-3f70-43c2-a45d-f39adabec255.png)


## Model 2. PSPNet + Inceptionv3

- Image resized to *[144,144,3]* - 
    - (PSPNet only supports input (H,W), divisible by 48

| Model  | Inceptionv3 |
| ------------- | :-------------: | 
| Training Time   | 5mins  |
| Inference Time  | **1ms**  |
| Accuracy  | 94.5%  |

![incep_psp](https://user-images.githubusercontent.com/53849669/133200250-c59cbecf-3897-48c8-aeef-e69b3670aa7e.png)
![incep_psp2](https://user-images.githubusercontent.com/53849669/133200257-383b81fe-d2b6-4534-8683-6e240bdcaad5.png)
