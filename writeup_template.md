# **Finding Lane Lines on the Road** 

## Writeup Template

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describing the pipeline. The draw_lines() function.

My pipeline consisted of below steps.
#Converting the image to Grayscale
#Applying Gaussian Smoothing, setting up the Kernel Size
#Performing Canny Edge Detection on the result of Gaussian Smoothing alongwith the parameters of low_threshold and high_threshold
#Creating the Region of Interest, putting it into vertices by adjusting the coordinates
#Applying the Hough Transform
#Averaging and Extrapolating the lines and applying them to the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...
#first seperating the line segments on the basis of their slope, negative slope for right lane and positive for the left lane
#Creating the coordinates using the array the that we got in previous step
#Then have calculated the average of the positions for the lines for the coordinates

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
