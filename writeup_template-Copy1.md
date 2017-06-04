# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. 

My pipeline consisted of the following steps:
    1- Create a grayscale copy of the image
    2- Applying Gaussian blur
    3- Finding edges using Canny method
    4- Creating a mask on the image to only process the region of interest
    5- Using hough line method to create lines connecting the points detected by canny finction
    6- Creating two single solid guide lines in order to show the lane lines. This step is further explained below.
    7- Imposing the processed image with line over the original image and plotting it

Step 6:
The idea is to divide slopes of hough_lines into positive and negative group. Then take an average over each group. Then assign positive averaged slope as slope of the left guide line and negative to the right line. By assuming each line equation to be y=mx+b, b is calculated by solving the line equation for b when passing throgh the mid point of the guideline. In order to calculate the midpoint, all Xs and Ys contributing in hough_lines are called and their midpoint is calculated as sum(all x)/(number of points). The same procedure is done formid point of y axis which is basically the midpoint between the upper edge of mask and bottom of the image.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
