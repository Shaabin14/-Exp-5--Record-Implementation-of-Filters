# Image Smoothing and Sharpening Using OpenCV

## Aim:

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By:

- **Name:** SHAABIN R S
- **Register No:** 212224230259

---

## Program:



### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread(r"C:\Users\admin\OneDrive\Desktop\ai assistant\WhatsApp Image 2026-10-30 at 8.45.52 AM.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="895" height="558" alt="image" src="https://github.com/user-attachments/assets/e716e064-9e1c-4423-ba07-ffaa26e38d25" />


#### ii) Using Weighted Averaging Filter
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="682" height="427" alt="image" src="https://github.com/user-attachments/assets/92351063-540b-4f72-9985-317db5e98f85" />


#### iii) Using Gaussian Filter
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="655" height="415" alt="image" src="https://github.com/user-attachments/assets/de1ce0e0-3cce-4cdb-a1ad-85169726d15b" />


#### iv)Using Median Filter
```python
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="933" height="563" alt="image" src="https://github.com/user-attachments/assets/a0eb404c-e655-4f13-8bbb-4024eabdc697" />

### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output
<img width="681" height="422" alt="image" src="https://github.com/user-attachments/assets/4676bd87-f717-47ce-b2a7-7ecbe11340e9" />


#### ii) Using Laplacian Operator
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
<img width="661" height="413" alt="image" src="https://github.com/user-attachments/assets/eba5097d-beec-4278-9dbd-299b01049c9c" />


##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
