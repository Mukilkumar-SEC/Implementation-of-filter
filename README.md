# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.

### Step 2: 
Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.

### Step 3: 
Apply different filters:
1. Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D().
2. Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D().
3. Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur.
4. Median Filter: Use cv2.medianBlur() to reduce noise.
5. Laplacian Operator: Use cv2.Laplacian() to apply edge detection.
    

### Step 4: 
Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.

### Step 5: 
Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.

## Program:
### Developed By   : Mukil kumar v
### Register Number: 212222230087

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1 = cv2.imread("dog.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/9a30ef35-a8ec-40ec-953d-e8e4fdce8313)

### 1. Smoothing Filters

#### i) Using Averaging Filter
```
kernel = np.ones((11, 11), np.float32) / 121
averaging_image = cv2.filter2D(image2, -1, kernel)
plt.imshow(averaging_image)
plt.title("Averaging Filter Image")
plt.axis("off")
plt.show()
```

![image](https://github.com/user-attachments/assets/27a015a5-399e-4031-a2db-8bb37eddb4ce)

#### ii) Using Weighted Averaging Filter
```
kernel2 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

weighted_average_image = cv2.filter2D(image2, -1, kernel2)
plt.imshow(weighted_average_image)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/3e0ae3d2-710d-4659-be56-0a818d16adbe)

#### iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(image2, (11, 11), 0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/514bda73-883e-4c70-b860-ecd5fdcea1f4)


#### iv) Using Median Filter
```
median_blur = cv2.medianBlur(image2, 11)
plt.imshow(median_blur)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/edd15c6f-234c-4c03-8a52-5a245128d309)

### 2. Sharpening Filters
#### i) Using Laplacian Kernal
```
sharpened_image = cv2.filter2D(gaussian_blur, -1, kernel2)
plt.imshow(sharpened_image)
plt.title("Sharpened Image (Laplacian Kernel)")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/08fe1b6a-71cf-4bbd-9245-6a7c3484f566)


#### ii) Using Laplacian Operator
```
laplacian = cv2.Laplacian(image2, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/01305f6e-1441-425e-bd7e-220cf9b6ba5d)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
