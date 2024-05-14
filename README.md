# THRESHOLDING
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
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

## Program:
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```
image = cv2.imread("nature.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("nature.png",0)
```

### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
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

## Output:
### Original Image
<img width="334" alt="325661121-4c51ada8-8fc2-428c-92b7-f4cfaae0e6ee" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/e03c6f56-1f94-425c-ae89-d872430bf8b4">

### Global Thresholding
<img width="335" alt="325661375-fb7955b8-f171-4af1-999a-a97253d4d839" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/fb92aa37-c0b6-40f6-a474-cf837e475e60">
<img width="339" alt="325661540-3c7081b9-c30e-4a8d-8388-b5c7ef1819e5" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/fafba743-9c43-455a-9f1c-7b36b950908a">
<img width="335" alt="325661685-623a6eaf-6d21-44d4-8b99-d81cbacae581" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/9511c709-297e-4f29-b0c1-e002efb52635">

### Adaptive Thresholding
<img width="338" alt="325661948-ef26f0b4-23a9-4751-82f3-7367e04fd826" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/cc099dbe-4a9a-4033-88a1-d5afb2d5d579">

### Optimum Global Thesholding using Otsu's Method
<img width="331" alt="325661811-6b1b4c22-ea5f-42b7-a3f5-c0b55a688677" src="https://github.com/Priya-Loganathan/Thresholdingg/assets/121166075/d465fa13-8135-4af5-a0a5-1f8d344ca7b2">

## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
