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

## PROGRAM
## Developed by : V.SHRIYHA
## Reg No : 212223240267
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('My pic.jpeg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
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
<img width="431" height="565" alt="image" src="https://github.com/user-attachments/assets/17fe48d5-e84e-42f2-b303-ea866c81b0ee" />
<img width="397" height="563" alt="image" src="https://github.com/user-attachments/assets/5c90fa52-057a-4cf9-a163-aa9d49c660c6" />


### Canny Edge detector output
<img width="398" height="562" alt="image" src="https://github.com/user-attachments/assets/6ebbc4ae-70bd-4d5a-9a89-571c0a76c1ed" />

### Display the result of Hough transform
<img width="395" height="554" alt="image" src="https://github.com/user-attachments/assets/225ac608-a8ce-4070-ab59-5a14c4c011f0" />

## RESULT
Hence a Python program to detect the lines using Hough Transform is implemented.
