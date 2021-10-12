# Segmentation_project

- Tested accuracy/performance/inference time of various backbones and models on segmentation task
- PSPNet+Inceptionv3 chosen to be the best model for my particular task (best model vary depending on the task)
- Applied, trained, and applied inference on the dataset.
- Image preprocessing done with **opencv**
- Modelling (Semantic segmentation) done with **segmentation_models** library
- First applied morphological operations on the model output, then applied contour detection, blob detection
- Finally, task-specific algorithms to provide solution.

## 2021.10.12
- training and inference codes added for hole detection.


### Model selection. (UNET)

- Training and Inference were done on *[128 x 128 x 3]* image (Batch = 64)
    - Training and Inference time likely to increase when using larger images.
- Both *resnet34* and *resnet101* were trained up to 20 epochs.
    - May need more epochs for *resnet101* to converge

| Model   | Resnet34   | Resnet101  |
| ------------- |  :-------------: | :-------------: | 
| Training Time  | 6mins    | 20mins  |
| Inference Time    | **120ms** | 450ms  |
| Accuracy  | 93.7% | 94%  |


#### Resnet 34 Samples
![resnet34_unet](https://user-images.githubusercontent.com/53849669/133183544-117019e6-5f09-449c-87d4-3ecca423c146.png)
![resnet34_unet2](https://user-images.githubusercontent.com/53849669/133184006-bf0f7450-5cbe-432e-80d3-9b7bcb4d2125.png)

#### Resnet 101 Samples
![resnet101_unet](https://user-images.githubusercontent.com/53849669/133184010-f01f3a3a-ee9c-4500-8f48-bf10e42729f2.png)
![resnet101_unet2](https://user-images.githubusercontent.com/53849669/133184013-e944815e-3f70-43c2-a45d-f39adabec255.png)


### Model selection 2. PSPNet (2017) + Inceptionv3

- Image resized to *[144,144,3]* - 
    - (PSPNet only supports input (H,W), divisible by 48

| Model  | Inceptionv3 |
| ------------- | :-------------: | 
| Training Time   | 5mins  |
| Inference Time  | **14ms**  |
| Accuracy  | 94.5%  |

![incep_psp](https://user-images.githubusercontent.com/53849669/133200250-c59cbecf-3897-48c8-aeef-e69b3670aa7e.png)
![incep_psp2](https://user-images.githubusercontent.com/53849669/133200257-383b81fe-d2b6-4534-8683-6e240bdcaad5.png)

### Blob detection with OpenCV to count number of objects in the image

- After choosing appropriate sementic segmentation model to work with, we can apply it directly to the custom image dataset.
- After Training, you may run the inference code to test on other images on test dataset.
- From this output, we further apply Blob detection code from OpenCV to correctly count the number of objects (blobs).


## Conclusion

- Tested multiple combinations of backbones and models on sementic segmentation, and seemed that **PSPNet+Inceptionv3** works the best (at least) for the two datasets that I have worked with.
