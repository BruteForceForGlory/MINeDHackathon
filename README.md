## MINeDHackathon
# Background removal from diamond images using Image Processing or ML techniques

# Dataset:
The dataset for the problem has been provided by D360 Tech. In the dataset, there are 14 folders - one for each SHAPE-label of a diamond.
There are a total of 9135 uniquely numbered diamonds each having 256 images captured at different angles.

# Datasets folder link:

https://drive.google.com/drive/folders/1FPiUhNzWmJMNXkafV02WDtCufWu83KUV?usp=sharing


It contains 3 .rar files:

      - Shape_1d_256i -> count  = 1 diamond of each SHAPE label
      
      - Shape_5d_256i -> count = {'PS': 5, 'RA': 5, 'PR': 5, 'EM': 5, 'BR': 5, 'MQ': 5, 'SEM': 2, 'OV': 5, 'HS': 5, 'CMB': 5, 'PE': 3, 'RD': 5, 'TRI': 1, 'AS': 5} 
      
      - Shape_10d_256i -> count = {'PS': 10, 'RA': 10, 'PR': 10, 'EM': 10, 'BR': 10, 'MQ': 10, 'SEM': 2, 'OV': 10, 'HS': 10, 'CMB': 10, 'PE': 3, 'RD': 10, 'TRI': 1, 'AS': 10}

# Image Processing:

Since images in the raw datasets do not have the output suitable to train the model first of all the required images have been created from the raw dataset using image processing techniques like power-law transformations, image smoothening, etc. using matlab. 

The code for the same has been provided in the MaskCreatoe.m file.

The primary task here is accomplished but we always want a model to obtain faster results:).


# Results after image processing:
![image](https://user-images.githubusercontent.com/72211869/156837029-c491a9a6-1a7b-4597-81ef-d440652e5524.png)


# Model:

The model used to generate desired output images from input images is the Pix2Pix GAN for image translation with a reference to “[Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/abs/1611.07004)” and [presented at CVPR in 2017](https://ieeexplore.ieee.org/abstract/document/8100115), presented by [Philip Isola](http://web.mit.edu/phillipi/).

Reference: https://machinelearningmastery.com/how-to-develop-a-pix2pix-gan-for-image-to-image-translation

The Pix2Pix GAN has been demonstrated on a range of image-to-image translation tasks such as converting maps to satellite photographs, black and white photographs to color, and sketches of products to product photographs.

![image](https://user-images.githubusercontent.com/72211869/156833884-449959bd-85e6-4394-a2ec-19db81daeed6.png)

# Training:
The model presented here has been trained for only the type 'AS' diamond inputs from the Shape_5d_256i folder which includes about 1280 source images for 30 epochs.

The loss function used is binary_crossentropy and mae.

# Dependencies

The code requires libraries such as :
- numpy
- tensorflow
- keras
- matplotlib
- python 3
