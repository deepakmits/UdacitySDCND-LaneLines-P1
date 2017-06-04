# **Finding Lane Lines on the Road** 

## Pipeline for lane line identification - 
### Step 1: Read Image.
### Step 2: Convert read image to grayscale using helper function.
[image1]: ./examples/greyed_solidWhiteCurve.jpg "greyed_solidWhiteCurve"
### Step 3: Apply gaussian blur to greyed image using helper function.
[image2]: ./examples/blurred_solidWhiteCurve.jpg "blurred_solidWhiteCurve"
### Step 4: Apply canny edge detection to blurred image using helper function.
[image3]: ./examples/canny_solidWhiteCurve.jpg "canny_solidWhiteCurve"
### Step 5: Mask region of interest on canny edges detected image using vertices and helper function.
[image4]: ./examples/masked_solidWhiteCurve.jpg "masked_solidWhiteCurve"
### Step 6: Apply hough line function on masked region with tuned hough transformation parameters.
[image5]: ./examples/lines_drawn_solidWhiteCurve.jpg "lines_drawn_solidWhiteCurve"
### Step 7: Blend image with hough lines with the initial image using weighted_img given helper function.
[image5]: ./examples/output_solidWhiteCurve.jpg "output_solidWhiteCurve"

Applied above steps on all the given test images and got transformed all the images.

### To draw a single line on left and right lanes, draw_lines() function was modified as below -
1) Loop thru all the line segments and calculate slope using (y2-y1)/(x2-x1).
2) Based on slope values segments are grouped in left(slope < 0) and right lanes(slope > 0).
3) Keep taking averages of x and y coordinates and keep drawing lines.
4) Adjust thickness of line by changing thickness parameter to 8.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Potential shortcomings with your current pipeline


One potential shortcoming would be when position of lane lines in in an image is very different from the given test images/videos. Then this pipeline would not work as expected.




### 3. Possible improvements

draw_lines() function can be improved to get best fit line using all the coordinates of all the segments of left or right group.
