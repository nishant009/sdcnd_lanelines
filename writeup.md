# **Finding Lane Lines on the Road**
---

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

[//]: # (Image References)

[image1]: ./writeup_images/grayscale.jpg "Grayscale"
[image2]: ./writeup_images/solidWhiteCurve.jpg "No Extrapolation"
[image3]: ./writeup_images/solidWhiteCurveEx.jpg "Extrapolation"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps:
1. Convert the image to grayscale
![alt text][image1]
2. Run Gaussian blur on grayed image to remove noisy pixels.
3. Run Canny edge detection on the smoothed image.
4. Define a region of interest and mask edges outside this region.
5. Use Hough transform to detect strong edges and draw lines to connect them.
6. Superimpose the image with lines drawn on the original image.

This is what the output of this pipeline looked like:
![alt text][image2]

In order to draw a single line on the left and right lanes, I modified then draw_lines() function to do the following:
1. For each line detected by Hough transform, calculate the slope of that line.
2. Separate points to be on the right or left based on the sign of the slope. Positive slope means points belong to the right side and negative means to the left.
3. Find the slope and intercept of the extrapolated line for the right and left side by using polynomial regression.
4. Calculate top and bottom x co-ordinates for right and left side by using the slopes and intercepts found in step 3 and bounding box y co-ordinates used in region of interest selection.
5. Draw the extrapolated lines on right and left.

This is what the output of extrapolation looked like:
![alt text][image3]

I then applied this pipeline to each frame in videos to generate the video output.

### 2. Identify potential shortcomings with your current pipeline

1. Smaller line segments cause a break in the extrapolated lines.
2. Lane detection will go awry if the car is for example changing lanes.
3. If there are objects other than lane lines inside the region of interest they might cause erroneous lines to be drawn.


### 3. Suggest possible improvements to your pipeline

1. Dynamically learn and adjust the bounds of the region of interest.
2. Differentiate between lane lines in the region of interest and line segments detected due objects other than lane lines present in the region of interest.
