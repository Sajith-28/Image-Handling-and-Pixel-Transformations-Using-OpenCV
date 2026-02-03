# Image-Handling-and-Pixel-Transformations-Using-OpenCV 
## NAME : SAJITH AHAMED F
## REG NO : 212223240144

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** SAJITH AHAMED F
- **Register Number:** 212223240144

## Ex. No. 01

#### ```python
```
import cv2
import matplotlib.pyplot as plt
```
# Read the image using OpenCV
```
img = cv2.imread('TK.JPG', cv2.IMREAD_COLOR)
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off') 
plt.show()
```

# Load the image
```
image = cv2.imread('TK.JPG')
```
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)

```
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```
# Draw a line from top-left to bottom-right

```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
# Draw a circle at the center of the image.
```
image = cv2.imread('TK.JPG') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

# Draw a rectangle around  the whole image
```
image = cv2.imread('TK.JPG') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

# Add the text "OpenCV Drawing" at the top-left corner of the image.
```
image = cv2.imread('TK.JPG') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
    

    

```

image = cv2.imread('TK.JPG')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
#  Convert the image from RGB to HSV and display it.
```
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
# Convert the image from RGB to GRAY and display it. 
```
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

# Convert the image from RGB to YCrCb and display it. 
```
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
# Convert the HSV image back to RGB and display it.
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
```
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

```
# Convert BGR to RGB for displaying with Matplotlib
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
# Resize the original image to half its size and display it.

```
image = cv2.imread('TK.JPG')
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

# Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

```
image = cv2.imread('TK.JPG')
image.shape
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

# Flip the image vertically (up-down)
```
flipped_vertically = cv2.flip(image, 0)
```
# Convert BGR to RGB for displaying with Matplotlib

```
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
## Output:
 # Read the image using OpenCV

<img width="526" height="311" alt="image" src="https://github.com/user-attachments/assets/9db8527a-f671-488b-89d2-43dace255a31" />



2.  Draw a line from top-left to bottom-right


   
<img width="505" height="300" alt="image" src="https://github.com/user-attachments/assets/e6d12998-66bb-4596-b23a-aeef5bbb86f9" />



3)Draw a circle at the center of the image.


<img width="510" height="305" alt="image" src="https://github.com/user-attachments/assets/f50de860-ed47-411d-86bd-2ecabf2ff12e" />



4)Draw a rectangle around  the whole image

<img width="489" height="298" alt="image" src="https://github.com/user-attachments/assets/1f2e50ce-dd47-4d4c-882f-3108fa7218b0" />



5)Add the text "OpenCV Drawing" at the top-left corner of the image.

<img width="491" height="305" alt="image" src="https://github.com/user-attachments/assets/ec259126-5aa0-4f63-ae0a-88dc97af2737" />


6)Convert the image from RGB to HSV and display it.

<img width="531" height="306" alt="image" src="https://github.com/user-attachments/assets/a43bf714-564b-4cef-83cd-734983a44ded" />


7) Convert the image from RGB to GRAY and display it. 


<img width="506" height="298" alt="image" src="https://github.com/user-attachments/assets/a98b965c-65e1-4d3e-a3cb-93df34719367" />



8) Convert the image from RGB to YCrCb and display it. 


<img width="484" height="299" alt="image" src="https://github.com/user-attachments/assets/3696457b-aa03-4f27-8224-9a35a06c51d4" />


9)Convert the HSV image back to RGB and display it.

<img width="534" height="308" alt="image" src="https://github.com/user-attachments/assets/b6b6eee1-0781-46ec-bcd5-e2aa93759b08" />



10) Modify the color of the pixel at (300, 300) to white.


<img width="520" height="294" alt="image" src="https://github.com/user-attachments/assets/af1c5446-8920-49b1-bddb-0deb397dcea4" />

11)  Resize the original image to half its size and display it.
    
<img width="487" height="380" alt="image" src="https://github.com/user-attachments/assets/7550508c-44b3-4857-bd36-7d4ed0d88bc2" />


12)Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.




<img width="391" height="386" alt="image" src="https://github.com/user-attachments/assets/93fa7c1b-4290-49ee-8db2-1915dbb6cee2" />


13) Flip the original image horizontally and display it.

<img width="525" height="294" alt="image" src="https://github.com/user-attachments/assets/2c231ade-fbaa-4355-984f-dfc3e59b245c" />


14) Flip the original image vertically and display it.

<img width="516" height="312" alt="image" src="https://github.com/user-attachments/assets/3e1e6cc2-3d30-4375-86c1-91f94f92d434" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
