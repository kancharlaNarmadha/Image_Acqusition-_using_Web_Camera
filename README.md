## EX 02 Image_Acqusition-_using_Web_Camera
## DATE
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>
### Step 2:
Use cv2.imread to read the video or image
<br>
### Step 3:
Use cv2.imwrite to save the image
<br>
### Step 4:
Use cv2.imshow to show the video
<br>
### Step 5:
End the program and close the output video window by pressing 'q'.
<br>
## Program:
### Developed By:Kancharla Narmadha
### Register No:212222110016
## i) Write the frame as JPG file
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("keerthana.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
``` Python
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
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
``` Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![dip 1](https://github.com/Keerthanasampathkumar/Image_Acqusition-_using_Web_Camera/assets/119477890/0bfc9af5-dc44-4e2e-b6d2-9117957a7bd7)

### ii) Display the video
![dip 2](https://github.com/Keerthanasampathkumar/Image_Acqusition-_using_Web_Camera/assets/119477890/d92e048a-3968-4108-bc6b-018cb74e1154)


### iii) Display the video by resizing the window
![dip 3](https://github.com/Keerthanasampathkumar/Image_Acqusition-_using_Web_Camera/assets/119477890/a720fa8e-4b62-43d1-83db-0d61cc455d7d)


### iv) Rotate and display the video

![dip 4](https://github.com/Keerthanasampathkumar/Image_Acqusition-_using_Web_Camera/assets/119477890/2851d1cb-4bfc-4362-8f2b-0598c49703e2)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
