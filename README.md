# Image-Acquisition-from-Web-Camera
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.
## Program:
``` Python
### Developed By:Dineshkumar V
### Register No:212220230013

## i) Write the frame as JPG file

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("New.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()





## ii) Display the video

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('image', frame)
    
    if cv2.waitKey(1) == ord('k'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window

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
    

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video

import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)


    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)


    image[height//2:, width//2:] = smaller_frame
    

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
![i11](https://user-images.githubusercontent.com/75235427/161986895-f68f22ae-73e2-452e-b19f-b9bb03385c0f.jpg)


### ii) Display the video

![i12](https://user-images.githubusercontent.com/75235427/161986917-2c61b242-3470-47d8-892b-2a570b2015b6.jpg)


### iii) Display the video by resizing the window

![i13](https://user-images.githubusercontent.com/75235427/161986931-2e834e12-c24b-4553-989f-fa5964512da8.jpg)


### iv) Rotate and display the video

![i14](https://user-images.githubusercontent.com/75235427/161986954-2a37885f-5501-43fc-8975-f99bc8beb4f3.jpg)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
