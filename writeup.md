# **Finding Lane Lines on the Road** 

## When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

## In this project you will detect lane lines in images using Python and OpenCV. OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.



---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./images/selected_image.jpg "selected_image"
[image2]: ./images/gray.jpg "gray"
[image3]: ./images/blur_gray.jpg "blur_gray"
[image4]: ./images/edges.jpg "edges"
[image5]: ./images/masked_edges.jpg "masked_edges"
[image6]: ./images/line_image.jpg "line_image"
[image7]: ./images/com_image.jpg "com_image"

---

### Reflection

### 1. Description of pipeline. 

My pipeline consisted of 7 steps. 
	1)try to use color selection to select white and yellow.
	![alt test][image1]
	2)I converted the images to grayscale
	![alt test][image2]
	3)Use Gaussian smoothing to blur the gray image' noise 
	![alt test][image3]
	4)Use Cany transform to find the edges
	![alt test][image4]
	5)use a mask to get the ROI ,my mask is a polygon
	![alt test][image5]
	6)use Hough Transform to find lines and deaw a single line for each side
	![alt test][image6]	
	7)Draw the lines on the  image
	![alt test][image7]		
	
	

In order to draw a single line on the left and right lanes, my steps is :
	1)pick the lines with impossible slope
	2)calculate the weighted avarage of slope and intercept
	3)use the weighted avarage of slope and intercept to get the top and bottom point for each line and draw it


### 2. shortcomings 


If the road have different colors，or lane lines are too blurry，the algorithm can not work


### 3. Suggest possible improvements 

Maybe change the image to other color space will be helpful to pick the color of  lane line 
