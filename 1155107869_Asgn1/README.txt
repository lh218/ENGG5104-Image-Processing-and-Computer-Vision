Task 1: High-pass Filter with Fourier Transform

In this question, two core functions are needed: np.fft.fft2 and np.fft.fftshift, which apply fourier transform and shifting on frequency domain. After shifting, we can implement high-pass filter by masking the low frequency domain, right in the middle of transformed image. 

Then we can apply inverse fourier transform to recover the image.

Task 2: Image Affine Transformation

In this question, two core functions in openCV are needed: cv2.getRotationMatrix2D and cv2.getAffineTransform. We are required to implement rotation, scaling and moving transformations. 

However, as mentioned in hints, the coordinates of cv2 and the real images are different, it made us change the rotation center from upper right to middle before rotating and scaling, otherwise the rotation center would be the upper right point. Then we can apply affine transformations to get the right image.

Task 3: Local Histogram Equalization

In this question, two core functions in openCV are needed: cv2.equalizeHist and cv2.createCLAHE, which apply histogram equalization and local histogram equalization. 

The main idea of those two methods are: finding the cdf of pixels' intensity, then adjusting the new distribution of intensity according to cdf, while the local histogram equalization seeks intensity information from the neighborhood of every pixels. In implementation, since those two equalization is applied to gray image, so we need to convert the color image to gray image at first.

Task 4: Line Detection with Hough Transform

In this question, three core functions are needed according to three main steps: cv2.GaussianBlur will convert the image to gray and process with Gaussian blur for edge detection, cv2.Canny performs Canny edge detection to detect the edges, then cv2.HoughLines (we choose cv2.HoughLinesP in this task) will find the lines in the edge sets. 

The parameters in this function, such as threshold, minLineLength and maxLineGap are highly related to the final results, and we can find 
the best images by adjusting them. After finding all the lines, we can draw the lines and add the lines to the original image by cv2.lines and cv2.addWeighted.

Task 5: Joint Bilateral Filter

In this question, two core functions are needed: cv2.bilateralFilter and cv2.ximgproc.jointBilateralFilter, respectively implement Bilateral Filter and Joint Bilateral Filter to the original image. The main difference between those two filters is that Joint Bilateral Filter needs a guidance image to provide the intensity information, while the Bilateral Filter just makes image smooth by averaging the intensity in every pixels according to their neighborhoods.

We can also use cv2.addWeighted function to observe the difference of those two filters.
