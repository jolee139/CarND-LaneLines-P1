**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

In order to identify the lines on the images, I first converted the images to grayscale, then reduced image details by using Gausssian blur. The next step was to use Canny to detect edges on image and defined the region of interest. And lastly, Hough line was used to find the lines on the road. 

I calculated the slope of each line to decide if the line was either on the right or left side of the image. 

And, with all the calculated slopes and center coordinates, I was able to find the bottom and top points of each line and drew the extended lines on the road.


###2. Identify potential shortcomings with your current pipeline

One of the shortcomings can be the region of interest because if the lanes on image did not fit in the region, then the unexpected result might be produced.

Another shortcoming is the length of the extended line, if the lane curve is steep, then the pipeline might be too long.


###3. Suggest possible improvements to your pipeline

Should find the region of interest dynamically by removing meaningless edges from the image and fine the region near by the lanes.

Also, find the top coordinates of the lanes so that the pipeline does not go over the top points.
