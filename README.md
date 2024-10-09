# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('HappyFish.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5) 
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y) 

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

canny_edges = cv2.Canny(gray_image, 50, 150)

plt.figure(figsize=(12, 12))

# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Sobel Edge Detection
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

# Laplacian Edge Detection
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

# Canny Edge Detection
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')

plt.tight_layout()
plt.show()
```
## Output:
### ORIGINAL IMG
![Screenshot 2024-10-08 112110](https://github.com/user-attachments/assets/9f5202cf-674c-4266-9b8f-6912b79dd73f)
### SOBEL EDGE DETECTOR
![Screenshot 2024-10-08 112119](https://github.com/user-attachments/assets/e41c5779-adad-46ee-a00d-0aa745c913c8)
### LAPLACIAN EDGE DETECTOR
![Screenshot 2024-10-08 112129](https://github.com/user-attachments/assets/1a4be947-9ce0-4c5f-b01c-3182b76b58ee)
### CANNY EDGE DETECTOR
![Screenshot 2024-10-08 112136](https://github.com/user-attachments/assets/3ca1732f-b366-48a7-9a6c-862599d9c6e9)
## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
