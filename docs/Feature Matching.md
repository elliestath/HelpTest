
# Feature Matching

## Brute Force

[Source](https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_feature2d/py_matcher/py_matcher.html)

Every feature descriptor in the first set is matched with all other features in second set using some distance calculation, returning the closest one. **_BFMatcher.match()_ or _BFMatcher.knnMatch()_ ??**

*Parameters*

 - *NormType*

 NORM_L1 / NORM_L2 / NORM_HAMMING / NORM_HAMMING2 --> Distance measurement to be used

 - *Ratio:*

 0.8: ratio test proposed by D.Lowe in SIFT paper

 - *Cross Matching*

Cross check (bool). If it is true, matching returns only those matches with value (i,j) such that i-th descriptor in set A has j-th descriptor in set B as the best match and vice-versa. That is, the two features in both sets should match each other. It provides consistent result, and is a good alternative to ratio test proposed.

 - *Geometric Test*

Homography Matrix/Fundamental Matrix

    IF Homography
    	Compute Method: All Points/RANSAC/LMedS/RHO
    	IF All Points
		    Confidence
    	ELSE IF RANSAC
		    Distance/Confidence/Maximum RANSAC iteration
	ELSE IF LMedS
			Confidence
	ELSE IF RHO
			Distance/Confidence
    ELSE
    	Compute Method: 7-point/8-point/RANSAC/LMedS
    	IF RANSAC
		    	Distance/Confidence
    	ELSE IF LMedS
			Confidence
    	ELSE (7-point/8-point)
    		Nothing

 1. Homography

 Finds a perspective transformation between two planes. Can be estimated either by using all points (`All points`) to compute an initial homography estimate with a simple least-squares scheme, or RANSAC-based robust method `RANSAC`, a Least-Median robust method (`LMedS`) or the PROSAC-based robust method `RHO`. The methods `RANSAC`, `LMeDS` and `RHO` try many different random subsets of the corresponding point pairs (of four pairs each), estimate the homography matrix using this subset and a simple least-square algorithm, and then compute the quality/goodness of the computed homography (which is the number of inliers for RANSAC or the median re-projection error for LMeDs). The functions find and return the perspective transformation between the source and the destination plane so that the back-projection error is minimized. Regardless of the method, robust or not, the computed homography matrix is refined further (using inliers only in case of a robust method) with the Levenberg-Marquardt method to reduce the re-projection error even more. The method `RANSAC` and `RHO` can handle practically any ratio of outliers but it needs a threshold to distinguish inliers from outliers. The method `LMeDS` does not need any threshold but it works correctly only when there are more than 50% of inliers. Finally, if there are no outliers and the noise is rather small, use the default method (`All points`).The function is used to find initial intrinsic and extrinsic matrices. Homography matrix is determined up to a scale.

 2. Fundamental

Calculates the fundamental matrix (projective transformation with at least 7 point correspondences) from the corresponding points in two images, using either the `7-point algorithm`, the `8-point algorithm`, `RANSAC` or `LMedS`. Normally just one matrix is found. But in case of the `7-point algorithm`, the function may return up to 3 solutions.


## FLANN

*Fast Library for Approximate Nearest Neighbors*

It contains a collection of algorithms optimized for fast nearest neighbor search in large datasets and for high dimensional features. For large datasets, it can be more efficient than Brute Force.

 - *Ratio:*
 - *Cross Matching*
 - *Geometric Test*

Homography Matrix/Fundamental Matrix

    IF Homography
    	Compute Method: All Points/RANSAC/LMedS/RHO
    	IF All Points
		    Confidence
    	ELSE IF RANSAC
		    Distance/Confidence/Maximum RANSAC iteration
	ELSE IF LMedS
			Confidence
	ELSE IF RHO
			Distance/Confidence
    ELSE
    	Compute Method: 7-point/8-point/RANSAC/LMedS
    	IF RANSAC
		    	Distance/Confidence
    	ELSE IF LMedS
			Confidence
    	ELSE (7-point/8-point)
    		Nothing




[FLANN]: Muja, M. and Lowe, D.G., 2017. Fast library for approximate nearest neighbors. _Dosegljivo: https://github. com/mariusmuja/flann_.

> Written with [StackEdit](https://stackedit.io/).
