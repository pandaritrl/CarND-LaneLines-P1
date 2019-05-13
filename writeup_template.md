# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Build a pipeline using color selection, region masks, canny edge detection and hough space transformation
* Draw a solid lane line on the left and right lane of the ego car 


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Pipeline description.

My pipeline consisted of 6 steps. 
* First I converted RGB image to HLS color space so that color filters can be applied more easily. Mask 1 was used for picking up white objects in the image. Mask 2 was used for picking up yellow objects. A combined mask was used for picking up white and yellow lane lines. This stage of the pipeline was helpful in picking up lane lines on low contrast concrete surface in the challenge video.

[//]: # (Image References)

[image1]: ./examples/challengeSnap2.jpg "Challenge Video Snapshot"

First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
