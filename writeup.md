### **Finding Lane Lines on the Road** 

## Writeup

The purpose of this project is to take in a video stream and add lines to it that corresponds to the lines on the road

---

## Reflection

#### 1. The pipeline

The original image:

1. I convert the image to grayscale
![grayscale](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/grayscale.jpg)
2. Blur the image using guassian blur.  This removes impurities that impeads edge detection.
![blurred](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/blurred.jpg)
3. Apply canny edge detection to the image.  This finds all the hard edges in the images.
![canny](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/canny.jpg)
4. Limit the image to the are that I'm interested in.
![cropped](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/cropped.jpg)
5. Find the Hough Lines of the image.
![lined](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/lined.jpg)
6. Remove the Hough Lines that are sloped incorrectly, and find two lines that best approximates the Hough Lines. The longer the Hough Line, the higher weight it carries in the approximation.
7. Apply the two fitting lines to the original image
![final](https://github.com/vssrcj/lane-lines/blob/master/test_images_output/final.jpg)


My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
