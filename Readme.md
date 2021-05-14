# Readme.md

The repo contains the scripts I used during my summer school training at Dept of Computer Science, IIT BHU.
The topic was image processing techniques and anomaly detection.
The database used was primarily [UCSD Pedestrian Dataset](http://www.svcl.ucsd.edu/projects/anomaly/dataset.html).

Basic Image processing included:

1. Edge Detection
2. Contour Detection
3. Features Calculation(GLCM, Haralick, LBP)
4. Image Histogram, Histogram Equalisation
5. Thresholding(Binary, Adaptive, Otsu)

In Anomaly Detection, the aim was to detect anomalies(i.e. Cars, skaters, bikers) in a pedestrian Dataset.
Our approachs are as follows:

1. Approach 1:
   1. Train an SVM on the calculated(LBP, GLCM) features of people
   2. Calculate contours of objects on each frame of video
   3. Classify each contour with our trained SVM.
Results: Failed.

2. Approach 2:
   1. Calculate the velocity and direction of moving objects using optical Flow.(Since cars and bikes will significantly higher velocity.)
   2. Take higher( ~95% percentile) of the velocities, those will be of the anomalies like car or bikes .
Results:Success
