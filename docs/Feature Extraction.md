
# Feature Extraction

## *Keypoint Detectors*

## AGAST

<p style="text-align: justify;">
*Adaptive and Generic Accelerated Segment Test.* 

Corner detector introduced as an optimization of FAST, achieving higher computational efficiency.  AGAST is also based on Accelerated Segment Test (AST), but  its decision tree is generic with no need to retrain, as it adapts according to the current region of the images being processed.

[Source: self adjusted] + [Source](http://www.i6.in.tum.de/Main/ResearchAgast)

[[AGAST](https://mediatum.ub.tum.de/doc/1287456/file.pdf)]: _Mair, E., Hager, G.D., Burschka, D., Suppa, M. and Hirzinger, G., 2010. Adaptive and generic corner detection based on the accelerated segment test. In European conference on Computer vision, pp. 183-196. Springer, Berlin, Heidelberg._

</p>

## AKAZE

*Accelerated KAZE*

<p style="text-align: justify;">
In a similar fashion with KAZE,  this blob detector operates in nonlinear scale space and not in Gaussian like SIFT and SURF. Numerical methods are used to approximate the solution, namely Fast Explicit Diffusion (FED), that are proven to work much faster than any other discretization scheme. The detector is based on the determinant of the Hessian Matrix, while Scharr filters are used to provide rotational invariance.

[Source: self adjusted]

[[AKAZE](http://www.bmva.org/bmvc/2013/Papers/paper0013/abstract0013.pdf)]: _Alcantarilla, P.F., Nuevo, J., Bartoli, A., 2013. Fast explicit diffusion for accelerated features in nonlinear scale spaces. In Proc. BMVC, Vol. 34(7), pp. 1281–1298._
</p>

## BRISK

*Binary Robust Invariant Scalable Keypoints*

<p style="text-align: justify;">
Corner detector robust to scale and rotation changes. Using AGAST detection methods, a sampling pattern consisting of points lying on appropriately scaled concentric circles is applied at the neighborhood of each keypoint to retrieve gray values: processing local intensity gradients,the feature characteristic direction is determined. 

[Source: paper]+ [Source:self-adjusted]

[[BRISK](https://www.research-collection.ethz.ch/bitstream/handle/20.500.11850/43288/1/eth-7684-01.pdf)]: _Leutenegger, S., Chli, M. and Siegwart, R., 2011. BRISK: Binary robust invariant scalable keypoints. In 2011 IEEE International Conference on Computer Vision a(ICCV), pp. 2548-2555. IEEE._
</p>

## FAST

*Features from Accelerated Segment Test*

<p style="text-align: justify;">
Modification of the SUSAN corner detector that outperforms previously used detectors in terms of speed and reliability. Is based on Accelerated Segment Test (AST), which is used to distinguish keypoints by examining the intensity values of 16 pixels in a circular pattern around the candidate keypoint pixel. A candidate pixel is considered as keypoint based on a segment test, i.e. if there are at least N continuous pixels that have either higher or lower intensity values than it. Because of his effectiveness, it is suitable for real-time applications.

[Source: self adjusted]

[[FAST](https://link.springer.com/chapter/10.1007/11744023_34)]: _Rosten, E. and Drummond, T., 2006. Machine learning for high-speed corner detection. In European conference on computer vision, pp. 430-443. Springer, Berlin, Heidelberg._
</p>

## GFTT 

*Good Features to Track.* 

<p style="text-align: justify;">
Modified version of the traditional Harris detector as to select only the features that have large eignevalues and pass the dissimilarity  test. Thus, it filters out the less robust ones through a temporal monitoring. In more detail, in order to keep the more robust features, it then rejects corners with minimum eigenvalues less than a threshold. Finally, it further rejects weak corners that are closer than a pre-defined distance to a strong corner. Invariant to affine changes.

[Source: self adjusted]

[Good features to track](http://www.ai.mit.edu/courses/6.891/handouts/shi94good.pdf)

[Harris]: _Harris, C.G. and Stephens, M., 1988. A combined corner and edge detector. In Alvey vision conference, Vol. 15(50), pp. 10-5244._

[GFTT]: _J. Shi and C. Tomasi. Good features to track. In IEEE Computer Society Conference on Computer Vi-sion and Pattern Recognition, pages 593–600, 1994._
</p>

## KAZE

<p style="text-align: justify;">

Blob detector that operates in nonlinear scale space through non-linear diffusion filtering (and not in Gaussian), keeping important image details. KAZE detector is based on scale normalized determinant of Hessian Matrix, computed at multiple non-linear scale levels. 

[Source: self adjusted]

[[KAZE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.304.4980&rep=rep1&type=pdf)]: _Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012. KAZE features. In European Conference on Computer Vision, pp. 214-227. Springer, Berlin, Heidelberg._
</p>

## MSD

*Maximal Self-Dissimilarity.* 

<p style="text-align: justify;">
The algorithm implements a detector based on the assumption that image patches (edges, corners, blobs etc) which are highly dissimilar over a relatively large extent of their surroundings tend to be repeatable and distinctive. It relies on the computation of a patch’s self-similarity over an extended neighborhood and more precisely it  determines whether or not a pixel (keypoint) shows similar patches in its surroundings using Contextual Self-Dissimilarity (CSD). It provided invariance to viewpoint variations and illmination changes.

[Source: self adjusted]

[[MSD](http://imagine.enpc.fr/~monasse/Stereo/Projects/TombariDiStefano14.pdf)]: _Tombari, F. and Di Stefano, L., 2014. Interest points via maximal self-dissimilarities. In Asian Conference on Computer Vision, pp. 586-600. Springer, Cham._
</p>

## MSER

*Maximally Stable Extremal Region Extractor.*

<p style="text-align: justify;">
Blob detection algorithm of nearly linear complexity, invariant to scale, rotation and affine transformations tackling wide baseline matching. First, distinguished regions are detected and multiple scaled measurement regions are associated with them. MSER has been sucessfully used for tracking applications.

[Source:self-adjusted]

[MSER](https://pdfs.semanticscholar.org/e045/aafb44693c9de943c750a6b60f2153ac3ccb.pdf): _Matas, J., Chum, O., Urban, M. and Pajdla, T., 2004. Robust wide-baseline stereo from maximally stable extremal regions. _Image and vision computing_, _22_(10), pp.761-767._
</p>

## ORB

*Oriented FAST and Rotated BRIEF*

<p style="text-align: justify;">
Corner detection algorithm that uses modified FAST (oFAST) in pyramids to detect stable keypoints over scale changes. It selects the strongest corners using FAST or Harris response (Harris Corner score) and finds their orientation using first-order moments.

[Source:self-adjusted]

[[ORB](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.370.4395&rep=rep1&type=pdf)]: _Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011. ORB: An efficient alternative to SIFT or SURF. In ICCV, Vol. 11(1), pp. 2._
</p>

## SIFT

*Scale Invariant Feature Transform*

<p style="text-align: justify;">
Blob detector using Difference of Gaussians (DoG), a feature enhancement method, where image pyramids are created by repeatedly convolving the original image with Gaussian kernels. In each pyramid level, every pixel is compared with its 8 neighboring pixels in the current image as well as with its 9 neighbors of its adjacent pyramid images. Keypoints are detected as extrema (local maxima) in the difference between the Gaussian images.

[Source: self adjusted]

[[SIFT](https://link.springer.com/article/10.1023/B:VISI.0000029664.99615.94)]: _Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. International journal of computer vision, Vol. 60(2), pp.91-110._
</p>

## STAR

<p style="text-align: justify;">
Star Feature Detector derived from CenSurE (Center Surrounded Extrema) detector. STAR is multiscale and works on full spatial resolution, using a bi-level approximation of the Laplacian of Gaussians (LoG) filter and integral images for computational efficiency. Scale space is generated by using masks of different sizes.

[Source:self-adjusted]

[[CENSURE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.465.1117&rep=rep1&type=pdf)]: _Agrawal, M., Konolige, K. and Blas, M.R., 2008. Censure: Center surround extremas for realtime feature detection and matching. In European Conference on Computer Vision, pp. 102-115. Springer, Berlin, Heidelberg._
</p>

## SURF

*Speeded-Up Robust Features*

<p style="text-align: justify;">
SURF blob detector uses Fast Hessian (Hessian-Laplace) as a detection method that is based on integral images through Hessian matrix approximation. Box type convolution filters of different sizes are used to approximate second order Gaussian derivatives for each image point. Keypoints are regions where the determinant becomes maximal through non-maximal suppression. 

[Source:self-adjusted]

[[SURF](https://link.springer.com/chapter/10.1007/11744023_32)]: _Bay, H., Tuytelaars, T. and Van Gool, L., 2006. Surf: Speeded up robust features. In European conference on computer vision, pp. 404-417. Springer, Berlin, Heidelberg._
</p>


## *Keypoint Descriptors*

## AKAZE

*Accelerated KAZE*

A highly efficient Modified Local Difference Binary (MLDB) descriptor that uses gradient and intensity information from the nonlinear scale space. The LDB descriptor is similar to BRIEF, but using binary tests between the average of areas instead of single pixels for additional robustness. MLDB uses the derivatives computed in the feature detection step.

[Source:self-adjusted]

[[AKAZE](http://www.bmva.org/bmvc/2013/Papers/paper0013/abstract0013.pdf)]: _Alcantarilla, P.F., Nuevo, J., Bartoli, A., 2013. Fast explicit diffusion for accelerated features in nonlinear scale spaces. In Proc. BMVC, Vol. 34(7), pp. 1281–1298._


## BOOST 

*Learning Image Descriptors with Boosting*

Supervised learning framework detecting low dimensional but highly discriminative features. It applies boosting to learn a set of binary hash functions that achieve a performance comparable to real-valuedother descriptors such as BRIEF and BRISK, by optimizing their sampling patterns. Each bit is computed as a thresholded linear combination of a set of weak learners.

[Source:self-adjusted]

[[BOOST](Trzcinski_Boosting_Binary_Keypoint_2013_CVPR_paper)]: *Trzcinski, T., Christoudias, M., Fua, P. and Lepetit, V., 2013. Boosting binary keypoint descriptors. In _Proceedings of the IEEE conference on computer vision and pattern recognition_ (pp. 2874-2881).*

## BRIEF

*Binary Robust Independent Elementary Features*

A short binary descriptor inspired by the census transform extracting bit strings (intensities) which are therefore compared along the same lines. Simple binary tests are used on smoothed image patches. Using pre-trained binary tests on classificatiion trees, the signature od any arbitrary keypoint can be obtained. Although originally not invariant to scale and rotation, several variations existi such as the upright (U-BRIEF), oriented (O-BRIEF) or scaled (S-BRIEF).

[Source:self-adjusted]

[[BRIEF](https://ieeexplore.ieee.org/abstract/document/6081878)]: _Calonder, M., Lepetit, V., Ozuysal, M., Trzcinski, T., Strecha, C. and Fua, P., 2011. BRIEF: Computing a local binary descriptor very fast. IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol. 34(7), pp.1281-1298._

## BRISK

*Binary Robust Invariant Scalable Keypoints*

It uses a pattern of points circually distributed around each detected feature, estimates the dominant orientation by local gradient in order to achieve rotation invariance. BRISK features are invariant to scale, rotation, and limited affine changes.

[Source:self-adjusted]

[[BRISK](https://www.research-collection.ethz.ch/bitstream/handle/20.500.11850/43288/1/eth-7684-01.pdf)]: _Leutenegger, S., Chli, M. and Siegwart, R., 2011. BRISK: Binary robust invariant scalable keypoints. In 2011 IEEE International Conference on Computer Vision (ICCV), pp. 2548-2555. IEEE._

## DAISY 

Feature descriptor that  retains the robustness of other descriptors like SIFT or GLOH, yet can be efficiently computed densly for every pixel generating depth maps. Designed to work also with wide-baseline scenarios, it depends on histograms of gradients like SIFT but uses a Gaussian weighting, i.e. sum of convolutions to achieve speed, and circularly symmetrical kernel. Robust to scale, viewpoint, brightness and image quality transformations.

[[DAISY](https://ieeexplore.ieee.org/abstract/document/4815264)]: _Tola, E., Lepetit, V. and Fua, P., 2009. Daisy: An efficient dense descriptor applied to wide-baseline stereo. IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol. 32(5), pp. 815-830._

## FREAK

*Fast Retina Keypoint*

The algorithm propose a novel keypoint descriptor inspired by the human visual system and and its retina. A cascade of binary strings is computed by efficiently comparing image intensities over a retinal sampling pattern, that, similarly to BRIEF is circular but with a higher density closer to the keypoint.  They are competitive alternatives to existing keypoints in particular for embedded applications.

[Source:self-adjusted]

[[FREAK](https://ieeexplore.ieee.org/abstract/document/6247715)]: _Alahi, A., Ortiz, R. and Vandergheynst, P., 2012. Freak: Fast retina keypoint. In 2012 IEEE Conference on Computer Vision and Pattern Recognition, pp. 510-517. IEEE._

## HOG 

*Histogram of Oriented Gradients*

Based on image gradients, histograms of gradients (HOG) are calculated for pre-defiend image subregions. For each feature point, a square block is defined.  Applying the Sobel operator, gradient orientation and magnitutes are computed. Pixels are assigned to orientation bins and for each cell a vector of nine values is obtained. Mainly used for pedestrian detection and tracking, sensitive to rotation changes.

[[HOG](https://hal.inria.fr/file/index/docid/548512/filename/hog_cvpr2005.pdf)]: _Dalal, N. and Triggs, B., 2005. Histograms of oriented gradients for human detection. In IEEE International Conference on Computer Vision and Pattern Recognition, V. 2, pp. 886–893._


## KAZE 

KAZE descriptor reassures rotation invariance by finding the dominant orientation within a circular region around every detected feature using a variant of the SURF descriptor. KAZE features are invariant to rotation, scale, limited affine and have more distinctiveness at varying scales with the cost of moderate increase in computational time.


[Source:self-adjusted]

[[KAZE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.304.4980&rep=rep1&type=pdf)]: _Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012. KAZE features. In European Conference on Computer Vision, pp. 214-227. Springer, Berlin, Heidelberg._

## LATCH 

*Learned Arrangements of Three Patch Codes*

LATCH is a binary descriptor based on learned comparisons of triplets of image patches instead of pairs to improve robustness. Patch triplets are introduced in order to improve robustness

[[LATCH](https://arxiv.org/pdf/1501.03719.pdf)]: _Levi, G. and Hassner, T., 2016. LATCH: learned arrangements of three patch codes. In 2016 IEEE winter conference on applications of computer vision (WACV), pp. 1-9. IEEE._

## LSS 

*Local Self-Similarity*

Local Self-Similarity is based on the texture features of images to densely calculate local self-similarity descriptors on patch-level. Self similarities are calculated locally within image regions centred around certain patches using sum of squared sum metrics (SSD).  Applicable also for registering video sequences and image retrieval applications as well as object detection and classification.

[Source:self-adjusted]

[[LSS](http://image.ntua.gr/iva/files/ShechtmanIrani_CVPR2007%20-%20Matching%20Local%20Self-Similarities%20Across%20Images%20and%20Videos.pdf)]: _Shechtman, E. and Irani, M., 2007. Matching Local Self-Similarities across Images and Videos. In CVPR, Vol. 2, pp. 3._

## ORB 

*Oriented FAST and Rotated BRIEF*

The descriptor part of ORB is developed in a similar fashion to BRIEF, yet it also provides additional invariance to rotation and robustness to noise. A rotation-aware version of BRIEF (rBRIEF) is used and then a learning method is applied to choose a good subset of binary tests, identifiying features that have high variance and are uncorrelated.

[Source:self-adjusted]

[[ORB](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.370.4395&rep=rep1&type=pdf)]: _Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011. ORB: An efficient alternative to SIFT or SURF. In ICCV, Vol. 11(1), pp. 2._

## VGG 

An Oxford Visual Geometry Group descriptor trained end to end using "Descriptor Learning Using Convex Optimisation" (DLCO). Indeed, it tackles the problem of learning pooling regions as a convex optimization, i.e. selecting a few regions among a large set of candidate ones. Dimensionality reduction and discrimination of the the descriptor are also solved by learning. Comparable with other state of the art real value and binary descriptors.

[Source:self-adjusted]

[[VGG](https://ieeexplore.ieee.org/document/6718113)]: *Simonyan, K., Vedaldi, A. and Zisserman, A., 2014. Learning local feature descriptors using convex optimisation. _IEEE Transactions on Pattern Analysis and Machine Intelligence_, _36_(8), pp.1573-1585.*


## SIFT

*Scale Invariant Feature Transform*
Image gradients are used  to describe the detected keypoints. Magnitudes and orientations are calculated for 16 subregions around the keypoint on a specific scale and for eight orientations and stored in a 128 element non-binary vector. By normalizing the values,  invariance under certain illumination changes is reassured.

[Source:self-adjusted]

[[SIFT](https://link.springer.com/article/10.1023/B:VISI.0000029664.99615.94)]: _Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. International journal of computer vision, Vol. 60(2), pp.91-110._


## SURF

*Speeded-Up Robust Features*

SURF describes the detected features using Haar wavelets. Responses are calculated for 16 suregions around the detected feature, which are further subdivided, yielding a 64 element descriptor vector for each detected feature. In a similar fashion with SIFT, illumination invariance is achieved. SURF outperforms SIFT in terms of computational complexity.

[Source:self-adjusted]

[[SURF](https://link.springer.com/chapter/10.1007/11744023_32)]: _Bay, H., Tuytelaars, T. and Van Gool, L., 2006. Surf: Speeded up robust features. In European conference on computer vision, pp. 404-417. Springer, Berlin, Heidelberg._


> Written with [StackEdit](https://stackedit.io/).

