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

## Program :
```
import cv2
import matplotlib.pyplot as plt

# 1. Read the image using imread
# Replace 'your_image.jpg' with your actual file path
img = cv2.imread('rose.png')

# 2. Convert the color (Note: OpenCV reads in BGR, so we convert BGR to RGB for Matplotlib)
gray = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
gray_single_channel = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY) # Often used for processing
gray = cv2.GaussianBlur(gray, (3,3), 0)

# --- Sobel X ---
sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=5)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(sobelx)
plt.title("Sobel X axis")
plt.axis("off")
plt.show()

# --- Sobel Y ---
# 3. Complete the Sobel Y code
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=5) 
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(sobely)
plt.title("Sobel Y axis")
plt.axis("off")
plt.show()

# --- Sobel XY ---
sobelxy = cv2.Sobel(gray, cv2.CV_64F, 1, 1, ksize=5)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
# 4. Add the subplot command for the second image
plt.subplot(1,2,2)
plt.imshow(sobelxy)
plt.title("Sobel XY axis")
plt.axis("off")
plt.show()

# --- Laplacian ---
lap = cv2.Laplacian(gray, cv2.CV_64F)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
# 5. Display the image using imshow
plt.imshow(lap) 
plt.title("Laplacian Edge Detector")
plt.axis("off")
plt.show()

# --- Canny ---
canny = cv2.Canny(img, 120, 150) # Canny usually works best on the original or grayscale
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(gray)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(canny, cmap='gray')
# 6. Provide the title
plt.title("Canny Edge Detection") 
plt.axis("off")
plt.show()
```

## Output:
### SOBEL EDGE DETECTOR

<img width="803" height="522" alt="image" src="https://github.com/user-attachments/assets/f1c08758-6f10-4f34-a2df-1e5ac82f44c1" />
<img width="790" height="516" alt="image" src="https://github.com/user-attachments/assets/8682a467-bf63-4ed2-835e-7dab70a10b85" />
<img width="811" height="527" alt="image" src="https://github.com/user-attachments/assets/001f40e9-d194-4fe1-b7a4-0a0b343739db" />

### LAPLACIAN EDGE DETECTOR
<img width="797" height="531" alt="image" src="https://github.com/user-attachments/assets/aad3696c-0631-489a-a9d4-2d2d350311cc" />

### CANNY EDGE DETECTOR
<img width="801" height="530" alt="image" src="https://github.com/user-attachments/assets/26ca9c16-8d7e-450e-b7ea-794501bba2a7" />


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
