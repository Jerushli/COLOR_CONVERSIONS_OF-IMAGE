#                     COLOR_CONVERSIONS_OF-IMAGE
## EX NO: 01
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
image=cv2.imread('jero.JPG',1)
cv2.imshow('Jerushlin',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-04-10 111617](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/489dc6d4-5bed-46c6-81c3-4bdf866f183c)


### ii) Resized Image
```

image=cv2.resize(image,(350,350))
cv2.imshow('Jerushlin',image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![Screenshot 2024-04-10 111820](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/975061b5-506f-4781-bf5c-b3dbef9fea73)


### iii)Write the image
```
import cv2
image=cv2.imread('jero.JPG',0)
cv2.imwrite('Jerushlin.jpg',image)
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/35da421c-e1c1-4149-92f1-4c7de4a63e7d)

### iv)Shape of the Image
```
import cv2
image=cv2.imread('jero.JPG',1)
print(image.shape)
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/3b37951e-0d92-4520-b7c3-55024c23ebf9)


### v)Access rows and columns
```
import random
import cv2
image=cv2.imread('jero.JPG',1)
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
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/ddab8044-61c2-4fbd-bea3-34114ed63ab0)

### vi)Cut and paste portion of image
```
import cv2
image=cv2.imread('jero.JPG',1)
image=cv2.resize(image,(350,350))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/6cb8533e-7bd2-4b90-96da-a1fbf41cec09)

### vii) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('jero.JPG',1)
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
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/56d59916-cdac-432f-87c1-b23fa82a7b6d)
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/b5d19e22-02b1-4de8-b5bc-c7114032aa73)



### viii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('jero.JPG')
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
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/ed1abadf-c1e7-44c6-8f5c-940fb06b0ed8)
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/9abfd42f-1d8a-45bb-84aa-3f00c9b3d938)


### ix) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('jero.JPG')
img = cv2.resize(img,(350,350))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/1745d68d-84d6-41aa-8faa-3dcfcebc7c61)
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/3e9eae20-6f82-4bb4-ad5f-a9a7eac72b45)

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
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/ddce64c7-8d35-406f-b990-015447f3b82b)


### xi) Split and merge HSV Image
```
import cv2
img = cv2.imread("jero.JPG",1)
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
![image](https://github.com/Jerushli/COLOR_CONVERSIONS_OF-IMAGE/assets/120041243/f1118731-12e0-4e84-be27-b3bd25f4c213)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







