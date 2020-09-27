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

My pipeline consisted of 5 steps. Steps will be explained below. 

* Color image is converted to grayscale image.
* Gaussian smoothing witht the kernel size of 3, before running canny (way of suppressing noise and spurious gradients by averaging).
* Obtaining edges by using cv2.Canny() with 80 , 250 being low and high thresholds.
* As it can be seen Lanes in the images are in the specific area. So I use hardcoded trapezoid region to mask out the region of interest. 
* Finally, using Hough transform to detect lines from the Canny edges. 

`Hardcoded values are experimented and optimized according to the obtained results`

This pipeline is ran on the test images and below images are the outputs. 


<img src="./test_images_output/Red/solidWhiteCurve_test_output.jpg" width="250"/> <img src="./test_images_output/Red/solidWhiteRight_test_output.jpg" width="250"/> 

<table>
  <tr>
    <td>solidWhiteCurve</td>
     <td>solidWhiteRight</td>
     <td>solidYellowCurve</td>
  </tr>
  <tr>
    <td><img src="./test_images_output/Red/solidWhiteCurve_test_output.jpg" width=250 ></td>
    <td><img src="./test_images_output/Red/solidWhiteRight_test_output.jpg" width=250 ></td>
    <td><img src="./test_images_output/Red/solidYellowCurve_test_output.jpg" width=250 ></td>
  </tr>
 </table>
 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
