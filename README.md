# IMAGE-TRANSFORMATIONS
## NAME: SANTHOSH KUMAR R
## REG NO: 212223240153

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('flower.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6.Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))
```
```
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')

plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')

plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')

plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()


```
# Output:
<img width="1174" height="858" alt="image" src="https://github.com/user-attachments/assets/8b6b44ea-f7f1-4681-b0b9-cf09eca4267e" />

# 1. Translation
<img width="711" height="512" alt="image" src="https://github.com/user-attachments/assets/8419baa8-f745-40d0-9184-94c230d2aade" />

# 2. Scaling

### Output:
<img width="721" height="510" alt="image" src="https://github.com/user-attachments/assets/862b73eb-68c0-4a3a-990e-69230f2ffe07" />

# 3. Shearing

### Output:
<img width="726" height="524" alt="image" src="https://github.com/user-attachments/assets/38a9e798-b156-40c1-9d1b-a4ad282d160f" />

# 4. Reflection (Flip)

### Output:
<img width="676" height="479" alt="image" src="https://github.com/user-attachments/assets/a70b6b95-22d5-4cb1-bfe1-34999fce7dad" />

# 5. Rotation

### Output:
<img width="669" height="461" alt="image" src="https://github.com/user-attachments/assets/2c92c847-b424-4e65-b39c-711fab560434" />
# 6.Cropping

### Output:
<img width="433" height="419" alt="image" src="https://github.com/user-attachments/assets/685e3ed4-5a64-4286-9d50-18ae3c8bb576" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
