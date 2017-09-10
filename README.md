# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.


This project is forked from [udacity/CarND-LaneLines-P1](https://github.com/udacity/CarND-LaneLines-P1).


Creating a Great Writeup
---
For this project, a great writeup should provide a detailed response to the "Reflection" section of the [project rubric](https://review.udacity.com/#!/rubrics/322/view). There are three parts to the reflection:



1. Describe the pipeline
..* Grab the image
..* Apply Gaussian blur filter
..* Apply Canny edge detection filter
..* Apply the region of interest
..* Apply Hough transform
..* Using numpy polyfit to find the (y = Ax + B) A and B co-efficient
..* Calculate the gradient of each line, to identify left or right lane line points
..* Filter gradient value that is greater than 60 degree and less than 30 degree
..* Calculate the X1 and X2 points by using (x = (y-B)/A) equation
..* Append the points into the list
..* Find the mean value of X1 and X2 using numpy.mean

When using video feed
..* Apply Complimentary filter to left and right lane points (x = A * cur_x + B * x) where A = 0.01 and B = 0.99
..* Use previous points as high pass and current points as low pass
..* Draw the lines using the filter points

Lastly
..* Display the image

2. Identify any shortcomings
Environment lighting changes may cause edge detection unable to detect lane marking.

3. Suggest possible improvements
In the video test, when the edge detection unable to detect the lane marking, tracking discontinuity may arise. By using complimentary filter, it able to filter out temporary noise. Advance filter such as kalman filter or particle filter may improve the reliability of the tracking.

