# **Finding Lane Lines on the Road** 

## In this project I detected lane lines in images using Python and OpenCV

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on my work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidWhiteRight.jpg "Original"
[image2]: ./test_images_output/intermediate_stages/solidWhiteRight.jpg_gray_image.jpg "Grayscale"
[image3]: ./test_images_output/intermediate_stages/solidWhiteRight.jpg_blur_image "Blurred"
[image4]: ./test_images_output/intermediate_stages/solidWhiteRight.jpg_canny_image "Canny"
[image5]: ./test_images_output/intermediate_stages/solidWhiteRight.jpg_hough_image.jpg "Hough"
[image6]: ./test_images_output/intermediate_stages/solidWhiteRight.jpg_masked_image "Masked"
[image7]: ./test_images_output/solidWhiteRight.jpg "Result"

---

### Reflection

### My pipeline consisted of following 6 steps

![alt text][image1]

## 1. The image is converted to grayscale


## 2. The grayscale image is blurred

![alt text][image3]

## 3. Edge detection on blurred image with an Canny edge detector (algorithm to detect a wide range of edges in images)

![alt text][image4]

## 4. Feature extraction with the Hough transformation


## 5. Only the interesting image section is taken into account (via masking)


## 6. Adding lines to the original image 

![alt text][image7]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by separating line segments by their 
slope to decide which segments are part of the left line vs. the right line. These lines are also seperated by their Points. Then I use np.polyfit 
to fit a line to these points. A straight line is represented with y = mx + b which is a polynomial of degree 1. 


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there's a road with no median strip. 
Or a continuous median strip (for overtaking manoeuvres). The weather and light is another factor.

Another shortcoming could be dirtings that look like lanes.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to filter by color in the first steps (white and/or yellow).

Another potential improvement could be to examine which other algorithms are available for e.g edge detection.
Perhaps the results are better.
