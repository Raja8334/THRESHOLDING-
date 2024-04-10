# EX-08 THRESHOLDING
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
```
DEVELOPED BY: Raja R
REGISTER NO: 212222100041
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("Demon.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("Demon.jpg",0)
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
![Screenshot 2024-04-10 105934](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/bd8ad8d7-d288-4f14-a767-949b52e238c0)

### Global Thresholding
![Screenshot 2024-04-10 105945](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/ccd69338-4e8b-4594-adc8-a008ff1995c8)




![Screenshot 2024-04-10 110023](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/ce729ced-6aa9-4ed6-91dc-94b85170ee7e)

### Adaptive Thresholding
![Screenshot 2024-04-10 110032](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/933af7fd-0bc7-4299-af6b-a6b611021819)

![Screenshot 2024-04-10 110041](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/dacf0054-2166-4105-a51a-ca7b25381b7e)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110055](https://github.com/Raja8334/THRESHOLDING-/assets/120719634/cbaf70e2-587b-4456-9e1a-90aea05d25bc)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
