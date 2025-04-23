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
Import CV2,numpy and the other required libraries

### Step 2:
Create an instance of Video Capture and save the displayed image

### Step 3:
Capture video and using numpy resize the shape of the window and display the video

### Step 4:

Rotate the captured image by 180*

## Program:
``` Python
### Developed By: Hashwatha M
### Register No: 212223240051

## i) Write the frame as JPG file

import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

## ii) Display the video

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window

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
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

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
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![image](https://github.com/user-attachments/assets/cc5f39f9-c5e8-4f2a-83c3-0decf8881d80)

### ii) Display the video

![image](https://github.com/user-attachments/assets/750355f9-85b3-46fb-b628-94e92a8dd16c)

### iii) Display the video by resizing the window

![image](https://github.com/user-attachments/assets/8c356ab7-fa4d-4478-b6dc-961e8a96ce7c)

### iv) Rotate and display the video
![image](https://github.com/user-attachments/assets/68c6e4b6-1280-4a0f-ac72-06212f538c7f)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
