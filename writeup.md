

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I run canny edge detection in OpenCV. The next step was probabilistic Hough lines in OpenCV to identify the location of lane lines on the road. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by slope and reject outliers that throw off the intended slope of the line.Positive slopes are the right lane and negative slopes are the left lane in OpenCV. 

The last step is extending Hough lines into a single unified lane line. I've done it in a few substeps: 

    Line outliers were removed (e.g flat lines or lines that deviate significantly from the man)
    Lines were merged by the mean of their endpoints. 
    Endpoints were extended off the image canvas. 

In the last section, I added a few optional steps. First, I created a color mask that highlighted the whites and yellows in the frame. This  ensured our Hough lines are more easily detected in shaded regions or low contrast regions. 