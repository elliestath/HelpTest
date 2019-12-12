# HELP for PhotoMatch
Brief explanations of the algorithms used in the scientific initiative PhotoMatch. 

## Preprocessing
This step offers the option to use image enhancement techniques that could potentially facilitate the detection of robust image features.

**PARAMETERS**
Full Image Size/Max Image Size

### Decolorization
Contrast Preserving Decolorization

### ACEBSF
*Adaptive Contrast Enhancement Based on modified Sigmoid Function.* 
It first improves the poor quality images using a modified sigmoid function and then applies contrast limited adaptive histogram equalization (AHE) to enhance image contrast.

*Parameters*

 - Blocksize (Width: 8/Height: 8)
 - L: 0.3
 - K1: 10
 - K2: 0.50

[ACEBSF]: _S. Lal and M. Chandra, "Efficient algorithm for contrast enhancement of natural images," The International Arab Journal of Information Technology, vol. 11, no. 1, January 2014._

### CLAHE
*Contrast Limited Adaptive Histogram Equalization.*
CLAHE is a local contrast enhancement technique robust to outliers. Local contrast enhancement methods such as adaptive histogram equalization (AHE) divide the original image into several non-overlapped sub-blocks and apply histogram equalization accordingly. CLAHE is an improvement of AHE and performs well on low contrast images.

*Parameters*

 - Clip Limit: 40
 - Tiles Size X: 8
 - Tiles Size Y: 8

[CLAHE]: _Zuiderveld, Karel. “Contrast Limited Adaptive Histograph Equalization.” _Graphic Gems IV_. San Diego: Academic Press Professional, 1994. 474–485._
[Source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3092044/) 

### CMBFHE
*Cascaded Multistep Binomial Filtering Histogram Equalization.*
Based on the POSHE approach using cascaded multistep binomial filtering histogram equalization to reduce algorithm complexity. Similar to other local adaptive techniques, it exploits image sub-blocks (and not pixels), achieving results with effect similar to the application of a low-pass filter (LPF) avoiding the blocking effect.

*Parameters*

 - Block Size (Width: 11/Height: 11)

[CMBFHE]: _F. Lamberti, B. Montrucchio, and A. Sanna, "CMBFHE: a novel contrast enhancement technique based on cascaded multistep binomial filtering histogram equalization," TCE, vol. 52, no. 3, 2006._
[POSHE]: _J. Y. Kim, L. S. Kim, and S. H. Hwang, “An advanced contrast enhancement using partially overlapped sub-block histogram equalization,” IEEE Transactions on Circuits and Systems for Video Technology, Vol. 11(4), pp. 475-484, 2001._

### DHE
*Dynamic Histogram Equalization.*
Traditional histogram equalization employing a histogram partitioning operation to avoid dominating components and achieving better overall contrast enhancement with controlled dynamic range of gray levels while also reassuring minimum detail loss.

*Parameters*

 - x: 1

[Source]: _M. Abdullah-Al-Wadud, Md. Hasanul Kabir, M. Ali Akber Dewan, and O. Chae, "A dynamic histogram equalization for image contrast enhancement," Intl. Conf. Consumer Electronics, pp. 1-2, 2007._

### FAHE
*Fast implementation of Adaptive Histogram Equalization* 
Software techniques on histogram acquisition and accumulation as well on the block size decision are used to reduce computational complexity.

*Parameters*

 - Block Size (Width: 11/Height: 11)

[Source]: _Z. Wang and J. Tao, "A fast implementation of adaptive histogram equalization," in Proc. ICSP, 2006._

### HMCLAHE
*Histogram Modified Contrast Limited Adaptive Histogram Equalization.*
It incorporates both histogram modifications as an optimization technique and CLAHE. It controls the level of contrast enhancement, before CLAHE, resulting a strong contrast image with enhanced details.

*Parameters*

 - Block Size (Width: 11/Height: 11)
 - L: 0.03
 - Phi: 0.50

