# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:
## Developed by : Priyanka A
## Reg.No. 212222230113
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('catt.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output

### Input image 
![image](https://github.com/PriyankaAnnadurai/Edge-Linking-using-Hough-Transformm/assets/118351569/efdb0669-f683-4c96-a73a-e57224438f62)

### Grayscale image
![image](https://github.com/PriyankaAnnadurai/Edge-Linking-using-Hough-Transformm/assets/118351569/851e7704-c116-40a5-97fb-328d40887a37)

### Canny Edge detector output

![image](https://github.com/PriyankaAnnadurai/Edge-Linking-using-Hough-Transformm/assets/118351569/f0482b9a-3380-4c12-a394-6720bd5f884d)


### Display the result of the Hough transform

![image](https://github.com/PriyankaAnnadurai/Edge-Linking-using-Hough-Transformm/assets/118351569/81e17cf4-a0e2-429a-8c78-168e1bb7f3d7)



## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
