# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

#### DEVELOPED BY : PRAGAHARSHITHA NC
#### Register number: 212222110033
```python
# Load the necessary packages
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('peacock.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('peacock.jpg',0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image
![out 1 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/895d94c4-805b-4fd6-9023-0b075612af84)


### Global Thresholding
![out 1 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/0e5d79ee-3fbb-4428-bcae-511e99c2c895)

![out 2 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/d12aa221-a168-46f1-8cd2-e77e289863f0)

![out 3 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/b960ce9b-c31f-4de1-890c-a1732a9f5dbe)

![out 4 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/e76fa09d-50cb-4028-8e2b-4a6ea2c8efca)

![out 5 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/dae5b623-e5b6-4012-90cd-e13e0fed7873)


### Adaptive Thresholding
![out 6 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/cdb05e1f-4363-4dcf-aed5-3b800e056593)

![out 7 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/82ff10de-8c7a-4191-b086-dff6d070b155)



### Optimum Global Thesholding using Otsu's Method

![out 8 8](https://github.com/Sakthimurugavel/Thresholdingg/assets/118707246/08c3c77c-b7d2-42e6-8c8a-9378d4adf7ae)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
