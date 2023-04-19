# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import all the necessary modules for the program.

### Step2:
<br>
Load a image using imread() from cv2 module.

### Step3:
<br>
Convert the image to grayscale.

### Step4:
<br>
Using Canny operator from cv2,detect the edges of the image

### Step5:
<br>
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```Python
Developed by : HARIDHARSHINI.S
Register num : 212221230033

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('img1.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)

# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)

# Display the result
plt.imshow(edges1)

```
## Output

### Input image and grayscale image

![EX 8 A](https://user-images.githubusercontent.com/94168395/233028182-9214cf77-af47-4727-b346-faa25464d044.png)

### Canny Edge detector output

![EX 8 B](https://user-images.githubusercontent.com/94168395/233028269-48494848-52c2-471b-bebc-6a5571b9903a.png)

### Display the result of Hough transform

![EX 8 C](https://user-images.githubusercontent.com/94168395/233028802-34111bb6-1984-4ae1-a0d7-0d7f2134a390.png)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
