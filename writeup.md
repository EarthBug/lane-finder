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
[image2]: ./examples/blurred.jpg "Blurred"
[image3]: ./examples/canny.jpg "Canny"
[image4]: ./examples/hough.jpg "Hough"
[image5]: ./examples/hough_over.jpg "HoughOverlay"

---

### Reflection

### 1.Pipeline Description

My pipeline consisted of 5 steps.
First, I converted the images to grayscale.
![grayscale][image1]
Then I gaussian blurred the grayscale to smooth the image.
![blurred][image2]
This is to remove noise, the blurred image is fed to the canny edge detector.
Canny edge detector gives a list of points that make up the edges.
![canny][image3]
These points translate to lines when fed to Hough transform. The lines passing through one cell of a grid can be approximated to a line in the original space
![hough][image4]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by seperating left and right lanes, Finding a single line approximating the edges and displaying it with a higher thickness
![hough_overlay][image5]


### 2. Potential shortcomings with my current pipeline


One potential shortcoming would be what would happen when highly curved lane markings are present. The prse

Another shortcoming is not being able to use color information


### 3. Possible improvements to your pipeline

One improvement is to convert the image to HSV and isolate late using color range.
We can also skip frames and use previous frame data when lanes are tough to detect