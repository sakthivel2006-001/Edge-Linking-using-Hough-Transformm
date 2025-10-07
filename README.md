# Edge-Linking-using-Hough-Transformm
## NAME : SAKTHIVEL S
## REG NO:212223220090
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Program:
```
NAME: PRIYADHARSHINI P
REG: 212223240128
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('exp7img.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/ce919e78-cdf8-4861-a44f-f4fd562a234a" />
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/2009b2e0-9607-44dc-b1a3-b5ae2c3ee63f" />



### Canny Edge detector output
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/db90a6e1-bafc-4c30-a054-52c872adef43" />


### Display the result of Hough transform
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/d23509d7-bf23-4769-ba8a-46e88be8be77" />

