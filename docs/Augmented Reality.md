# Augmented Reality (AR) in Python


**AR(Augmented Reality) is a system that combines the real and virtual worlds.** Have you ever played "Pokemon Go"? If you are not aware of the game, the player has to turn on the camera and roam around places to find a 3D pokemon placed somewhere randomly in the virtual-real world on the console of the app. The player with the highest collection of pokemons wins. **The concept that the player is able to see a virtual cartoon character in the real world in the game is AR(Augmented Reality).**

The game uses location tracking and geographical mapping and runs on AR technology. It creates a view of virtual objects in the real world**. There is another technology called "Virtual Reality". AR and VR are not the same**. Virtual reality is "virtual world made real" but Augmented reality is combining virtual objects with the real world. *VR is about 75 percent virtual but AR is only 25 percent virtual*.

The difference between AR and VR can be well understood with examples. Playing games with VR headset makes the player involve in a virtual world while playing AR games involves virtual world into real world locations.

**There are two major goals for AR technology:** 

1.  Real-time interaction
2.  Accurate 3D representation of real and virtual objects.

This tutorial gives a brief idea of AR using the OpenCV library in Python. Using the available functionality in Python, we'll try to implement some interesting AR ideas.

## **How does a Computer Read an Image?**

A computer doesn't have the capability of recognizing images by its own. An image is a collection of pixels or picture elements. When we say "*My TV's resolution is 1080p*", we mean that the height\*width ratio of the screen is 3840\*2160 which means, the TV screen has over 8 million pixels. A pixel is like a small dot measuring about 0.26mm or 1/96 of an inch (varies). The computer can only recognize numbers. Hence, every pixel is represented using different color models. Most commonly used color models are **RGB (Red green blue) and CMYK (Cyan Magenta Yellow Black)**.

## **RGB model:**

1.  To represent a **black and white image**, each pixel is given a single number that represents the amount of light (contrast). The number ranges from 0 to 255. 0 represents no light (**black**) and 255 represents full light (**white**) and the numbers in the interval represent **various shades of grey.**
2.  To represent a **color image** in RGB model, every pixel is given **3 values** each representing the amount of Red, green and blue colors in the pixel respectively.

## ![Augmented Reality (AR) in Python](https://images.javatpoint.com/python/images/augmented-reality-in-python.png)
## Processing Images with OpenCV library

In the vast libraries of Python, OpenCV is one of the notable ones. It is a huge open source library that is used a lot for **computer vision, machine learning applications**. Using this library, we can process images and even videos. To process an image, **every pixel is stored as a tuple of (B, G, R) values.**

There are various functions in OpenCV for processing images. Here are some basic functions:

```py
**import** cv2  
pic = cv2.imread(r"C:\\Users\\Jeevani\\Desktop\\6946b76fed14793869229898fc827e43.png")```  
 
 ### Displaying the image  
 
```py
print ('The picture we\\'re working on:')  
cv2.imshow('Multiverse spidey', pic)  
cv2.waitKey(0)```
  
### Get image size and color model  
 
```py
dim = pic.shape  
print('\\nHeight: {}'.format(dim\[0\]))  
print('Width: {}'.format(dim\[1\]))  
print('Number of channels: {}'.format(dim\[2\]))```
    
### BGR intensities in a pixel 
```py
(blue, green, red) = pic\[599, 499\]  
**print**("\\nNo-of blue channels:", blue)  
**print**("No-of green channels:", green)  
**print**("No-of red channels:", red)```
   
### Focusing on a region in the picture
    
```py
**print**('\\nSelecting a region in the image:')  
region = pic\[200: 600, 300 : 600\]  
cv2.imshow('Multiverse spidey', region)  
cv2.waitKey(0)``` 
  
### Resizing the image 
      
```py
**print**("\\nResizing the image to half by maintaining the aspect ratio:")  
ratio = 50  
h = int(dim\[0\]\*ratio/100)  
w = int(dim\[1\]\*ratio/100)  
size = (h,w)  
crop = cv2.resize(pic, size)  
cv2.imshow('Multiverse spidey', crop)  
cv2.waitKey(0)``` 
  
### Rotating the image
       
```py
**print**("\\nRotating the image by 60 degree clockwise:")  
h = int(dim\[0\])  
w = int(dim\[1\])  
center = (h//2, w//2)  
mat = cv2.getRotationMatrix2D(center, -60, 1)  
ro\_pic = cv2.warpAffine(pic, mat, (h, w))  
cv2.imshow('Multiverse spidey', ro\_pic)  
cv2.waitKey(0)``` 

**Output:**

The picture we're working on:



Height: 621
Width: 500
Number of channels: 3

No-of blue channels: 12
No-of green channels: 12
No-of red channels: 12

