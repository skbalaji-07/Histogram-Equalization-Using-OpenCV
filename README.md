# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim:

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---


## Developed By:
**Name:** sk balaji
**Register No:** 2305003001

## Program:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('parrot.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
```python
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
##  Output:

### ORIGINAL IMAGE:
<img width="786" height="492" alt="image" src="https://github.com/user-attachments/assets/1e5a8475-714f-4751-a689-8cdd99baad1e" />

<img width="839" height="545" alt="image" src="https://github.com/user-attachments/assets/826e4b36-a591-4f65-8130-21d2cec76059" />


### Equalised Histogram:

<img width="873" height="548" alt="image" src="https://github.com/user-attachments/assets/4126ae0f-55dd-4658-9ba2-20dec279d6dc" />

<img width="962" height="511" alt="image" src="https://github.com/user-attachments/assets/b910bbe6-d4e3-4887-b2c0-04fa2a8ae9af" />

### Histogram of Grayscale Image and any channel of Color Image:
<img width="787" height="272" alt="image" src="https://github.com/user-attachments/assets/1b97f53a-e1da-44c2-b285-6c897b340f50" />

### Histogram Equalization of Grayscale Image:
<img width="1106" height="808" alt="image" src="https://github.com/user-attachments/assets/ce8724cd-9545-4578-8019-fe4337c14e7b" />


## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