[Source]: _M. Sundaram, K. Ramar, N.Arumugam and G. Prabin, "Histogram based contrast enhancement for mammogram images," International Conference on Signal Processing, Communication, Computing and Networking Technologies, 2011._

### LCE-BSESCS
*Local Contrast Enhancement Utilizing Bidirectional Switching Equalization of Separated and Clipped Sub-histograms.*

*Parameters*

 - Block Size (Width: 33/Height: 33)

### MSRCP
*Multiscale Retinex with Chromaticity Preservation.*

Based on the original Multiscale Retinex method, it applies some modifications on the post-processing steps and preserves image chromaticity. Recommended for images with a correct color distribution and white lightning.

*Parameters*

 - Retinex Scales
 - Small scale: 10
 - Mid Scale: 100
 - Large scale: 220

[Source]: _Ana Bel´en Petro, Catalina Sbert, Jean-Michel Morel, Multiscale Retinex, Image Processing On Line, 2014._

### NOSHP
*Non-Overlapped Sub-blocks and local Histogram Projection.*
To reduce computational complexity, it segments the image into non-overlapped sub-blocks where the histogram projection (HP) is then executed individually. Subsequently, each sub-block is related to its adjacent three ones by certain weights, so that the integral image and local details can be enhanced.

*Parameters*

 - Block Size (Width: 127/Height: 127)

[Source:] _B. Liu, W. Jin, Y. Chen, C. Liu, and L. Li, "Contrast enhancement using non-overlapped sub-blocks and local histogram projection," TCE, vol. 57, no. 2, 2011._

### POHE
*Parametric-oriented histogram equalization (POHE)*
Local enhancement method using integral images to reduce computational time during the construction of the probability distribution function and the transformation function.

*Parameters*

 - Block Size (Width: 127/Height: 127)

Source: _Y. F. Liu, J. M. Guo, B. S. Lai, and J. D. Lee, "High efficient contrast enhancement using parametric approximation," in Proc. IEEE ICASSP, pp. 2444-2448, 26-31 May 2013_

### RSWHE
*Recursively Separated and Weighted Histogram Equalization.*
It segments an input histogram into two or more sub-histograms recursively, modifies them using a weighting process based on a normalized power law function, and performs HE on the weighted sub-histograms independently, achieving brightness preservation and image contrast enhancement.

[Source]: _Mary Kim and Min Gyo Chung, Recursively Separated and Weighted Histogram Equalization for Brightness Preservation and Contrast Enhancement, 2008._


### Wallis Filter
Locally adaptive contrast adjustment filter to enhance image gray-scale details. It ensures that within every specified window, the local mean and the standard deviation will match some given (user-specified) values. Used to eliminate uneven illumination, where bright and dark tones are both present.

*Parameters*

 - Contrast: 1
 - Brightness: 0.20
 - Imposed Average: 41
 - Imposed Local StdDev: 127
 - Kernel Size: 50

