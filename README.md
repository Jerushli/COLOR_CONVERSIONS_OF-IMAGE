# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:JERUSHLIN JOSE JB
### Register Number: 212222240039


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('dipimage.jpg',1)
cv2.imshow('Jerushlin',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/7e40e7dd-3371-4dcc-9f57-e09b9fde3351)


### ii) Resized Image
```

image=cv2.resize(image,(350,350))
cv2.imshow('Jerushlin',image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/0f7bb005-905c-448b-80e6-008d2d054a91)




### iii)Write the image
```
import cv2
image=cv2.imread('dipimage.jpg',0)
cv2.imwrite('Jerushlin.jpg',image)
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/7c390c6a-67ae-48cd-b4e7-5238c1496820)


### iv)Shape of the Image
```
import cv2
image=cv2.imread('dipimage.jpg',1)
print(image.shape)
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/5ff9de19-5efc-48b8-8312-1747704e42c3)


### v)Access rows and columns
```
import random
import cv2
image=cv2.imread('dipimage.jpg',1)
image=cv2.resize(image,(350,350))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,555),
                    random.randint(0,555),
                    random.randint(0,555)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/3062def4-954a-4da6-bec1-2ede7d540166)



### vi)Cut and paste portion of image
```
import cv2
image=cv2.imread('dipimage.jpg',1)
image=cv2.resize(image,(350,350))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/bd63523f-27a2-4f01-9526-abf0d38ecd2f)


### vii) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('dipimage.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/4be241cd-8154-4c2d-a3bb-e3d0f1c3e5ae)
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/c99f2daf-23b3-4afd-ab2d-2fc35b186a1b)


### viii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dipimage.jpg')
img = cv2.resize(img,(350,350))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/2e43876d-025c-496d-9ff0-85cfefb26878)


### ix) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dipimage.jpg')
img = cv2.resize(img,(350,350))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/413b4883-0a34-4d75-837e-3dce3667209c)



### x) Split and merge RGB Image
```
import cv2
img = cv2.imread('dipimage.jpg',1)
img = cv2.resize(img,(370,370))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/58da1bbe-135b-43fc-9022-048098711c7d)



### xi) Split and merge HSV Image
```
import cv2
img = cv2.imread("dipimage.jpg",1)
img = cv2.resize(img,(370,370))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/24879c98-e306-478d-9ae8-819d1acf8ad2)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







