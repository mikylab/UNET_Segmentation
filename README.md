# UNET_Segmentation
A UNET model trained to segment nuclei H&amp;E and multi-photon images using 3 color channels. The UNET model was derived from [zhixuhao's UNET](https://github.com/zhixuhao/unet). His model only allowed segmentations of single channel images. To segment H&E images in color, I adjusted the model. Additonally, for training I created a custom generator to randomly transform color images into grayscale in three colors. This allowed the model to train on images that were randomly selected to be in color or in grayscale. Additionally, I added elastic transformations to improve the model's generalizability from H&E images to multiphoton images. 

This model was trained on H&E images with the hope of being able to perform on multi-photon images as well. Currently, most models can only perform on one domain or the other. The H&E images had larger nuclei and better quality than the multiphoton images used. The model was able to perform well on the H&E images, but produced lots of false positives of negatives in the nuclei images. However, considering the model was not trained on multiphoton images only H&E images the results were encouraging. 

Image Samples: 

Dice Coefficient: 0.85853463

![image](https://user-images.githubusercontent.com/43506570/153546478-8497b17a-0323-4b11-ba36-aa76a439047b.png)

Dice Coefficient: 0.89478624


![image](https://user-images.githubusercontent.com/43506570/153546545-44264a13-fe2c-48c6-8e2c-7a086f82e6d4.png)


---
Resources used:
Tutorial to randomly split the data into training, validation, and testing segments.
https://towardsdatascience.com/a-keras-pipeline-for-image-segmentation-part-1-6515a421157d

H&E Image Dataset:
https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=64685083 
