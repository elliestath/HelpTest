
# Feature Extraction

## *Keypoint Detectors*

## AGAST

*Adaptive and Generic Accelerated Segment Test.* 

Corner detector. It is an optimization of FAST, thus also based on Accelerated Segment Test (AST), but  its decision tree is generic, with no need to retrain the it every time.


[Source](http://www.i6.in.tum.de/Main/ResearchAgast)

[[AGAST](https://mediatum.ub.tum.de/doc/1287456/file.pdf)]: _Mair, E., Hager, G.D., Burschka, D., Suppa, M. and Hirzinger, G., 2010. Adaptive and generic corner detection based on the accelerated segment test. In European conference on Computer vision, pp. 183-196. Springer, Berlin, Heidelberg._

## AKAZE

*Accelerated KAZE*

In a similar fashion with KAZE, it operates in nonlinear scale space and not in Gaussian like SIFT and SURF do. Numerical methods are used to approximate the solution, namely Fast Explicit Diffusion (FED), that are proven to work much faster than any other discretization scheme.
[Source: self adjusted]

[[AKAZE](http://www.bmva.org/bmvc/2013/Papers/paper0013/abstract0013.pdf)]: _Alcantarilla, P.F., Nuevo, J., Bartoli, A., 2013. Fast explicit diffusion for accelerated features in nonlinear scale spaces. In Proc. BMVC, Vol. 34(7), pp. 1281–1298._

## BRISK

*Binary Robust Invariant Scalable Keypoints*

A sampling pattern consisting of points lying on appropriately scaled concentric circles is applied at the neighborhood of each keypoint to retrieve gray values: processing local intensity gradients,the feature characteristic direction is determined. The oriented BRISK sampling pattern is used to obtain pairwise brightness comparison results which are assembled into the binary BRISK descriptor.

[Source: paper]

[[BRISK](https://www.research-collection.ethz.ch/bitstream/handle/20.500.11850/43288/1/eth-7684-01.pdf)]: _Leutenegger, S., Chli, M. and Siegwart, R., 2011. BRISK: Binary robust invariant scalable keypoints. In 2011 IEEE International Conference on Computer Vision (ICCV), pp. 2548-2555. IEEE._


## FAST

*Features from Accelerated Segment Test*

Modification of the SUSAN corner detector that outperforms previously used detectors in terms of speed and reliability. Is based on Accelerated Segment Test (AST), which is used to distinguish keypoints by examining the intensity values of 16 pixels that fall in the circular pattern around the candidate pixel. A candidate pixel is considered as keypoint if there are at least N continuous pixels that have either higher or lower intensity values than it.

[Source: self adjusted]

[[FAST](https://link.springer.com/chapter/10.1007/11744023_34)]: _Rosten, E. and Drummond, T., 2006. Machine learning for high-speed corner detection. In European conference on computer vision, pp. 430-443. Springer, Berlin, Heidelberg._

## GFTT

*Good Features to Track.* 

Modified version of the traditional Harris detector as to select only the features that pass the dissimilarity (change of appearance) test and filter out the less robust ones.


[Source: self adjusted]

[Good features to track](http://www.ai.mit.edu/courses/6.891/handouts/shi94good.pdf)

[GFTT]: _Harris, C.G. and Stephens, M., 1988. A combined corner and edge detector. In Alvey vision conference, Vol. 15(50), pp. 10-5244._

## KAZE
Operates in nonlinear scale space and not in Gaussian, keeping important image details . The nonlinear scale space is build efficiently by means of Additive Operator Splitting (AOS) scheme.

[Source: self adjusted]

[paper](http://robesafe.com/personal/pablo.alcantarilla/papers/Alcantarilla12eccv.pdf)

[[KAZE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.304.4980&rep=rep1&type=pdf)]: _Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012. KAZE features. In European Conference on Computer Vision, pp. 214-227. Springer, Berlin, Heidelberg._

## MSD

*Maximal Self-Dissimilarity.* 

The algorithm implements a novel interest point detector stemming from the intuition that image patches which are highly dissimilar over a relatively large extent of their surroundings hold the property of being repeatable and distinctive. This concept of "contextual self-dissimilarity" reverses the key paradigm of recent successful techniques such as the Local Self-Similarity descriptor and the Non-Local Means filter, which build upon the presence of similar - rather than dissimilar - patches. Moreover, it extends to contextual information the local self-dissimilarity notion embedded in established detectors of corner-like interest points, thereby achieving enhanced repeatability, distinctiveness and localization accuracy.

[Source: self adjusted]

[[MSD](http://imagine.enpc.fr/~monasse/Stereo/Projects/TombariDiStefano14.pdf)]: _Tombari, F. and Di Stefano, L., 2014. Interest points via maximal self-dissimilarities. In Asian Conference on Computer Vision, pp. 586-600. Springer, Cham._

## MSER

*Maximally Stable Extremal Region Extractor.*

## ORB

*Oriented FAST and Rotated BRIEF*

The algorithm uses FAST in pyramids to detect stable keypoints, selects the strongest features using FAST or Harris response, finds their orientation using first-order moments and computes the descriptors using BRIEF (where the coordinates of random point pairs (or k-tuples) are rotated according to the measured orientation).

[[ORB](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.370.4395&rep=rep1&type=pdf)]: _Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011. ORB: An efficient alternative to SIFT or SURF. In ICCV, Vol. 11(1), pp. 2._

## SIFT

*Scale Invariant Feature Transform*

Detector part of SIFT algorithm uses Difference of Gaussians (DoG), a feature enhancement method, where image pyramids are created by repeatedly convolving the original image with Gaussian kernels. In each pyramid level, every pixel is compared with its 8 neighboring pixels in the current image as well as with its 9 neighbors of its adjacent pyramid images. Keypoints are detected as extrema in the difference between the Gaussian images.

[Source: self adjusted]

[[SIFT](https://link.springer.com/article/10.1023/B:VISI.0000029664.99615.94)]: _Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. International journal of computer vision, Vol. 60(2), pp.91-110._

## STAR

Star Feature Detector derived from CenSurE (Center Surrounded Extrema) detector. STAR is multiscale and works on full spatial resolution, using a bi-level approximation of the Laplacian of Gaussians (LoG) filter and integral images for computational efficiency.

[[CENSURE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.465.1117&rep=rep1&type=pdf)]: _Agrawal, M., Konolige, K. and Blas, M.R., 2008. Censure: Center surround extremas for realtime feature detection and matching. In European Conference on Computer Vision, pp. 102-115. Springer, Berlin, Heidelberg._


## SURF

*Speeded-Up Robust Features*

SURF uses Fast Hessian as a detection method that is based on integral images through Hessian matrix approximation. Box type convolution filters of different sizes are used to approximate second order Gaussian derivatives for each image point. Keypoints are regions where the determinant becomes maximal through non-maximal suppression.

[[SURF](https://link.springer.com/chapter/10.1007/11744023_32)]: _Bay, H., Tuytelaars, T. and Van Gool, L., 2006. Surf: Speeded up robust features. In European conference on computer vision, pp. 404-417. Springer, Berlin, Heidelberg._



## *Keypoint Descriptors*

## AKAZE

*Accelerated KAZE*

A highly efficient Modified-Local Difference Binary (M-LDB) descriptor that exploits gradient and intensity information from the nonlinear scale space. The LDB descriptor follows the same principle as BRIEF, but using binary tests between the aver-age of areas instead of single pixels for additional robustness. M-LDB uses the derivatives computed in the feature detection step, reducing the number of operations required to construct the descriptor.

[[AKAZE](http://www.bmva.org/bmvc/2013/Papers/paper0013/abstract0013.pdf)]: _Alcantarilla, P.F., Nuevo, J., Bartoli, A., 2013. Fast explicit diffusion for accelerated features in nonlinear scale spaces. In Proc. BMVC, Vol. 34(7), pp. 1281–1298._

## BRIEF

*Binary Robust Independent Elementary Features*

A short binary descriptor using the hamming distance.
Not invariant to scale and rotation.

[[BRIEF](https://ieeexplore.ieee.org/abstract/document/6081878)]: _Calonder, M., Lepetit, V., Ozuysal, M., Trzcinski, T., Strecha, C. and Fua, P., 2011. BRIEF: Computing a local binary descriptor very fast. IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol. 34(7), pp.1281-1298._

## BRISK

*Binary Robust Invariant Scalable Keypoints*


[[BRISK](https://www.research-collection.ethz.ch/bitstream/handle/20.500.11850/43288/1/eth-7684-01.pdf)]: _Leutenegger, S., Chli, M. and Siegwart, R., 2011. BRISK: Binary robust invariant scalable keypoints. In 2011 IEEE International Conference on Computer Vision (ICCV), pp. 2548-2555. IEEE._

## DAISY
Feature descriptor that depends on histograms of gradients like SIFT but uses a Gaussian weighting and circularly symmetrical kernel.

[[DAISY](https://ieeexplore.ieee.org/abstract/document/4815264)]: _Tola, E., Lepetit, V. and Fua, P., 2009. Daisy: An efficient dense descriptor applied to wide-baseline stereo. IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol. 32(5), pp. 815-830._

## FREAK

*Fast Retina Keypoint*

The algorithm propose a novel keypoint descriptor inspired by the human visual system and more precisely the retina. A cascade of binary strings is computed by efficiently comparing image intensities over a retinal sampling pattern. FREAK keypoints are in general faster to compute with lower memory load and also more robust than SIFT, SURF or BRISK. They are competitive alternatives to existing keypoints in particular for embedded applications.

[[FREAK](https://ieeexplore.ieee.org/abstract/document/6247715)]: _Alahi, A., Ortiz, R. and Vandergheynst, P., 2012. Freak: Fast retina keypoint. In 2012 IEEE Conference on Computer Vision and Pattern Recognition, pp. 510-517. IEEE._

## HOG

*Histogram of Oriented Gradients*

Based on image gradients, histograms of gradients are calculated for pre-defiend image sub-regions. Mainly used for pedestrian detection, sensitive to rotation changes.


## KAZE

[[KAZE](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.304.4980&rep=rep1&type=pdf)]: _Alcantarilla, P.F., Bartoli, A. and Davison, A.J., 2012. KAZE features. In European Conference on Computer Vision, pp. 214-227. Springer, Berlin, Heidelberg._

## LATCH

*Learned Arrangements of Three Patch Codes*

LATCH is a binary descriptor based on learned comparisons of triplets of image patches.

[[LATCH](https://arxiv.org/pdf/1501.03719.pdf)]: _Levi, G. and Hassner, T., 2016. LATCH: learned arrangements of three patch codes. In 2016 IEEE winter conference on applications of computer vision (WACV), pp. 1-9. IEEE._

## LUCID

*Locally Uniform Comparison Image Descriptor*

[[LUCID](https://papers.nips.cc/paper/4706-locally-uniform-comparison-image-descriptor.pdf)]: _Ziegler, A., Christiansen, E., Kriegman, D. and Belongie, S.J., 2012. Locally uniform comparison image descriptor. In Advances in Neural Information Processing Systems, pp. 1-9._

## LSS

*Local Self-Similarity*

Local Self-Similarity is based on the texture features of images to densely calculate local self-similarity descriptors.

[[LSS](http://image.ntua.gr/iva/files/ShechtmanIrani_CVPR2007%20-%20Matching%20Local%20Self-Similarities%20Across%20Images%20and%20Videos.pdf)]: _Shechtman, E. and Irani, M., 2007. Matching Local Self-Similarities across Images and Videos. In CVPR, Vol. 2, pp. 3._

## ORB

*Oriented FAST and Rotated BRIEF*

As the name declares combines FAST for feature detection and BRIEF for feature description, providing invariance to rotation and robustness to noise.

[[ORB](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.370.4395&rep=rep1&type=pdf)]: _Rublee, E., Rabaud, V., Konolige, K. and Bradski, G.R., 2011. ORB: An efficient alternative to SIFT or SURF. In ICCV, Vol. 11(1), pp. 2._

## SIFT

*Scale Invariant Feature Transform*

Image gradients are used  to describe the detected keypoints. Intensity values, gradient magnitude and orientation are stored, reassuring also a certain level of invariance under illumination changes.

[[SIFT](https://link.springer.com/article/10.1023/B:VISI.0000029664.99615.94)]: _Lowe, D.G., 2004. Distinctive image features from scale-invariant keypoints. International journal of computer vision, Vol. 60(2), pp.91-110._


## SURF

*Speeded-Up Robust Features*

The description part of SURF describes the intensity of the neighborhood around the pixel using Haar wavelets.

[[SURF](https://link.springer.com/chapter/10.1007/11744023_32)]: _Bay, H., Tuytelaars, T. and Van Gool, L., 2006. Surf: Speeded up robust features. In European conference on computer vision, pp. 404-417. Springer, Berlin, Heidelberg._


> Written with [StackEdit](https://stackedit.io/).
