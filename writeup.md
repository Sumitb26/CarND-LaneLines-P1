

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps:
1. I converted the images to grayscale
2. Reduced image noise by using gaussian blur
3. Used canny transformation to find edges in blurred image
4. Focus on interested areas of the image using fillPoly
5. Use hough transform to find lines on the region of interest
6. Merge output of hough transform with original image to show lane lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by finding left and right lane lines by comparing the slopes. Each point of those sides were accumulated and first degree polynomial was fit to those points using np.polyfit.

### 2. Identify potential shortcomings with your current pipeline


1. Lines are not entirely on lane lines at the end
2. Lines shake a bit from their required position sometimes


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to adjust parameters of hough transform to fix the problems listed above.
