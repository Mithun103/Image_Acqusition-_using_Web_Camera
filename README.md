![Screenshot 2024-09-28 104032](https://github.com/user-attachments/assets/5ef470f5-32d4-41ec-acb4-2d2670d1c72b)![Screenshot 2024-09-28 104113](https://github.com/user-attachments/assets/58c0da04-1e59-4f92-9cbb-082a5d09a67d)
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
### Developed By: MITHUN M S
### Register No: 212222240067

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)

ret,frame=viedoCaptureObject.read()
cv2.imwrite("webcam_img.jpg",frame)

viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()

cv2.imshow('fan', frame)

cv2.waitKey(10000)


cap.release()
cv2.destroyAllWindows()

```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame

cv2.imshow('ws.jpg',image)

cv2.waitKey(5000)  

image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)

cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video

```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('mithun_212222240067',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## Output

### i) Write the frame as JPG image


![webcam_img](https://github.com/user-attachments/assets/86468e1d-4b3c-4d0a-8fd1-10ffb68224af)


### ii) Display the video
![Screenshot 2024-09-28 104032](https://github.com/user-attachments/assets/7c770614-d122-4a56-8c39-e317189584cb)

### iii) Display the video by resizing the window

![Screenshot 2024-09-28 104113](https://github.com/user-attachments/assets/5279706d-ba34-4e59-91b6-ef28b8264e43)


### iv) Rotate and display the video

![Screenshot 2024-09-28 104133](https://github.com/user-attachments/assets/84e57287-799d-4a05-989b-33e38261ee5c)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
