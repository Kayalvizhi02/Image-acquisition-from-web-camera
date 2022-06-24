### EX NO: 02
### DATE:
# <p align="center">Image Acquisition from Web Camera</p>
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Required:
Anaconda - Python 3.7
## Algorithm
### Step 1:

Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:

Write the captured image using cv2.imwrite("image.jpg",frame)

### Step 3:

Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:

display the image until the loop gets over

### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
### Developed By: KAYALVIZHI M
### Register No: 212220230024

## i) Write the frame as JPG file
```python3
import cv2

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("image.jpg",frame)


```
## ii) Display the video
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("image1",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## iii) Display the video by resizing the window
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


```
## iv) Rotate and display the video
```python3
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


```
## Output:

### i) Write the frame as JPG image

![Write the frame as jpg](https://user-images.githubusercontent.com/75413726/162441687-bd8c29dc-c170-4b09-90fa-a0a6af30fee9.jpg)

### ii) Display the video

![Display the video](https://user-images.githubusercontent.com/75413726/162441753-8e189766-56e0-461b-a768-bf52185bfc10.jpg)

### iii) Display the video by resizing the window

![Display the video by resizing the window](https://user-images.githubusercontent.com/75413726/162441813-45df0d7c-cdd5-43f6-ba47-3e0077699903.jpg)

### iv) Rotate and display the video

![Rotate and display the video](https://user-images.githubusercontent.com/75413726/162441861-75a982f0-4a1f-403f-bbf7-dc932f71933b.jpg)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
