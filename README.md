# EXP 10 : OPENING AND CLOSING
### NAME : MUKESH KUMAR S
### REGISTER NO : 212223240099

## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step1:
Read or create a binary image containing text or shapes.
<br>


### Step2:
Create a structuring element (kernel) of a specific size to apply morphological operations.
<br>

### Step3:
Perform Opening operation by first eroding the image and then dilating the result.
<br>

### Step4:
Perform Closing operation by first dilating the image and then eroding the result.
<br>

### Step5:
Display the original image, the output of Opening, and the output of Closing.
<br>

 
## Program:

``` Python
# Import the necessary packages
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Create the text using cv2.putText
img = np.zeros((200, 600), dtype=np.uint8)     # Black background
cv2.putText(img, "OPENCV", (50, 120), cv2.FONT_HERSHEY_SIMPLEX, 4, (255), 15)

# Create the structuring element (kernel)
kernel = np.ones((7, 7), np.uint8)

# Use the Opening Operation (Erosion followed by Dilation)
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

# Use the Closing Operation (Dilation followed by Erosion)
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

# Display the images
titles = ["Original Image", "Opening", "Closing"]
images = [img, opening, closing]

for i in range(3):
    plt.subplot(1, 3, i + 1)
    plt.imshow(images[i], cmap="gray")
    plt.title(titles[i])
    plt.axis("off")

plt.show()



```
## Output:

### Displaying the input Image, result of Opening and result of Closing


<img width="658" height="131" alt="Screenshot 2025-11-04 191442" src="https://github.com/user-attachments/assets/2893c5c2-15aa-44f7-9221-5d4fa848b7d5" />



## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
