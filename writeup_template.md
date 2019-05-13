# **Finding Lane Lines on the Road** 

---

**Goals / Steps**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Build a pipeline using color selection, region masks, canny edge detection and hough space transformation
* Draw a solid lane line on the left and right lane of the ego car 


### Reflection

### 1. Pipeline description.

My pipeline consisted of 6 step:

* colorPipe: First I converted RGB image to HLS color space so that color filters can be applied more easily. Mask 1 was used for picking up white objects in the image. Mask 2 was used for picking up yellow objects. A combined mask was used for picking up white and yellow lane lines. This stage of the pipeline was helpful in picking up lane lines on low contrast concrete surface in the challenge video.

[//]: # (Image References)

[image1]: ./examples/colorPipe.png "Challenge Video Snapshot"

![alt text][image1]

[//]: # (Image References)

[image2]: ./examples/challengeSnap2.jpg "Challenge Video Snapshot"

![alt text][image2]
---

* A wrapper function was used for each stage of the pipeline so that jupyter's 'interact' module can be used for parameter tuning.

[//]: # (Image References)

[image3]: ./examples/interactiveTuning.png "Interactive Tuning"

![alt text][image3]
---

* cannyPipe: Canny edge detection was used to detect edges of the yellow and white lane lines.
* regionPipe: A trapezoidal ROI was used to filter out the canny edges that correspond to lane lines for ego vehicle.
* houghPipe: Hough transform was used to pickup straight line edges of the left and right lanes.

* In order to draw a single line on the left and right lanes, I added a filtering function to filter out the line segments obtained from houghLinesP function in draw_lines() function. Lines on the left half of the image with -0.5 to -0.8 were segregated and averaged out to get the lane line on the left. Lines on the right half of the image with 0.5 to 0.8 were segregated and averaged out to get to get the lane line on the right.

[//]: # (Image References)

[image4]: ./examples/challengeVideoOutput.png "Sample Output"

![alt text][image4]
---


### 2. Potential shortcomings with the current pipeline


The potential shortcomings for the pipeline are:
* The lane line detections jitters a lot when the dashed line disappear at the left and right of the image. The jumps are more pronounced when the road curves to the left or right.
* The pipeline has not been tested with vehicles at the front of ego vehicle.
* The pipeline has not been tested with night time driving videos.
* The pipeline may not work if there are markings on the road (like stop sign)


### 3. Possible improvements to pipeline

A possible improvement would be to use hough transform that can follow the road curvature

Another potential improvement could be to use more bit depth for the images to detect edges more accurately.
