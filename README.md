# Edge-Linking-using-Hough-Transformm
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

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("facebook_logo.jpg",0)
img1=cv2.imread("facebook_logo.jpg",1)
img1=cv2.cvtColor(img1,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray=cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title("Original Image")
plt.figure(figsize=(13,13))
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
lines=cv2.HoughLinesP(canny,1,np.pi/280,threshold=180,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img1,(x1,y1),(x2,y2),(255,0,0),200)
plt.imshow(img1)
plt.title("Result Image")
```
## Output

### Input image and grayscale image

<img width="652" height="320" alt="Screenshot 2025-10-09 152231" src="https://github.com/user-attachments/assets/10beb406-d79d-4ff1-83a3-e0a9a5182781" />

<img width="650" height="332" alt="Screenshot 2025-10-09 152253" src="https://github.com/user-attachments/assets/89415800-7851-4e36-9cba-54ffda880bcf" />

### Canny Edge detector output

<img width="717" height="357" alt="Screenshot 2025-10-09 152305" src="https://github.com/user-attachments/assets/d67a1561-3b93-4826-9df4-6ab3efb10cec" />

### Display the result of Hough transform

<img width="708" height="346" alt="Screenshot 2025-10-09 152317" src="https://github.com/user-attachments/assets/0b65e5b3-4800-4305-892a-7eb351eb2475" />

### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform
