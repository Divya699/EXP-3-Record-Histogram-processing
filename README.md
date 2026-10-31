# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

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

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

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

## Program

### Developed By:
### **Name:** DIVYA PRIYA .S

### Register No: 212225240037

###  Histogram Equalization for Grayscale Images
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r'C:\Users\acer\Downloads\photo 2.jpeg')
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img = cv2.imread(r'C:\Users\acer\Downloads\photo 2.jpeg')
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
img_eq = cv2.equalizeHist(gray)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Histogram Equalization for Color Images 
```
img = cv2.imread(r'C:\Users\acer\Downloads\photo 2.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```

##  Output

### Grayscale Histogram Equalization

Original grayscale image is displayed

<img width="344" height="553" alt="image" src="https://github.com/user-attachments/assets/ffa6394e-3682-4b01-b773-6c1311fc25bb" />

Histogram of original grayscale image is plotted

<img width="786" height="563" alt="image" src="https://github.com/user-attachments/assets/c8a24d31-646f-4268-9cb3-6791c121db28" />


Enhanced image after histogram equalization is displayed

<img width="798" height="603" alt="image" src="https://github.com/user-attachments/assets/d2f145d2-54d3-47e4-96e3-0b1201cb5a51" />

Histogram of enhanced grayscale image shows improved contrast  

<img width="304" height="554" alt="image" src="https://github.com/user-attachments/assets/f1d61d76-b3c8-4fec-93b2-2a00751cb995" />

### Color Image Histogram Equalization

Original color image is displayed

<img width="285" height="537" alt="image" src="https://github.com/user-attachments/assets/ceec2909-9955-457a-a556-6a2c31f4c1cd" />
  
Histogram of B, G, R channels is plotted

<img width="763" height="561" alt="image" src="https://github.com/user-attachments/assets/48430b7a-b6ed-42c7-8223-c21f4b44e2ee" />

Enhanced image after HSV-based equalization is displayed

<img width="903" height="354" alt="image" src="https://github.com/user-attachments/assets/349a28b9-9603-483b-a7f0-8f23d6a9e139" />

Histogram of enhanced image shows better intensity distribution  

<img width="928" height="307" alt="image" src="https://github.com/user-attachments/assets/2987cbe9-a421-470c-9905-0496ed2bc6dc" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.

