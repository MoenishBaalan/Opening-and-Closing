# Opening-and-Closing

## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:
```
#Name:  Moenish Baalan G
#Reg No: 212223220057
```
## Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

def load_img():
    blank_img =np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='MOENISH',org=(100,350), fontFace=font,fontScale= 3,color=(255,255,255),thickness=20,lineType=cv2.LINE_AA)
    return blank_img
def display_img(img):
    fig = plt.figure(figsize=(6,7))
    ax = fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()
img = load_img()
display_img(img)
white_noise = np.random.randint(low=0, high=3, size=(600, 600), dtype='uint8')
white_noise
white_noise = white_noise*255
white_noise
noise_img = white_noise+img
display_img(noise_img)
kernel = np.ones((5,5), np.uint8)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
black_noise = np.random.randint(low=0,high=2,size=(600,600))
black_noise
black_noise= black_noise * -255
black_noise_img = img + black_noise
black_noise_img
black_noise_img[black_noise_img==-255] = 0
display_img(black_noise_img)
closing = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing)  

```

## Output:


<img width="590" height="519" alt="image" src="https://github.com/user-attachments/assets/b4708716-4ce2-486d-84aa-6e965fcd7af3" />

<img width="531" height="518" alt="image" src="https://github.com/user-attachments/assets/0351cc56-a3d9-4bd2-96ce-242f7359dce1" />

<img width="591" height="520" alt="image" src="https://github.com/user-attachments/assets/2abe95ea-93cd-42c7-81ad-7fcd7a39c791" />

<img width="525" height="528" alt="image" src="https://github.com/user-attachments/assets/679a0bf8-3b61-4f2d-b1bc-38b45056c0ff" />

<img width="572" height="507" alt="image" src="https://github.com/user-attachments/assets/52a18b1d-99b4-4dd8-bcb9-310b11e41975" />


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
