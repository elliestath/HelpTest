
# Quality Control

As a quality measure of the implemented feature extraction methods, the commonly used in statistics ROC and DET curves are implemented. Ground truth data are expected to be provided by the user.

## ROC Curves

*Receiver Operating Characteristics*

Probability curves, plotting the True Positive (TP) rate against to the false positive (FP). True Positives (y-axis) is defined as the percentage of correct matches over the total number of matches while the False positive (x-axis) is the respective percentage of incorrect matches.

The highest the AUC (Area Under the Curve) index is, the better our results are.

True Positive Rate = TP/(TP+FN)

For more details see
[Google Developers](https://developers.google.com/machine-learning/crash-course/classification/roc-and-auc)

## DET Curves

*Detection Error Trade-off*

Commonly used in classificatio problems, it plots the false negative rate against the false positive rate. The lines shows the trade-off between the above.

> Written with [StackEdit](https://stackedit.io/).
