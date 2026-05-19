# EXP-2-Record-Image Acquisition using Web Camera
# Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
# Step 1:
Use cv2.VideoCapture(0) to access web camera.

# Step 2:
Use cv2.imread to read the video or image.

# Step 3:
Use cv2.imwrite to save the image.

# Step 4:
Use cv2.imshow to show the video.

# Step 5:
End the program and close the output video window by pressing 'q'.

## Program :
Developed by: HIBA NASREEN M

Register Number: 212224040117

## i) Write the frame as JPG file 

```python
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()


```



## ii) Display the video

```python

import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

```


## iii) Display the video by resizing the window

```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video

```python
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
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```









## Output

### i) Write the frame as JPG image


<img width="665" height="535" alt="image" src="https://github.com/user-attachments/assets/8b78177b-dddb-4ab8-85a6-7e4c08b98b29" />



### ii) Display the video

<img width="666" height="511" alt="image" src="https://github.com/user-attachments/assets/666761c7-608e-4589-bc69-f3d2f320ebc6" />


### iii) Display the video by resizing the window

![Uploading image.png…]()




### iv) Rotate and display the video

<img width="390" height="511" alt="image" src="https://github.com/user-attachments/assets/4db072e8-9c90-4dc2-ac2c-f98a269732e3" />


## Result :
Thus the image is accessed from webcamera and displayed using openCV.
