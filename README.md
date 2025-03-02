VR_Assignment1_Divyansh_Kumar_IMT2022509

Divyansh Kumar IMT2022509

📌 Project Overview

This repository contains solutions for Computer Vision Assignment 1, focusing on two primary tasks:

Coin Detection and Segmentation – Identifying, segmenting, and counting coins in an image using edge detection and the watershed algorithm.

Image Stitching – Creating a panoramic image by stitching multiple overlapping images using feature matching and homography estimation.

All implementations are written in Python.

📂 Repository Structure
VR_Assignment1_Divyansh_Kumar_IMT2022509/
├── Q1/                                   # Coin Detection and Segmentation
│   ├── coin_edge.py                     # Script for coin edge detection and counting
│   ├── coin_segmentation.py             # Script for coin segmentation using watershed
│   ├── coins1.jpg                       # Input image for edge detection
│   ├── coins2.jpeg                      # Input image for segmentation
│   ├── coins_with_edge_detection.jpeg   # Output image with detected coins highlighted
│   ├── Segmented_coins.jpg              # Output image showing segmented coins
│   └── segmented_coin_*.jpg             # Individual images of segmented coins
│
├── Q2/                                   # Image Stitching
│   ├── stitch_panorama.py               # Script for creating stitched panoramas
│   ├── stitch_1.jpg                     # Input image 1 for stitching
│   ├── stitch_2.jpg                     # Input image 2 for stitching
│   ├── stitch_3.jpg                     # Input image 3 for stitching
│   └── final_panorama.jpg               # Output stitched panorama image
│
├── README.md                             # Project documentation
├── requirements.txt                      # List of required Python packages
└── VR_Assignment1_Divyansh_Kumar_IMT2022509.pdf # Final report in PDF format

Dependencies

Ensure the required Python packages are installed before running the scripts. Use the following command:
pip install opencv-python numpy


Execution Instructions

1. Coin Detection and Segmentation

Navigate to the Q1 folder and run the following commands:

python coin_edge.py
python coin_segmentation.py
Expected Outputs:

coins_with_edge_detection.jpeg – Image with detected coin edges highlighted and the total coin count.

Segmented_coins.jpg – Image with segmented coins highlighted.

segmented_coin_*.jpg – Individual images of segmented coins.

2. Image Stitching

Navigate to the Q2 folder and execute the following command:
python stitch_panorama.py
Expected Output:
final_panorama.jpg – The resulting stitched panoramic image.

Methodology

Part 1: Coin Detection and Segmentation

🔹 Steps Implemented:

Edge Detection (coin_edge.py):

Convert the image to grayscale and apply Gaussian blur.

Detect edges using the Canny edge detection algorithm.

Identify circular shapes using the Hough Circle Transform.

Overlay detected circles on the original image and count the coins.

Segmentation (coin_segmentation.py):

Convert the image to grayscale and apply Gaussian blur.

Perform Otsu’s thresholding to create a binary mask.

Apply morphological operations to refine the coin regions.

Use the Distance Transform to distinguish between foreground and background.

Implement the Watershed algorithm to segment and isolate individual coins.

Extract and save each coin as a separate image.

📌 Observations:

Edge Detection provides accurate coin boundary identification but may misidentify overlapping coins or noisy regions.

Segmentation using the Watershed algorithm effectively separates overlapping coins but may require tuning for better accuracy.

Part 2: Image Stitching

🔹 Steps Implemented:

Load the overlapping images.

Convert images to grayscale for feature extraction.

Use SIFT to detect keypoints and compute descriptors.

Match features using a FLANN-based matcher and apply Lowe’s ratio test to filter results.

Compute the homography matrix using RANSAC to align images.

Warp and merge images to generate the panoramic output.

📌 Observations:

Feature Matching using SIFT and FLANN performs reliably when the images have significant overlap and distinct features.

Image Stitching is successful for well-aligned images, though minor misalignments may occur without additional blending techniques.

🎯 Conclusion

This project successfully implements core Computer Vision techniques to:

Detect and segment objects (Coin detection).

Align and stitch images (Panorama creation).

While the results are accurate, future enhancements such as multi-band blending could improve the seamlessness of the stitched images.



