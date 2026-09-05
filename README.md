# EX-12-PROJECT-Face-Detection-with-Haar-Cascades
Face Detection using Haar Cascades with OpenCV and Matplotlib
# Aim
To write a Python program using OpenCV to perform the following image manipulations:
i) Extract ROI from an image.
ii) Perform face detection using Haar Cascades in static images.
iii) Perform eye detection in images.
iv) Perform face detection with label in real-time video from webcam.

# Software Required
1.Anaconda - Python 3.7 or above
2.OpenCV library (opencv-python)
3.Matplotlib library (matplotlib)
4.Jupyter Notebook or any Python IDE (e.g., VS Code, PyCharm)
# Algorithm
I) Load and Display Images
Step 1: Import necessary packages: numpy, cv2, matplotlib.pyplot
Step 2: Load grayscale images using cv2.imread() with flag 0
Step 3: Display images using plt.imshow() with cmap='gray'
II) Load Haar Cascade Classifiers
Step 1: Load face and eye cascade XML files
III) Perform Face Detection in Images
Step 1: Define a function detect_face() that copies the input image
Step 2: Use face_cascade.detectMultiScale() to detect faces
Step 3: Draw white rectangles around detected faces with thickness 10
Step 4: Return the processed image with rectangles
IV) Perform Eye Detection in Images
Step 1: Define a function detect_eyes() that copies the input image
Step 2: Use eye_cascade.detectMultiScale() to detect eyes
Step 3: Draw white rectangles around detected eyes with thickness 10
Step 4: Return the processed image with rectangles
V) Display Detection Results on Images
Step 1: Call detect_face() or detect_eyes() on loaded images
Step 2: Use plt.imshow() with cmap='gray' to display images with detected regions highlighted
VI) Perform Face Detection on Real-Time Webcam Video
Step 1: Capture video from webcam using cv2.VideoCapture(0)
Step 2: Loop to continuously read frames from webcam
Step 3: Apply detect_face() function on each frame
Step 4: Display the video frame with rectangles around detected faces
Step 5: Exit loop and close windows when ESC key (key code 27) is pressed
Step 6: Release video capture and destroy all OpenCV windows


# Program:
Developed by LITYA M
REG NO:- 212225230152
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
image = cv2.imread("litya .jpeg")

if image is None:
    print("Image not found")
    exit()

# Extract ROI
roi = image[50:250, 50:250]

# Convert BGR to RGB
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
roi = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.subplot(1, 2, 1)
plt.imshow(image)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(roi)
plt.title("ROI")
plt.axis("off")

plt.show()
```
```
roi = image[100:420, 200:550]
mask = np.zeros_like(image)
mask[100:420, 200:550] = roi
segmented = cv2.bitwise_and(image, mask)
plt.imshow(cv2.cvtColor(segmented, cv2.COLOR_BGR2RGB))
plt.title("Segmented ROI")
plt.axis('off')
plt.show()
```
```
image = cv2.imread('litya .jpeg')
if image is None:
    print("Error: dhoni.jpeg not found")
    exit()
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blur = cv2.GaussianBlur(gray, (5, 5), 0)
edges = cv2.Canny(blur, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detection")
plt.axis('off')
plt.show()
```
```
contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
result = image.copy()
for c in contours:
    if cv2.contourArea(c) > 50:
        x, y, w, h = cv2.boundingRect(c)
        cv2.rectangle(result, (x, y), (x+w, y+h), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
plt.title("Contour Detection")
plt.axis('off')
plt.show()
```
# output
<img width="687" height="490" alt="image" src="https://github.com/user-attachments/assets/daf758bf-e17c-4c6e-9e20-0c657ad8c631" />
<img width="490" height="517" alt="image" src="https://github.com/user-attachments/assets/9857b5dd-ce23-4f4a-a793-b208e60ecd87" />
<img width="395" height="511" alt="image" src="https://github.com/user-attachments/assets/66fe72db-57b1-453d-ba88-49566221b836" />

<img width="325" height="531" alt="image" src="https://github.com/user-attachments/assets/588e5ea8-712f-404a-bcea-414c205ca307" />


# Result

Thus, the Python program for ROI extraction, face detection, eye detection, and real-time face detection using Haar Cascade classifiers was successfully 
implemented using OpenCV and Matplotlib.

..











..










..


...







..




..
.
..
.











..
..

..




..
..
..





..












..














..






..
