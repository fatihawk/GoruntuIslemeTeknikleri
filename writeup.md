##Writeup Template
###You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---

**Advanced Lane Finding Project**

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

[//]: # (Image References)

[image1]: ./output_images/undistort_output.png "Undistorted"
[image2]: ./output_images/test1.png "Road Transformed"
[image3]: ./output_images/binary_combo_example.png "Binary Example"
[image4]: ./output_images/warped_straight_lines.png "Warp Example"
[image5]: ./output_images/color_fit_lines.png "Fit Visual"
[image6]: ./output_images/example_output.png "Output"

---
## [Rubric](https://review.udacity.com/#!/rubrics/571/view) Points

###Here I consider the rubric points individually and describe how I addressed each point in my implementation.  

---
###Writeup / README

####1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

You're reading it!
###Camera Calibration

####1. Briefly state how you computed the camera matrix and distortion coefficients. Provide an example of a distortion corrected calibration image.

A function `camcal()` is defined for this step is at lines 10 through 35 of the file called `lanelines.py`.  The function `camcal()` is called at line 469 of `lanelines.py`.

In `camcal()` I start by preparing "object points", which will be the (x, y, z) coordinates of the chessboard corners in the world. Here I am assuming the chessboard is fixed on the (x, y) plane at z=0, such that the object points are the same for each calibration image.  Thus, `objp` is just a replicated array of coordinates, and `objpts` will be appended with a copy of it every time I successfully detect all chessboard corners in a test image.  `imgpts` will be appended with the (x, y) pixel position of each of the corners in the image plane with each successful chessboard detection.  

I then used the output `objpts` and `imgpts` to compute the camera calibration and distortion coefficients using the `cv2.calibrateCamera()` function.  I applied this distortion correction to a test image using the `cv2.undistort()` function and obtained this result: 

![alt text][image1]

###Pipeline (single images)

####1. Provide an example of a distortion-corrected image.
The first step in the `process_image()` function (at line 477 in `lanelines.py`) is to apply distortion correction to the image before any further processing of the image. To demonstrate this step, I applied the distortion correction obtained from `camcal()` to this test image:

![alt text][image2]

####2. Describe how (and identify where in your code) you used color transforms, gradients or other methods to create a thresholded binary image.  Provide an example of a binary image result.
I used a combination of color and gradient thresholds to generate a binary image (thresholding steps in fuction `pipeline()` at lines 198 through 235 in `lanelines.py`).  Here's an example of my output for this step.

![alt text][image3]

####3. Describe how (and identify where in your code) you performed a perspective transform and provide an example of a transformed image.

The code for perspective transform includes 2 functions.  The first function, `warp()` appears in lines 193 through 196 in the file `lanelines.py`.  The `warp()` function takes as inputs an image (`img`) and a transformation matrix (`M`).  The transformation matrix (`M`) is generated using the second fuction, `warp_transforms()`, which appears in lines 174 through 191 in the file `lanelines.py`. The `warp_transforms()` function takes as arguments the source (`src_vertices`) and destination (`dst_vertices`) points.  I used the following hardcoded source and destination points.  I assumed an assumed input image size of (1280x720):

This resulted in the following source and destination points:

 | Source        | Destination   | 
 |:-------------:|:-------------:| 
 | 571, 461      | 250, 0        |
 | 709, 461      | 1030, 0       |
 | 1030, 660     | 1030, 660     |
 | 250, 660      | 250, 660      |

I verified that my perspective transform was working as expected by drawing the `src` and `dst` points onto a test image and its warped counterpart to verify that the lines appear parallel in the warped image.

![alt text][image4]

####4. Describe how (and identify where in your code) you identified lane-line pixels and fit their positions with a polynomial?

Then I implemented the `fitlines()` function at lines 270 through 437 in the file `lanelines.py` and used it to fit 2nd order polynomial lane lines to my data.  The function `fitlines()` first uses a histogram on the warped binary image to identify the starting point of the lane lines at the bottom of the image and then applies a sliding window search to follow the lane lines up to the top of the image, collecting the pixels that are determined to be part of a the lane lines as it goes.  Once the lane line pixels are identified the best fit polynomials are generated for the left and right lane lines.

The `fitlines()` function also implements a sanity check of fitted lines (at lines 372 through 383 in the file `lanelines.py`) that discards any fits if the radius of curvatures of the left and right lane lines aren't similar.

Here's an example of the result:

![alt text][image5]

####5. Describe how (and identify where in your code) you calculated the radius of curvature of the lane and the position of the vehicle with respect to center.

The fitted polynomials from the previous step are adjusted from pixels to meters for real world perspective and then used to calculate the radius of the curvature of the lines.  This is done at lines 369 through 370 in `lanelines.py`. The average of the left and right radii is used as the final result to approximate the radius at the center of the lane (line 519 in `lanelines.py`).

The generated polynomial lines for the left and light lanes are averaged to provide an estimate of the center line of the lane at the bottom of the image near the hood of the car. Then the position of the vehicle with respect to the lane center is calculated; this is implemented in lines 512 through 517 in the file `lanelines.py`.

####6. Provide an example image of your result plotted back down onto the road such that the lane area is identified clearly.

I implemented this step in lines 439 through 452 in my code in `lanelines.py` in the function `draw_lane()`.  This includes augmentation of the image with text showing the radius of curvature and the deviation of the vehicle from the center of the lane. Here is an example of my result on a test image:

![alt text][image6]

---

###Pipeline (video)

####1. Provide a link to your final video output.  Your pipeline should perform reasonably well on the entire project video (wobbly lines are ok but no catastrophic failures that would cause the car to drive off the road!).

Here's a [link to my video result](./output_video.mp4)

---

###Discussion

####1. Briefly discuss any problems / issues you faced in your implementation of this project.  Where will your pipeline likely fail?  What could you do to make it more robust?

The biggest challenge in this project was creating a pipeline that yielded an acceptable result. It took a lot of trial and error to find a combination of color channels (from RGB, HLS, HSV), thresholds and gradients that extracted good lane line information under different conditions without providing bad information in other conditions. Some of my initial choices worked well for some conditions but introduced bad information in other conditions. The goal is to provide good information when it exists but otherwise provide null info, allowing other filters to provide good lane data.

Even with a good pipeline there are often brief transients where some artifact in an image causes a bad lane line detection. I didn't implement it for this project but it's clear that additional line filtering is required that discards transient outlier detections.

The lane line jitter that was pronounced in project 1 was much less in this implementation but still present. It would be wise to implement some kind of averaging or smoothing function on the detected lines that incorporate good detections from the last few frames.   

The challenge videos were indeed challenging and there is much work to do before the pipeline will be work effectively in the most adverse conditions that real cars will face.  