[Source] (https://www.microimages.com/documentation/TechGuides/55Wallis.pdf)


## Feature Extraction

### *Keypoint Detectors*

### AGAST
Adaptive and Generic Accelerated Segment Test. Corner detector. It is an optimization of FAST, thus also based on Accelerated Segment Test (AST), but  its decision tree is generic, with no need to retrain the it every time.
[Source: http://www.i6.in.tum.de/Main/ResearchAgast]

*Elmar Mair, Gregory D. Hager, Darius Burschka, Michael Suppa, and Gerhard Hirzinger. Adaptive and generic corner detection based on the accelerated segment test. In _Proceedings of the European Conference on Computer Vision (ECCV'10)_, September 2010* 

### AKAZE
Accelerated version of KAZE detector. In a similar fashion with KAZE, it operates in nonlinear scale space and not in Gaussian like SIFT and SURF do. Numerical methods are used to approximate the solution, namely Fast Explicit Diffusion (FED), that are proven to work much faster than any other discretization scheme.
[Source: self adjusted]

*Fast Explicit Diffusion for Accelerated Features in Nonlinear Scale Spaces. Pablo F. Alcantarilla, Jesús Nuevo and Adrien Bartoli]. In British Machine Vision Conference (BMVC), _Bristol, UK, September 2013_.*

### BRISK
A sampling pattern consisting of points lying on appropriately scaled concentric circles is applied at the neighborhood of each keypoint to retrieve gray values: processing local intensity gradients,the feature characteristic direction is determined. Finally, the oriented BRISK sampling pattern is used to obtain pairwise brightness comparison results which are assembled into the binary BRISK descriptor.

[Source: paper]
*Stefan Leutenegger, Margarita Chli, and Roland Yves Siegwart. Brisk: Binary robust invariant scalable keypoints. In _Computer Vision (ICCV), 2011 IEEE International Conference on_, pages 2548–2555. IEEE, 2011.*

### FAST
Modification of the SUSAN corner detector that outperforms previously used keypoint detectors in terms of speed and reliability. Is based on Accelerated Segment Test (AST), which is used to distinguish keypoints by examining the intensity values of 16 pixels that fall in the circular pattern around the candidate pixel. A candidate pixel is considered as keypoint if there are at least N continuous pixels that have either higher or lower intensity values than it.
[Source: self adjusted]

*E. Rosten. Machine Learning for High-speed Corner Detection, 2006*

### GFTT
Stands for [Good features to track](http://www.ai.mit.edu/courses/6.891/handouts/shi94good.pdf). Modified version of the traditional Harris detector as to select only the features that pass the dissimilarity (change of appearance) test and filter out the less robust ones.
[Source: self adjusted]

*Harris, C.G. and Stephens, M., 1988, August. A combined corner and edge detector. In Alvey vision conference (Vol. 15, No. 50, pp. 10-5244).* 

### KAZE
Operates in nonlinear scale space and not in Gaussian, keeping important image details [paper](http://robesafe.com/personal/pablo.alcantarilla/papers/Alcantarilla12eccv.pdf). The nonlinear scale space is build efficiently by means of Additive Operator Splitting (AOS) scheme.
[Source: self adjusted]

*Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012, October. KAZE features. In _European Conference on Computer Vision_ (pp. 214-227). Springer, Berlin, Heidelberg.*

### MSD
Maximal Self-Dissimilarity. The algorithm implements a novel interest point detector stemming from the intuition that image patches which are highly dissimilar over a relatively large extent of their surroundings hold the property of being repeatable and distinctive. This concept of "contextual self-dissimilarity" reverses the key paradigm of recent successful techniques such as the Local Self-Similarity descriptor and the Non-Local Means filter, which build upon the presence of similar - rather than dissimilar - patches. Moreover, it extends to contextual information the local self-dissimilarity notion embedded in established detectors of corner-like interest points, thereby achieving enhanced repeatability, distinctiveness and localization accuracy.
[Source: self adjusted]

*Federico Tombari and Luigi Di Stefano. Interest points via maximal self-dissimilarities. In _Asian Conference on Computer Vision – ACCV 2014_, 2014.*

### MSER
Maximally stable extremal region extractor.

### ORB
The algorithm uses FAST in pyramids to detect stable keypoints, selects the strongest features using FAST or Harris response, finds their orientation using first-order moments and computes the descriptors using BRIEF (where the coordinates of random point pairs (or k-tuples) are rotated according to the measured orientation).

*Ethan Rublee, Vincent Rabaud, Kurt Konolige, Gary R. Bradski: ORB: An efficient alternative to SIFT or SURF. ICCV 2011: 2564-2571.*

### SIFT
Detector part of SIFT algorithm uses Difference of Gaussians (DoG), a feature enhancement method, where image pyramids are created by repeatedly convolving the original image with Gaussian kernels. In each pyramid level, every pixel is compared with its 8 neighboring pixels in the current image as well as with its 9 neighbors of its adjacent pyramid images. Keypoints are detected as extrema in the difference between the Gaussian images.
[Source: self adjusted]

*Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. _International journal of computer vision_, _60_(2), pp.91-110.*

### STAR
Star Feature Detector is derived from CenSurE (Center Surrounded Extrema) detector.

### SURF
SURF uses Fast Hessian as a detection method that is based on integral images through Hessian matrix approximation. Box type convolution filters of different sizes are used to approximate second order Gaussian derivatives for each image point. Keypoints are regions where the determinant becomes maximal through non-maximal suppression.

*Bay, H., Tuytelaars, T. and Van Gool, L., 2006, May. Surf: Speeded up robust features. In _European conference on computer vision_ (pp. 404-417). Springer, Berlin, Heidelberg.*


### *Keypoint Descriptors*

### AKAZE
A highly efficient Modified-Local Difference Binary (M-LDB) descriptor that exploits gradient and intensity information from the nonlinear scale space. The LDB descriptor follows the same principle as BRIEF, but using binary tests between the aver-age of areas instead of single pixels for additional robustness. M-LDB uses the derivatives computed in the feature detection step, reducing the number of operations required to construct the descriptor.

*Fast Explicit Diffusion for Accelerated Features in Nonlinear Scale Spaces. Pablo F. Alcantarilla, Jesús Nuevo and Adrien Bartoli]. In British Machine Vision Conference (BMVC), _Bristol, UK, September 2013_.*

### BRIEF
Standing for Binary Robust Independent Elementary Features, is a short binary descriptor using the hamming distance.
Not invariant to scale and rotation.

*Calonder, M., Lepetit, V., Ozuysal, M., Trzcinski, T., Strecha, C. and Fua, P., 2011. BRIEF: Computing a local binary descriptor very fast. _IEEE Transactions on Pattern Analysis and Machine Intelligence_, _34_(7), pp.1281-1298.*

### BRISK

### DAISY
Feature descriptor that depends on histograms of gradients like SIFT but uses a Gaussian weighting and circularly symmetrical kernel.

*Tola, E., Lepetit, V. and Fua, P., 2009. Daisy: An efficient dense descriptor applied to wide-baseline stereo. _IEEE transactions on pattern analysis and machine intelligence_, _32_(5), pp.815-830.*

### FREAK

The algorithm propose a novel keypoint descriptor inspired by the human visual system and more precisely the retina, coined Fast Retina Key- point (FREAK). A cascade of binary strings is computed by efficiently comparing image intensities over a retinal sampling pattern. FREAKs are in general faster to compute with lower memory load and also more robust than SIFT, SURF or BRISK. They are competitive alternatives to existing keypoints in particular for embedded applications.

*A. Alahi, R. Ortiz, and P. Vandergheynst. FREAK: Fast Retina Keypoint. In IEEE Conference on Computer Vision and Pattern Recognition, 2012. CVPR 2012 Open Source Award Winner.*

### HOG
Histogram of Orented Gradients. Based on image gradients, histograms of gradients are calculated for pre-defiend image sub-regions. Mainly used for pedestrian detection, sensitive to rotation changes.

*Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011, November. ORB: An efficient alternative to SIFT or SURF. In _ICCV_ (Vol. 11, No. 1, p. 2).*

### KAZE

*Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012, October. KAZE features. In _European Conference on Computer Vision_ (pp. 214-227). Springer, Berlin, Heidelberg.*

### LATCH
LATCH is a binary descriptor based on learned comparisons of triplets of image patches.

*Levi, G. and Hassner, T., 2016, March. LATCH: learned arrangements of three patch codes. In _2016 IEEE winter conference on applications of computer vision (WACV)_ (pp. 1-9). IEEE.*

### LUCID

*Ziegler, A., Christiansen, E., Kriegman, D. and Belongie, S.J., 2012. Locally uniform comparison image descriptor. In _Advances in Neural Information Processing Systems_ (pp. 1-9).*

### LSS

Local Self-Similarity is based on the texture features of images to densely calculate local self-similarity descriptors.

*Shechtman E, Irani M. Matching local self-similarities across images and videos, in: Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 1–8, 2007.*

### ORB
Oriented FAST and Rotated BRIEF, as the name declares combines FAST for feature detection and BRIEF for feature description, providing invariance to rotation and robustness to noise.

*Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011, November. ORB: An efficient alternative to SIFT or SURF. In _ICCV_ (Vol. 11, No. 1, p. 2).*

### SIFT
Image gradients are used  to describe the detected keypoints. Intensity values, gradient magnitude and orientation are stored, reassuring also a certain level of invariance under illumination changes.

*Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. _International journal of computer vision_, _60_(2), pp.91-110.*

### SURF
The description part of SURF describes the intensity of the neighborhood around the pixel using Haar wavelets.

*Bay, H., Tuytelaars, T. and Van Gool, L., 2006, May. Surf: Speeded up robust features. In _European conference on computer vision_ (pp. 404-417). Springer, Berlin, Heidelberg.*

## Feature Matching

### Brute Force
[Source: https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_feature2d/py_matcher/py_matcher.html]
Every feature descriptor in the first set is matched with all other features in second set using some distance calculation, returning the closest one. **_BFMatcher.match()_ or _BFMatcher.knnMatch()_ ??**

*NormType* (NORM_L1 / NORM_L2 / NORM_HAMMING / NORM_HAMMING2) --> Distance measurement to be used
*Ratio:* 0.8 --> ratio test proposed by D.Lowe in SIFT paper
*Cross Matching* --> Cross check (bool). If it is true, matching returns only those matches with value (i,j) such that i-th descriptor in set A has j-th descriptor in set B as the best match and vice-versa. That is, the two features in both sets should match each other. It provides consistent result, and is a good alternative to ratio test proposed.
*Geometric Test*: Homography Matrix/Fundamental Matrix

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

- Homography: Finds a perspective transformation between two planes. Can be estimated either by using all points (`All points`) to compute an initial homography estimate with a simple least-squares scheme, or RANSAC-based robust method `RANSAC`, a Least-Median robust method (`LMedS`) or the PROSAC-based robust method `RHO`. The methods `RANSAC`, `LMeDS` and `RHO` try many different random subsets of the corresponding point pairs (of four pairs each), estimate the homography matrix using this subset and a simple least-square algorithm, and then compute the quality/goodness of the computed homography (which is the number of inliers for RANSAC or the median re-projection error for LMeDs). The functions find and return the perspective transformation between the source and the destination plane so that the back-projection error is minimized. Regardless of the method, robust or not, the computed homography matrix is refined further (using inliers only in case of a robust method) with the Levenberg-Marquardt method to reduce the re-projection error even more. The method `RANSAC` and `RHO` can handle practically any ratio of outliers but it needs a threshold to distinguish inliers from outliers. The method `LMeDS` does not need any threshold but it works correctly only when there are more than 50% of inliers. Finally, if there are no outliers and the noise is rather small, use the default method (`All points`).The function is used to find initial intrinsic and extrinsic matrices. Homography matrix is determined up to a scale
- Fundamental: Calculates the fundamental matrix (projective transformation with at least 7 point correspondences) from the corresponding points in two images, using either the `7-point algorithm`, the `8-point algorithm`, `RANSAC` or `LMedS`. Normally just one matrix is found. But in case of the `7-point algorithm`, the function may return up to 3 solutions.


### FLANN
FLANN stands for Fast Library for Approximate Nearest Neighbors [Muja 2009]. It contains a collection of algorithms optimized for fast nearest neighbor search in large datasets and for high dimensional features. For large datasets, it can be more efficient than Brute Force.

*Ratio:*
*Cross Matching*
*Geometric Test*: Homography Matrix/Fundamental Matrix

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


## Quality Control

### ROC Curves

### DET Curves

> Written with [StackEdit](https://stackedit.io/).
