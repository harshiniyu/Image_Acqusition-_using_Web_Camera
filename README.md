
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
<br>Use cv2.VideoCapture(0) to access web camera.

### Step 2:
<br>
Use cv2.imread to read the video or image.

### Step 3:
<br>Use cv2.imwrite to save the image.

### Step 4:
<br>Use cv2.imshow to show the video.

### Step 5:
<br>End the program and close the output video window by pressing 'q'.

## Program:

### Developed By:Harshini Y
### Register No:212223240050

## i) Write the frame as JPG file

```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("bald_cat.jpg",frame)
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

cv2.imshow('',image)
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

cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![Screenshot 2025-04-21 205837](https://github.com/user-attachments/assets/cf729389-6183-4d38-a6fb-f683ead3e721)




### ii) Display the video
![Screenshot 2025-04-21 205956](https://github.com/user-attachments/assets/b0007c42-f7f8-4b24-8f8b-989ff4cfb0df)



### iii) Display the video by resizing the window
![Screenshot 2025-04-21 210017](https://github.com/user-attachments/assets/00be4bdb-d30e-4697-8210-7c19f31ce6ed)




### iv) Rotate and display the video
![Screenshot 2025-04-21 210041](https://github.com/user-attachments/assets/76ab5863-3111-4bf2-9b67-0ba2cc0d716f)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
