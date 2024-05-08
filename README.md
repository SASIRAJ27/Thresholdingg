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
```
Name: sasirajkumar T j
Reg no:212222230137
```

# Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```python
image = cv2.imread("nature.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("nature.png",0)
```

# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results

```python
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
![Screenshot 2024-05-08 215144](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/47d03821-ce35-4b15-a309-344c6de3cba7)



### Global Thresholding
![Screenshot 2024-05-08 215150](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/f0bfd936-f29b-425e-9bae-e708da920dad)
![Screenshot 2024-05-08 215157](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/47aaa12e-78dc-4168-9163-8abe1b9ecd08)


![Screenshot 2024-05-08 215206](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/e8b049ef-c1ed-440e-9d27-1f4c57da6a37)

![Screenshot 2024-05-08 215219](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/31f5a6b7-83db-4b5c-ab79-3cf828079f8f)

![Screenshot 2024-05-08 215212](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/85d98740-6bde-4037-aea6-3eb561ab47f7)

### Adaptive Thresholding
![Screenshot 2024-05-08 215236](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/ac570b00-3b44-4787-9dba-778b53c83ed9)

![Screenshot 2024-05-08 215243](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/118428c9-10d1-4124-811c-abb91ca7ed34)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-05-08 215226](https://github.com/SASIRAJ27/Thresholdingg/assets/113497176/1c8989b6-eb93-4b84-94bd-a76007de238c)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
