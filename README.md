## Vision pipeline approach

- Grab the image.
- Apply Gaussian blur filter
- Apply Canny edge detection filter
- Apply the region of interest
- Apply Hough transform
- Using numpy polyfit to find the (y = Ax + B) A and B co-efficient
- Calculate the gradient of each line, to identify left or right lane line points
- Filter gradient value that is greater than 60 degree and less than 30 degree
- Calculate the X1 and X2 points by using (x = (y-B)/A) equation
- Append the points into the list
- Find the mean value of X1 and X2 using numpy.mean

#### When using with video feed
- Apply Complimentary filter to left and right lane points (x = A * cur_x + B * x) where A = 0.01 and B = 0.99
- Use previous points as high pass and current points as low pass
- Draw the lines using the filter points

#### Lastly
- Display the image

## Identify any shortcomings
Environment lighting changes may cause edge detection unable to detect lane marking. When applying the complimentary filter, a lower A coefficient may reduce the responsiveness of the tracking.

## Suggest possible improvements

In the video test, when the edge detection unable to detect the lane marking, tracking discontinuity may arise. By using complimentary filter, it able to filter out temporary noise. Advance filter such as kalman filter or particle filter may improve the reliability of the tracking.

