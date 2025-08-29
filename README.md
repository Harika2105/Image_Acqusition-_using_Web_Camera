## EXP-2-Record-Image Acquisition using Web Camera

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

### Developed By: S.harika
### Register No: 212224240155

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

cv2.imshow('captured_frame', frame)

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

cv2.imshow('212224240155_Harika',image)

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

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame

cv2.imshow('212224240155',image)

cv2.waitKey(5000) 

image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)

cap.release()
cv2.destroyAllWindows()
```


## Output

### i) Write the frame as JPG image

<img width="803" height="601" alt="Screenshot 2025-08-29 224715" src="https://github.com/user-attachments/assets/4b870565-6d24-4a4e-8266-bee3d8f6a4d7" />



### ii) Display the video

<img width="803" height="601" alt="Screenshot 2025-08-29 224715" src="https://github.com/user-attachments/assets/a73c4e9c-cd21-4638-8947-8b682d4c427b" />



### iii) Display the video by resizing the window

<img width="799" height="600" alt="Screenshot 2025-08-29 224810" src="https://github.com/user-attachments/assets/da5c364c-da83-48e4-bf80-945a97451103" />

### iv) Rotate and display the video

<img width="798" height="594" alt="Screenshot 2025-08-29 224843" src="https://github.com/user-attachments/assets/91fcf28a-ee28-4b5a-9ddd-ae1569f07248" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
