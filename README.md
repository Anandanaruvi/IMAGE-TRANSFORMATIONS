# IMAGE-TRANSFORMATIONS.


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### step 6:
Rotate the image using angle function.am:
## Program:
```python
Developed By:A.ARUVI.
Register Number:212222230014.
```
### Load the image:
### ORIGINAL IMAGE:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('flowerbouqet.jpg.webp')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Plot the original and transformed images
plt.figure(figsize=(12, 8))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
![PHO 1 EX 4](https://github.com/user-attachments/assets/b05ef64d-d095-4e86-b091-d03789ac43a5)

### i)Image Translation:
```

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/ed6003df-76c3-415a-b429-3870ac9ddbfe)





### ii) Image Scaling:
```

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

### OUTPUT:

![image](https://github.com/user-attachments/assets/24f4e867-0515-440d-9d98-4f525b303065)





### iii)Image shearing:
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/a598eafb-6107-47c0-b0b4-29c2faecbb04)


### iv)Image Reflection:

```

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/ad6e684c-b2d9-449e-bd8a-20477501275d)


### v.)Image Rotation:
```

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.tight_layout()
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/6fa2f319-0d45-4a23-ae87-4646963046ce)



### vi.)Image Cropping:
```
cropped_image = image_rgb[100:300, 500:2000]   # Crop a portion of the image
plt.figure(figsize=(17, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/67886f88-c430-462f-be99-0c90464dec31)





### RESULT:

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
