# Detect-the-lines-using-Hough-Transform

##  Developed By: sribalakumaran r

## Register: No: 212225220104

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```
image = cv2.imread('bala.jpeg') 
```

---

###  Step 3: Convert to Grayscale

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 5: Display Images

```

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
```

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 6: Edge Detection (Canny)

```
edges = cv2.Canny(gray_image, 50, 150)
```

```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---


###  Step 7: Hough Transform

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line.flatten()
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

---

### Step 8: Display the result of Hough Transform (Image with lines):
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

## Output:

## Original image:

<img width="507" height="401" alt="image" src="https://github.com/user-attachments/assets/1723fd65-8dc8-4a1d-8402-e432ea5c3960" />

## Grayscale image:

<img width="588" height="416" alt="image" src="https://github.com/user-attachments/assets/b52448ba-36b2-4258-b00f-59b60a5c61f7" />


## Canny Edge Detector:

<img width="357" height="415" alt="image" src="https://github.com/user-attachments/assets/28a3fa60-e7a4-41c4-a10e-f5c80b6f2911" />

## Hough Transform:

<img width="400" height="445" alt="image" src="https://github.com/user-attachments/assets/2332d757-d561-42d5-8715-2ee1ee9c84f0" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
