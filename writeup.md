### **Finding Lane Lines on the Road** 

## Writeup

The purpose of this project is to take in a video stream and add lines to it that corresponds to the lines on the road

## Reflection

#### 1. The pipeline

The original image:
![grayscale](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/original.jpg =250x)

1. I convert the image to grayscale
![grayscale](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/grayscale.jpg =250x)
2. Blur the image using guassian blur.  This removes impurities that impeads edge detection.
![blurred](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/blurred.jpg =250x)
3. Apply canny edge detection to the image.  This finds all the hard edges in the images.
![canny](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/canny.jpg =250x)
4. Limit the image to the are that I'm interested in.
![cropped](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/cropped.jpg =250x)
5. Find the Hough Lines of the image.
![lined](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/lined.jpg =250x)
6. Remove the Hough Lines that are sloped incorrectly, and find two lines that best approximates the Hough Lines. The longer the Hough Line, the higher weight it carries in the approximation.
7. Apply the two fitting lines to the original image
![final](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/final.jpg =250x)

#### 2. Shortcomings
There are multiple glaring shortcomings, which include:
* If the dashed lines are too far apart, it doesn't work.
* The curb can sometimes be registered as a line.
* If the image isn't centered correctly, the cropped region is incorrect.
* If the contrast between the line and the road isn't enough, then it doesn't pick up a line.
* A curved line is approximated with a straight line (obviously not ideal).

#### 3. Possible Improvements
* Fiddle with the Canny Edge and Hough Line constants.
* Find a better way to approximate a fitted line from the Hough Lines (like least sqaures).
* Dynamically adjust the area of concern.
* Do not allow a drastic change from one frame to the next.
