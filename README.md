# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("s.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("s.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
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
## OUTPUT:

### Original Image and Grayscale Image
![DIP-EXP9-A](https://user-images.githubusercontent.com/75235132/169962475-3035e59e-70d3-41eb-bf67-2235bcf16d30.png)

### Global Thresholding
![DIP-EXP9-B](https://user-images.githubusercontent.com/75235132/169962524-2ab2fbed-d6f2-47d4-8e81-351b09a9bedf.png)
![DIP-EXP9-C](https://user-images.githubusercontent.com/75235132/169962538-dca62bed-3aa3-49fc-bc23-1621380ce1a2.png)
![DIP-EXP9-D](https://user-images.githubusercontent.com/75235132/169962551-754c4c03-31c3-4b1d-9ab8-8fed0fe54c7a.png)
![DIP-EXP9-E](https://user-images.githubusercontent.com/75235132/169962564-4fdf816d-a691-4f2f-8b1c-0c262aca86bf.png)
![DIP-EXP9-F](https://user-images.githubusercontent.com/75235132/169962578-e76a831e-2875-472b-9b49-55642b7f7a00.png)

### Adaptive Thresholding
![DIP-EXP9-G](https://user-images.githubusercontent.com/75235132/169962601-dd5361f8-cfc0-4519-9152-4086949a6098.png)
![DIP-EXP9-H](https://user-images.githubusercontent.com/75235132/169962614-688d92a3-571d-439b-95c2-c00ac1e6b6cf.png)

### Optimum Global Thesholding using Otsu's Method
![DIP-EXP9-I](https://user-images.githubusercontent.com/75235132/169962638-783c2061-d2da-4faf-a5d6-68a8917e67d1.png)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
