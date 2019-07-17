## SfM test problem 

This is test problem to showcase key features of the project.

There is dataset comprised by images of the same scene taken from the different perspective. The task is to recover and visualize structure of the scene in the form of the consistent point cloud. To do that you should perform several steps:


1. Download dataset from [here](https://drive.google.com/open?id=1cBQl3NNYvlbLOCNS47Yb3XizO1SDWBPR). During further processing assume that camera intrinsics are unknown, but that all images were taken from the same camera.

2. Process images by detecting and describing keypoints using any rich detector/descriptor ([AKAZE](https://github.com/pablofdezalc/akaze) or its analogs are recommended).

3. Build co-visibility graph of the scene (measurement matrix) via matching keypoints and rejecting outliers using geometric constraints for every image pair. We recommend to use RANSAC or its analogs for outliers rejection.

4. Optimize camera intrinsics, camera motions and 3D points using your favorite solver. We recommend to use [g2o](https://github.com/RainerKuemmerle/g2o) or [ceres-solver](http://ceres-solver.org/). Use constraints on the form of the calibration matrix: zero skew. Note: If you have some troubles with solver libraries you can find minor solution by means of measurement matrix factorization. But this approach would be assessed as a poor solution.

5. Visualize results of reconstruction using [Pangolin](https://github.com/stevenlovegrove/Pangolin), Elektronik or any other visualization library/framework.
