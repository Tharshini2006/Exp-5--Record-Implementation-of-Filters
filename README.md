## EXP. 5 – IMPLEMENTATION OF FILTERS USING OPENCV

## NAME  : THARSHINI.M
## REG NO : 212224230287

## Aim

To implement different smoothing and sharpening filters using OpenCV and Python to enhance image quality and display the filtered images for comparison.

## Software Requirements

- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Filters Implemented

### Smoothing Filters
1. Average Filter
2. Weighted Average Filter
3. Gaussian Filter
4. Median Filter

### Sharpening Filters
1. Laplacian Kernel
2. Laplacian Operator

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the image from BGR to RGB format.
4. Apply the Average Filter using a custom kernel.
5. Apply the Weighted Average Filter using a weighted kernel.
6. Apply the Gaussian Filter using `cv2.GaussianBlur()`.
7. Apply the Median Filter using `cv2.medianBlur()`.
8. Apply the Laplacian Kernel using `cv2.filter2D()`.
9. Apply the Laplacian Operator using `cv2.Laplacian()`.
10. Display the original and processed images separately.

## Implementation

### 1. Import Libraries

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
```

### 2. Read the Input Image

```python
image1 = cv2.imread("Image.png")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
```

## OUTPUT:
<img width="248" height="347" alt="image" src="https://github.com/user-attachments/assets/78f323af-5e1e-493c-a87b-38b6f78b7274" />


### 3. Average Filter

```python
kernel = np.ones((11,11), np.float32)/169
image3 = cv2.filter2D(image2, -1, kernel)

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

## OUTPUT:
<img width="544" height="352" alt="{D4A1D268-16C9-48D1-9947-97FDE23ABC92}" src="https://github.com/user-attachments/assets/db34dbde-e500-4685-a8aa-00f33e759d4e" />


### 4. Weighted Average Filter

```python
kernel1 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="401" height="252" alt="{33542665-43DF-4DB3-87A5-8F554843E561}" src="https://github.com/user-attachments/assets/784f606c-c036-48df-880c-a03d1cd4ed7f" />


### 5. Gaussian Filter

```python
gaussian_blur = cv2.GaussianBlur(image2, (33,33), 0, 0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="390" height="259" alt="{1772FF94-93A5-4AA6-AB41-FD29E49CC1BA}" src="https://github.com/user-attachments/assets/da7ab1d3-6a1c-417e-998a-df3e1ddbf03e" />


### 6. Median Filter

```python
median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="549" height="353" alt="{FC930CCC-B198-490F-B827-484BB8291843}" src="https://github.com/user-attachments/assets/40fc9b7a-a1d3-4382-9a94-26ab24c3edc8" />


### 7. Laplacian Kernel

```python
kernel2 = np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="388" height="255" alt="{66C89A4B-10C1-4538-9A8A-E743CDBEA1FC}" src="https://github.com/user-attachments/assets/a7f41759-f293-48d6-93cd-0429be3686b6" />


### 8. Laplacian Operator

```python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

<img width="397" height="269" alt="image" src="https://github.com/user-attachments/assets/f90e0b08-6510-41f8-92b5-1593efb6baca" />


## Result

Thus, different smoothing and sharpening filters were successfully implemented using OpenCV and Python. Smoothing filters reduce noise, while sharpening filters enhance image edges and details.
