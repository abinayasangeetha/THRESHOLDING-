# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("thres.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("thres.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![Screenshot 2024-04-09 103229](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/be41e794-f8f9-4d6d-a44d-bb4f46175e4c)


### Global Thresholding
![Screenshot 2024-04-09 103253](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/521646b8-abb1-4af7-95bf-1304b1917f4f)
![Screenshot 2024-04-09 103305](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/2a517047-1448-4ed2-9b5a-c87c38eea65f)
![Screenshot 2024-04-09 103319](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/6ccd3470-5077-428d-a5ff-b4853138d40d)
![Screenshot 2024-04-09 103332](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/aa0a7667-a2f6-453a-b3dc-d6790c39131d)
![Screenshot 2024-04-09 103357](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/f44a0418-2293-4a41-9f3d-3155ab458181)



### Adaptive Thresholding
![Screenshot 2024-04-09 103424](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/90ebeef3-7f67-482d-9e76-caa18af509de)
![Screenshot 2024-04-09 103438](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/e880fbd6-b0f9-4002-9d34-dde4a138fc8e)



### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-09 103410](https://github.com/abinayasangeetha/THRESHOLDING-/assets/119393675/de60d273-d26a-4581-8476-8dcdb0f65ac2)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
