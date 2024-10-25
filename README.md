# WhiteBlood-Cells
Image Preprocessing and IoU Calculation - Feature Extraction and Classification


This project involves an image processing and machine learning pipeline aimed at classifying types of blood cells using microscopy images. The overall workflow has two main phases:

Phase I: Image Preprocessing and IoU Calculation
Directory Loading: The program reads and organizes images from two directories – one with processed images and another containing ground truth (reference) images.
Preprocessing: For each image, the contrast and brightness are adjusted, and various filters (median, Gaussian blur, etc.) are applied to reduce noise and enhance features.
Color Segmentation: The program identifies purple-colored pixels, which are likely blood cells, using HSV color thresholding.
Morphological Transformations: Open, close, erosion, and dilation transformations are applied to clean the binary mask.
IoU (Intersection over Union) Calculation: The segmented cells are compared to the ground truth images to calculate an IoU score for each image, reflecting the accuracy of cell segmentation.





Phase II: Feature Extraction and Classification
Feature Extraction: Using regionprops from the skimage library, geometrical properties of the segmented cells are extracted, such as area, eccentricity, solidity, perimeter, and Euler number.
Class Labeling: Blood cell types (e.g., basophils, monocytes, lymphocytes, etc.) are labeled based on the image file path.
Data Aggregation: The extracted features are consolidated into a DataFrame for all images, and classes are labeled for training.
Classification Using SVM
Label Encoding: Blood cell types are converted into numerical labels.
SVM Training: An SVM classifier with a linear kernel is trained on 80% of the data, while 20% is held out for testing.
Accuracy Calculation: The classifier’s accuracy on the test set is calculated and printed.
Results
The project outputs the overall classification accuracy of the SVM model and the average IoU score for image segmentation accuracy.

This pipeline combines image processing techniques for feature extraction with machine learning classification, providing a practical approach for cell type classification based on microscopy image segmentation.






