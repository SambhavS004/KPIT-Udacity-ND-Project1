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

1: Converting the image to Grayscale

2: Applying Gaussian Smoothing, setting up the Kernel Size

3: Performing Canny Edge Detection on the result of Gaussian Smoothing alongwith the parameters of low_threshold and high_threshold

4: Creating the Region of Interest, putting it into vertices by adjusting the coordinates

5: Applying the Hough Transform

6: Averaging and Extrapolating the lines and applying them to the original image.

### In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

1: first seperating the line segments on the basis of their slope, if slope falls on the negative part then taking it into left array and if on positive then taking it into right array. This is because we have y coordinate is reversed, otherwise the left lane should have positive slope and the right should have negative slope.

2: Creating the coordinates using the array the that we got in previous step

3: Then have calculated the average of the positions for these coordinates

4: Extrapolated the coordinates on the left lane and feeded then into cv2.line as parameters.

5: Same process for the right lane

### 2. Identify potential shortcomings with your current pipeline

1: Lines are getting distorted when curve is coming in the Lane.

2: I was getting a distorted output using intercept in the draw_line() function. The lines were getting close to each other at some point in the video.

### 3. Suggest possible improvements to your pipeline

1: Hough Transform parameter can be adjusted. 

2: draw_line() function can be implemented using the intercept approach where we can find the intercept of y axis and on the basis of slope that intercept value can be added to the intecept Left and Right value. However it didn't worked for me.
