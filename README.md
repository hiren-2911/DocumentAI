![detectcols_1](https://github.com/user-attachments/assets/8530e7b6-3f8b-4920-adbd-f76b1bb7831a)

Table Column Detection Using Image Processing and Layout Parser

This project combines the power of deep learning and traditional image processing techniques to accurately detect table columns in document images. It employs a hybrid approach that leverages Layout Parser for table detection and image processing operations for precise column boundary identification.

Objectives

	•	Detect and visualize columns in table images.

Overview of the Approach

	1.	Table Detection:
	•	Use Layout Parser, a deep learning-based library, to detect and crop table regions from the input image.
	2.	Preprocessing:
	•	Edge Removal: Remove horizontal and vertical edges using morphological operations to reduce noise.
	•	Dilation: Dilate the image to group pixels into distinct black-and-white regions for easier column detection.
	3.	Pixel Intensity Analysis:
	•	Analyze pixel intensity across the x-axis to identify column boundaries based on patterns of black (text) and white (gaps).
	4.	Peak Detection:
	•	Detect peaks in the smoothed pixel intensity signal to locate column boundaries.
	5.	Visualization:
	•	Draw vertical lines on the table image to mark detected column boundaries.

Detailed Steps

1. Table Detection

	•	Image Loading: Load the input image using OpenCV or PIL for further processing.
	•	Table Detection with Layout Parser:
	•	Identify and crop table regions using bounding boxes provided by Layout Parser.

2. Preprocessing the Cropped Table Image

	•	Horizontal Edge Removal:
	•	Use a horizontal kernel (e.g., size (30, 1)) with morphological operations to remove horizontal lines.
	•	Vertical Edge Removal:
	•	Use a vertical kernel (e.g., size (1, 30)) to eliminate vertical lines.
	•	Dilation:
	•	Expand white pixels to group nearby pixels into larger chunks, simplifying the column detection process.

3. Pixel Intensity Analysis

	•	Calculate pixel intensity across the x-axis of the table image.
	•	Normalize the intensity values to standardize the signal.
	•	Apply Gaussian smoothing to reduce noise and highlight significant peaks.

4. Peak Detection and Thresholding

	•	Use scipy.signal.find_peaks to detect peaks in the smoothed signal, corresponding to column boundaries.
	•	Apply a threshold to filter out insignificant peaks caused by noise.

5. Visualization

	•	Map the detected peaks to x-coordinates in the image.
	•	Use OpenCV’s cv2.line to draw vertical lines at the detected column boundaries.

Summary of the Approach

	1.	Table Detection: Use Layout Parser to locate and crop table regions.
	2.	Edge Removal: Remove horizontal and vertical lines to reduce noise.
	3.	Dilation: Convert the table into distinct black-and-white regions.
	4.	Pixel Intensity Analysis: Analyze and smooth pixel intensity across the x-axis.
	5.	Peak Detection: Identify column boundaries using peak detection.
	6.	Visualization: Draw vertical lines to mark detected columns.

Technologies Used

	•	Deep Learning: Layout Parser for table detection.
	•	Image Processing: OpenCV for edge removal, dilation, and visualization.
	•	Signal Processing: Scipy for peak detection and Gaussian smoothing.

Results

	•	Clean table images with detected column boundaries visualized as vertical lines.
	•	Accurate and efficient column detection by combining deep learning and image processing.

Future Enhancements

	•	Extend the approach to handle multi-page tables.
	•	Integrate OCR for extracting table content after column detection.

References

	•	Layout Parser Documentation
	•	OpenCV Documentation
	•	Scipy Signal Processing

Feel free to contribute by opening issues or submitting pull requests! 😊
