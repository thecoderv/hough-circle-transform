# hough-circle-transform

Detection and counting of the coins in an image using Hough Circle Transform

The images have been picked from the Kaggle dataset ‘Brazilian Coins’:
https://www.kaggle.com/datasets/lgmoneda/br-coins

The images contain multiple coins of different count, sizes and spacing. Additionally, the images have different intensities of lighting i.e., dark, light, low contrast, and blurry images.]

Introduction:
The Hough Transform is a feature extraction algorithm originally created to recognize complex lines in images. It has been modified and enhanced to be able to recognize other shapes such as circles and quadrilaterals of specific types.

Goal: Detection and counting of the coins in an image using Hough Circle


Algorithm

The parametric equation that describes the shape can be used to build a parameter space and detect that shape. For the circle: r2=(x−x0)^2+(y−y0)^2
Thus, the circle parameters are center (x0,y0) and radius r and the parameter space would be three dimensional, (x0,y0, r).

Circle Hough Transform (CHT) Algorithm:

1) For each A[a, b, r] = 0;

2) Process the filtering algorithm on image Gaussian Blurring, convert the image to grayscale, and make the Canny operator, The Canny operator gives the edges on the image.

3) Vote all possible circles in the accumulator.

4) The local maximum voted circles of Accumulator A gives the circle Hough space.

5) The maximum voted circle of Accumulator gives the circle.


Implementation:

Using the OpenCV2 function .HoughCircles() to detect the circles.

After trying multiple values for the parameters we found that the values given below worked best
for this dataset.

![image](https://user-images.githubusercontent.com/121651746/217101062-b05ba739-fcb0-4f0c-8efc-61865296b8b0.png)

When we draw the circles and display the image it looks like the image below because of the noise in the image.

![image](https://user-images.githubusercontent.com/121651746/217101230-021fbbb6-ea19-4d11-9b84-728e699bc5aa.png)

Therefore I used a 11 by 11 Gaussian kernel to blur the image to remove the noise and then apply hough circle transform

The resulting output is:

![image](https://user-images.githubusercontent.com/121651746/217101472-accc62b0-e833-4877-bb8f-1b849e8c021a.png)

Results:

Detection of coins and their count in more images from the dataset. (In the images given below the number of circles counted equals the number of coins.)


![image](https://user-images.githubusercontent.com/121651746/217101633-9540b394-cfdd-4e6f-8450-1000eb96b29a.png)
![image](https://user-images.githubusercontent.com/121651746/217101678-88641c9b-0826-4e80-b93c-d0c0758b043d.png)
![image](https://user-images.githubusercontent.com/121651746/217101717-3e81ebe6-61a5-4a74-a1b2-fdd742066ef5.png)




