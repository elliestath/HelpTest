# Preprocessing
This step offers the option to use image enhancement techniques that could potentially facilitate the detection of robust image features.

**PARAMETERS**

Full Image Size/Max Image Size

## Decolorization
Contrast Preserving Decolorization

## ACEBSF

*Adaptive Contrast Enhancement Based on modified Sigmoid Function.* 

It first improves the poor quality images using a modified sigmoid function and then applies contrast limited adaptive histogram equalization (AHE) to enhance image contrast.

*Parameters*

 - Blocksize (Width: 8/Height: 8)
 - L: 0.3
 - K1: 10
 - K2: 0.50

[ACEBSF]: _Lal, S. and Chandra, M., 2014. Efficient algorithm for contrast enhancement of natural images. International  Arab Journal of Information Technology, Vol. 11(1), pp. 95-102._

## CLAHE

*Contrast Limited Adaptive Histogram Equalization.*

CLAHE is a local contrast enhancement technique robust to outliers. Local contrast enhancement methods such as adaptive histogram equalization (AHE) divide the original image into several non-overlapped sub-blocks and apply histogram equalization accordingly. CLAHE is an improvement of AHE and performs well on low contrast images.

*Parameters*

 - Clip Limit: 40
 - Tiles Size X: 8
 - Tiles Size Y: 8

[CLAHE]: _Zuiderveld, K., 1994. Contrast limited adaptive histogram equalization. In Graphics gems, Vol. IV, pp. 474-485. Academic Press Professional, Inc._


[Source](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3092044/) 

## CMBFHE

*Cascaded Multistep Binomial Filtering Histogram Equalization.*

Based on the POSHE approach using cascaded multistep binomial filtering histogram equalization to reduce algorithm complexity. Similar to other local adaptive techniques, it exploits image sub-blocks (and not pixels), achieving results with effect similar to the application of a low-pass filter (LPF) avoiding the blocking effect.

*Parameters*

 - Block Size (Width: 11/Height: 11)

[CMBFHE]: _Lamberti, F., Montrucchio, B. and San, A., 2006. CMBFHE: a novel contrast enhancement technique based on cascaded multistep binomial filtering histogram equalization.  IEEE Transactions on Consumer Electronics, Vol. 52(3), pp.966-974._

[POSHE]: _Kim, J.Y., Kim, L.S. and Hwang, S.H., 2001. An advanced contrast enhancement using partially overlapped sub-block histogram equalization. IEEE Transactions on Circuits and Systems for Video Technology, Vol. 11(4), pp. 475-484._

## DHE

*Dynamic Histogram Equalization.*

Traditional histogram equalization employing a histogram partitioning operation to avoid dominating components and achieving better overall contrast enhancement with controlled dynamic range of gray levels while also reassuring minimum detail loss.

*Parameters*

 - x: 1

[DHE]: _Abdullah-Al-Wadud, M., Kabir, M.H., Dewan, M.A.A. and Chae, O., 2007. A dynamic histogram equalization for image contrast enhancement. IEEE Transactions on Consumer Electronics, Vol. 53(2), pp. 593-600._

## FAHE

*Fast implementation of Adaptive Histogram Equalization* 

Software techniques are used on histogram acquisition and accumulation as well on the block size decision  to reduce computational complexity.

*Parameters*

 - Block Size (Width: 11/Height: 11)

[FAHE]: _Wang, Z. and Tao, J., 2006. A fast implementation of adaptive histogram equalization. In 2006 8th international Conference on Signal Processing, Vol. 2. IEEE._

## HMCLAHE

*Histogram Modified Contrast Limited Adaptive Histogram Equalization.*

It incorporates both histogram modifications as an optimization technique and CLAHE. It controls the level of contrast enhancement, before CLAHE, resulting a strong contrast image with enhanced details.

*Parameters*

 - Block Size (Width: 11/Height: 11)
 - L: 0.03
 - Phi: 0.50

[HMCLAHE]: _Sundaram, M., Ramar, K., Arumugam, N. and Prabin, G., 2011. Histogram based contrast enhancement for mammogram images. In 2011 International Conference on Signal Processing, Communication, Computing and Networking Technologies, pp. 842-846. IEEE._

## LCE-BSESCS

*Local Contrast Enhancement Utilizing Bidirectional Switching Equalization of Separated and Clipped Sub-histograms.*

Similar to other local HE, it aims to enhance the local contrast and increase simultaneously the sharpness of the image, while avoiding noise and artefacts, recommended especially when uneven illumination conditions are met.

*Parameters*

 - Block Size (Width: 33/Height: 33)
 
 
[LCE-BSESCS]: _Ibrahim, H. and Hoo, S.C., 2014. Local contrast enhancement utilizing bidirectional switching equalization of separated and clipped subhistograms. Mathematical Problems in Engineering._

## MSRCP

*Multiscale Retinex with Chromaticity Preservation.*

Based on the original Multiscale Retinex method, it applies some modifications on the post-processing steps and preserves image chromaticity. Recommended for images with a correct color distribution and white lightning.

*Parameters*

 - Retinex Scales
 - Small scale: 10
 - Mid Scale: 100
 - Large scale: 220

[MSRCP]: _Petro, A.B., Sbert, C. and Morel, J.M., 2014. Multiscale retinex. Image Processing On Line, pp.71-88._

## NOSHP

*Non-Overlapped Sub-blocks and local Histogram Projection.*

To reduce computational complexity, it segments the image into non-overlapped sub-blocks where the histogram projection (HP) is then executed individually. Subsequently, each sub-block is related to its adjacent three ones by certain weights, so that the integral image and local details can be enhanced.

*Parameters*

 - Block Size (Width: 127/Height: 127)

[NOSHP]: _Liu, B., Jin, W., Chen, Y., Liu, C. and Li, L., 2011. Contrast enhancement using non-overlapped sub-blocks and local histogram projection. IEEE Transactions on Consumer Electronics, Vol. 57(2), pp. 583-588._

## POHE

*Parametric-oriented histogram equalization (POHE)*

Local enhancement method using integral images to reduce computational time during the construction of the probability distribution function and the transformation function.

*Parameters*

 - Block Size (Width: 127/Height: 127)

[POHE]: _Liu, Y.F., Guo, J.M., Lai, B.S. and Lee, J.D., 2013. High efficient contrast enhancement using parametric approximation. In 2013 IEEE International Conference on Acoustics, Speech and Signal Processing, pp. 2444-2448. IEEE._

## RSWHE

*Recursively Separated and Weighted Histogram Equalization.*

It segments an input histogram into two or more sub-histograms recursively, modifies them using a weighting process based on a normalized power law function, and performs HE on the weighted sub-histograms independently, achieving brightness preservation and image contrast enhancement.

[RSWHE]: _Kim, M. and Chung, M.G., 2008. Recursively separated and weighted histogram equalization for brightness preservation and contrast enhancement. IEEE Transactions on Consumer Electronics, Vol., 54(3), pp. 1389-1397._


## Wallis Filter

Locally adaptive contrast adjustment filter to enhance image gray-scale details. It ensures that within every specified window, the local mean and the standard deviation will match some given (user-specified) values. Recommended to eliminate uneven illumination, where bright and dark tones are both present.

*Parameters*

 - Contrast: 1
 - Brightness: 0.20
 - Imposed Average: 41
 - Imposed Local StdDev: 127
 - Kernel Size: 50


[Source](https://www.microimages.com/documentation/TechGuides/55Wallis.pdf)



> Written with [StackEdit](https://stackedit.io/).
