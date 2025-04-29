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

## DEVELOPED  BY : SARISH VARSHAN V
## REG NO : 212223230196
## Program


```python



# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread(r"C:\Users\admin\Downloads\download.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread(r"C:\Users\admin\Downloads\download.jpeg",0)

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
![Screenshot 2025-04-29 085444](https://github.com/user-attachments/assets/233633c4-c412-4562-b8cf-8cf6a0d0a070)



### Global Thresholding

![Screenshot 2025-04-29 090621](https://github.com/user-attachments/assets/f8467685-186b-478d-a006-0354c559b3bf)

![Screenshot 2025-04-29 085654](https://github.com/user-attachments/assets/0aae90ec-73a0-439d-ba27-b5d2411ff7c6)

![Screenshot 2025-04-29 085819](https://github.com/user-attachments/assets/9984ae49-21d1-4179-b55b-a570864f7daf)

![Screenshot 2025-04-29 085906](https://github.com/user-attachments/assets/d7add91a-e0c7-47f8-908f-547f8077c92e)

![Screenshot 2025-04-29 085951](https://github.com/user-attachments/assets/25efb983-af0b-48a1-82e0-9e869629f135)




### Adaptive Thresholding

![Screenshot 2025-04-29 090059](https://github.com/user-attachments/assets/c1f90fa3-c916-4f7d-bdd1-73e4dc758265)

![Screenshot 2025-04-29 085555](https://github.com/user-attachments/assets/c68bc0db-e74c-4530-a110-ea16d4903606)




### Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-04-29 090300](https://github.com/user-attachments/assets/a1418ef1-5114-4f4c-994f-3d5d00bba67a)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
