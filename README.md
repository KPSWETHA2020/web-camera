Image-Acquisition-from-Web-Camera

Aim:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

Software Used
Anaconda - Python 3.7

Algorithm
Step 1:Use VideoCapture(0) to access web camera

Step 2:
Use imread to read the video or image
Step 3:
use imwrite to save the images
Step 4:
use imshow to save imaage
Step 5:
End the program and close the output video windows by pressing 'q'.
Program:
### Developed By:Swetha.k.p
### Register No:212220230053

## i) Write the frame as JPG file
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)





## ii) Display the video
import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()






Output
i) Write the frame as JPG image

![ss1](https://user-images.githubusercontent.com/75235209/161907226-e080c6fe-bfc3-47d9-a940-a0cb5e2f1774.PNG)


ii) Display the video
![ss2](https://user-images.githubusercontent.com/75235209/161907273-e27e2580-7115-49a7-b237-7cc9aedc3124.PNG)


iii) Display the video by resizing the window

![ss5](https://user-images.githubusercontent.com/75235209/161955427-219d4005-53e6-48c2-abd0-57bb4ef573eb.PNG)


iv) Rotate and display the video
![ss6](https://user-images.githubusercontent.com/75235209/161956506-b593175a-4ed8-4311-939a-8a7167261747.PNG)



Result:
Thus the image is accessed from webcamera and displayed using openCV.
