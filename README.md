# EXPERIMENT 07: EDGE DETECTION
## AIM:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### STEP 1:
Import the required packages for further process.
### STEP 2:
Read the image and convert the bgr image to gray scale image.
### STEP 3:
Use any filters for smoothing the image to reduse the noise.
### STEP 4:
Apply the respective filters -Sobel,Laplacian edge dectector and Canny edge dector.
### STEP 5:
Display the filtered image using plot and imshow.

## PROGRAM

Import the packages:
```
import cv2
import matplotlib.pyplot as plt
```
Load the image, Convert to grayscale and remove noise:
```
image = cv2.imread("car.jpg")
plt.imshow(image)
gray_image = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
new_image = cv2.GaussianBlur(gray_image,(3,3),0)
````
Sobel Edge Detector:
```
sobelx = cv2.Sobel(new_image,cv2.CV_64F,1,0,ksize = 5)
plt.figure(figsize=(8,8))
plt.imshow(sobelx)
plt.title("SOBEL_X")
plt.xticks([])
plt.yticks([])
plt.show()
sobely = cv2.Sobel(new_image,cv2.CV_64F,0,1,ksize = 5)
plt.figure(figsize = (8,8))
plt.imshow(sobely)
plt.title("SOBEL_Y")
plt.xticks([])
plt.yticks([])
plt.show()
sobelxy = cv2.Sobel(new_image,cv2.CV_64F,1,1,ksize=5)
plt.figure(figsize = (8,8))
plt.imshow(sobelxy)
plt.title("SOBEL_XY")
plt.xticks([])
plt.yticks([])
plt.show()
```
Laplacian Edge Detector:
```
laplacian = cv2.Laplacian(new_image,cv2.CV_64F)
plt.figure(figsize = (8,8))
plt.subplot(1,2,1)
plt.imshow(new_image,cmap = 'bone')
plt.title('bone')
plt.subplot(1,2,2)
plt.imshow(laplacian,cmap = 'bone')
plt.title('Laplacian')
plt.xticks([])
plt.yticks([])
plt.show()
```
Canny Edge Detector:
```
canny_edges = cv2.Canny(new_image, 120, 150)
plt.figure(figsize = (8,8))
plt.imshow(canny_edges)
plt.title('CANNY_EDGES')
plt.axis("off")
plt.show()
```
## OUTPUT:
### ORIGINAL IMAGE:
![image](https://user-images.githubusercontent.com/93427256/232289108-dd6d4024-bdab-425d-89fc-1ca0c086c324.png)

### SOBEL EDGE DETECTOR:  
* SOBEL X:  
![image](https://user-images.githubusercontent.com/93427256/232289123-857bc37f-2ea9-47d0-80c3-f6dba8ef0b0b.png)
* SOBEL Y:  
![image](https://user-images.githubusercontent.com/93427256/232289135-056c0834-3da3-438a-9b14-b0ee1ef0e274.png)
* SOBEL XY:  
![image](https://user-images.githubusercontent.com/93427256/232289149-b3066883-d399-42d8-813d-92223fa73edb.png)

### LAPLACIAN EDGE DETECTOR:  
![image](https://user-images.githubusercontent.com/93427256/232289156-5748eb71-63f2-4a64-a3d8-c328784235a6.png)

### CANNY EDGE DETECTOR:  
![image](https://user-images.githubusercontent.com/93427256/232289168-adc9190b-a881-465f-a36e-b66cd61d8bf3.png)


## RESULT:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
