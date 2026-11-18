# Experiment 04 – Image Transformations Using OpenCV

## AIM

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

1. Image Translation
2. Image Scaling (Resizing)
3. Image Shearing
4. Image Reflection (Flipping)
5. Image Rotation
6. Image Cropping

## SOFTWARE REQUIRED

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## ALGORITHM

**Step 1:** Import the required libraries: OpenCV, NumPy and Matplotlib.

**Step 2:** Read the input image (`city.png`) in colour mode and display the original image.

**Step 3: Image Translation**
- Create a translation matrix to shift the image.
- Move the image 100 pixels to the right and 50 pixels down.
- Apply the transformation using `cv2.warpAffine()`.
- Display the original and translated images.

**Step 4: Image Scaling**
- Resize the image using scaling factors of 5.0 and 2.0.
- Use `cv2.resize()` to perform image scaling.
- Display the original and scaled images.

**Step 5: Image Shearing**
- Create a transformation matrix for horizontal and vertical shearing.
- Apply the transformation using `cv2.warpAffine()`.
- Display the sheared image.

**Step 6: Image Reflection**
- Perform image flipping using `cv2.flip()`.
- Apply horizontal, vertical and both-axis reflections.
- Display the reflected images.

**Step 7: Image Rotation**
- Create a rotation matrix using `cv2.getRotationMatrix2D()`.
- Rotate the image by 45 degrees.
- Apply the transformation using `cv2.warpAffine()`.
- Display the rotated image.

**Step 8: Image Cropping**
- Define the starting coordinates and dimensions of the image.
- Extract a specific region using array slicing.
- Display the cropped image.

---

## PROGRAM

### i) Import libraries and read the original image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('city.png')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

### ii) Image Translation

```python
# Translation factors
tx, ty = 100, 50

# Translation matrix
M_translation = np.float32([
    [1, 0, tx],
    [0, 1, ty]
])

translated_image = cv2.warpAffine(
    image,
    M_translation,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```

### iii) Image Scaling

```python
# Scaling factors
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image,
    None,
    fx=fx,
    fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')
```

### iv) Image Shearing

```python
# Shearing matrix
shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image,
    shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
```

### v) Image Reflection

```python
# YOUR CODE HERE
# Horizontal reflection
# Vertical reflection
# Both-axis reflection

# Display the reflected image
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')
```

### vi) Image Rotation

```python
# Get image dimensions
(height, width) = image.shape[:2]

angle = 45
center = (width // 2, height // 2)

# Get rotation matrix
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)

rotated_image = cv2.warpAffine(
    image,
    M_rotation,
    (width, height)
)

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
```

### vii) Image Cropping

```python
# Define cropping coordinates
x, y, w, h = 100, 100, 200, 150

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

---

## OUTPUT

The following outputs are obtained after executing the Python program:

1. Original Image
2. Translated Image
3. Scaled Image
4. Sheared Image
5. Reflected Image
6. Rotated Image
7. Cropped Image

### Output Screenshots

Upload your output screenshots into the `outputs` folder in your GitHub repository.

**1. Original and Translated Image**

<img width="515" height="310" alt="image" src="https://github.com/user-attachments/assets/413a74b8-a1d1-45c9-9f32-e3aa6d147771" />

<img width="515" height="310" alt="image" src="https://github.com/user-attachments/assets/5ec63a12-793c-4687-9148-ab712a363d05" />


**2. Scaled Image**

<img width="515" height="148" alt="image" src="https://github.com/user-attachments/assets/318add0c-dd9a-4d43-9d9e-5e12773675e5" />


**3. Sheared Image**

<img width="515" height="310" alt="image" src="https://github.com/user-attachments/assets/7c07409b-3370-4823-9aad-e77d44dbef2e" />


**4. Reflected Image**

<img width="515" height="310" alt="image" src="https://github.com/user-attachments/assets/2778c6d3-83de-4796-9434-72dbc83ceebe" />


**5. Rotated Image**

<img width="515" height="310" alt="image" src="https://github.com/user-attachments/assets/c1d951bf-7b95-4877-9226-728b6b42f312" />


**6. Cropped Image**

<img width="512" height="409" alt="image" src="https://github.com/user-attachments/assets/e322a5a6-e374-4763-b56e-390138995611" />


---

## RESULT

Thus, various geometric transformations such as image translation, scaling, shearing, reflection, rotation and cropping were successfully performed using Python and OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
