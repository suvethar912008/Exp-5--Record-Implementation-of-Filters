# Exp-5--Record-Implementation-of-Filters
# Image Smoothing and Sharpening Using OpenCV
# Aim
To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

The program performs the following operations: Read and display an input image Apply Averaging filter Apply Weighted Averaging filter Apply Gaussian filter Apply Median filter Apply Laplacian sharpening using kernel Apply Laplacian operator Display all outputs for comparison

# Software Used
Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib

# Algorithm
# Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

# Step 2:
Read the input image (e.g., image.jpg).

# Step 3:
Convert the image from BGR to RGB format for display.

# Step 4:
Apply Averaging Filter using cv2.blur().

# Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

# Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

# Step 7:
Apply Median Filter using cv2.medianBlur().

# Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

# Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

# Step 10:
Display all filtered images using a grid layout for comparison.

#Developed By Name: Suvetha R
#Register No: 212225220113

# Program
Smoothing Filters
# i) Using Averaging Filter

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("spider.png")
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

<img width="582" height="312" alt="image" src="https://github.com/user-attachments/assets/12e01ccc-7b1a-466a-bba4-0f65eddfda33" />

# ii) Using Weighted Averaging Filter

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="546" height="310" alt="image" src="https://github.com/user-attachments/assets/5756de39-abff-4b4d-ab9a-bfbb1f9b01aa" />

# iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
<img width="612" height="312" alt="image" src="https://github.com/user-attachments/assets/5ae8dd76-ebef-4f6c-8b1e-064c080d18ba" />

# iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

<img width="570" height="322" alt="image" src="https://github.com/user-attachments/assets/d3cf8a02-7b60-4dcf-a432-f0e56d65a669" />

# 3. Sharpening Filters
# i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

<img width="557" height="322" alt="image" src="https://github.com/user-attachments/assets/79699028-8fc8-4f4f-a42b-54245d37af01" />

# ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

<img width="582" height="332" alt="image" src="https://github.com/user-attachments/assets/8aa2704e-fe27-4df6-b3d4-02c6450aeead" />

# Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
