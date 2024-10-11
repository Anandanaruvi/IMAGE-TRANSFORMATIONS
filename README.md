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
![PHO 2 EX 4](https://github.com/user-attachments/assets/82d2176f-62e6-49ad-8602-d452fe9e243d)




### ii) Image Scaling:
```

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

### OUTPUT:

![PHO 3 EX 4](https://github.com/user-attachments/assets/3a332f64-2301-4fa9-a5d7-cacad93230ff)





### iii)Image shearing:
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### OUTPUT:

![image](https://github.com/user-attachments/assets/45ef034a-0741-4703-a856-4d7e6b13b319)



### iv)Image Reflection:

```

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/19985382-4a9b-4d12-818e-7eaa66afe52e)





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
![image](https://github.com/user-attachments/assets/18d0a6a8-4376-43d9-8074-fb3c7b94e2f3)





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
![image](https://github.com/user-attachments/assets/9faff588-0267-4f09-85fb-0b58bf42e105)






### RESULT:

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
