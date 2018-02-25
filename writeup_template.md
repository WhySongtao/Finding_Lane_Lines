# **Finding Lane Lines on the Road** 


---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./test_images_output/graysolidWhiteCurve.jpg "Grayscale"
[image3]: ./test_images_output/blursolidWhiteCurve.jpg "GaussianBlur"
[image4]: ./test_images_output/cannysolidWhiteCurve.jpg "Canny"
[image5]: ./test_images_output/maskedsolidWhiteCurve.jpg "MaskedLine"
[image6]: ./test_images_output/Hough_linesolidWhiteCurve.jpg "HoughLine"
[image7]: ./test_images_output/solidWhiteCurve.jpg "FinalPic"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of 5 steps. 
First, I converted the image to grayscale because cv2.Canny() only takes 8 bit image as input. 
![alt text][image2]
Second, I applied guassian filter on the image to smooth any noise points. 
![alt text][image3]
Third, I applied canny function to find out all the edge in the picture. 
![alt text][image4]
Fourth, because lane lines will only appear in certain area, I masked the original image to find out only the edge of the lane line. 
![alt text][image5]
Fifth, in order to draw lines on the image, I used hough transform function to find out lines in the image. 
![alt text][image6]
Sixth, I combined the line image with original image.


In order to draw a single line on the left and right lanes, I modified the draw_lines() function.
I have learnt that a point and a slope can define a line. Also, I can use the sign of the slope to differentiate left and right lane. So firstly I compute the centre point and the average slope for left and right lane. After that, I can find the top and bottom points for both lanes by using the formula: (y - y') = M(x - x')
![alt text][image7]



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are other edges appearing on the road. This is mess up the centre point and the slope, causing the lane line marker to be in the wrong position.  

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
