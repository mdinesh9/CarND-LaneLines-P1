# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following five steps:

    1. Convert the image to grayscale
    2. Apply Gaussian Blur
    3. Apply Canny edge detection
    4. Apply Region Masking
    5. Apply Hough transformation
    6. Draw lines on the left and right lanes in front of the car


#### Convert the image to grayscale

I converted the image to grayscale image using opencv

    cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)

#### Apply Gaussian Blur

Applied gaussian blur with kernel size 3

    cv2.GaussianBlur(img, (3, 3), 0)

#### Apply Canny Edge Detection

Applied Canny edge detection with low and high thresholds = 75, 150

    cv2.Canny(img, low_threshold, high_threshold)

#### Apply Region Masking

Applied region masking to detect the region infront of the car

#### Apply Hough Transformation

Applied hough transformation. Here I experimented with multiple parameters to get smooth detection.

#### Draw lines

This was the most time consuming step. 

First I calculated average slope and based on the sign of the slope value, I determined whether the line falls on the left side or right side considering the axis (0,0) starts at the top right.

The I extrapolated the lines to join them as a single line in the output.



![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
