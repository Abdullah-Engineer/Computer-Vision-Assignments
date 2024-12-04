# Computer-Vision-Assignments
This repository contains the solutions to two assignments from the Computer Vision course.

<h1> Assignment 1: Hybrid Filter</h1>

<h3>Problem Statement:</h3>
In this assignment, we were tasked with creating a hybrid image by combining two images (representing group members) using low-pass and high-pass filters. The goal was to create an image that, when viewed from a distance, looks like one person, but when viewed up close, reveals the features of the other person.

<h3>Solution:</h3>
To solve this problem, I used the following approach:

<h4>Image Preprocessing:</h4>
I started by uploading two images of the group members.
The images were resized to a standard size (500x500 pixels) for consistency.

<h4>Applying Filters:</h4>
<ul>
<li>A low-pass filter was applied to the first image (using Gaussian blur) to smooth out high-frequency details, leaving only the low-frequency information (general shapes).</li>
<li>A high-pass filter was applied to the second image by subtracting a blurred version of the image from the original, which removed low-frequency details and retained the high-frequency components (edges and fine details).</li>
</ul>

<h4>Combining the Filters:</h4>
The low-pass and high-pass images were then combined using a weighted sum, creating the final hybrid image.

<h4>Result:</h4>
The final image was displayed, showing both original images, the low-pass filtered image, the high-pass filtered image, and the resulting hybrid image.
This process created an image where one person’s features dominate at a distance, while the other’s details are revealed up close.


<h1>Assignment 2: Harris Corner Detection Algorithm</h1>
This assignment is about the implementation of the Harris Corner Detection Algorithm. The task was to manually implement the algorithm to detect corners in an image without using built-in corner detection functions.

<h3>Objective</h3>
The objective of this assignment was to detect corners in an image using the Harris Corner Detection algorithm. Corners are points in an image where intensity changes significantly in multiple directions. These points are useful in various computer vision applications, including object recognition, image alignment, and tracking.

<h3>Implementation Details</h3>
The algorithm was implemented step by step, as outlined below:

<h4>Image Gradients Calculation</h4>
<ul>
<li>Gradients represent the rate of intensity change in an image.</li>
<li>The Sobel operator was used to calculate:</li>
  <li><p class="equation">Horizontal Gradient (I<sub>x</sub>): Detects intensity changes in the x-direction.</p></li>
  <li><p class="equation">Vertical Gradient (I<sub>y</sub>): Detects intensity changes in the y-direction.</p></li>
</ul>
  
<h4>Gradient Products</h4>
The gradients were combined into second-order derivatives:
<ul>
<li><p class="equation">I<sub>xx</sub> = I<sub>x</sub><sup>2</sup>: Measures horizontal variations.</p></li>
<li><p class="equation">I<sub>yy</sub> = I<sub>y</sub><sup>2</sup>: Measures vertical variations.</p></li>
<li><p class="equation">I<sub>xy</sub> = I<sub>x</sub> &middot; I<sub>y</sub>: Measures cross variations.</p></li>
</ul>


<h4>Smoothing</h4>
The gradient products were smoothed using a Gaussian filter to reduce noise and ensure the detection is robust.


<h4>Harris Response Calculation</h4>
The Harris response for each pixel was computed using the formula:

<p class="equation">R = det(M) − k &middot; (trace(M))<sup>2</sup></p> 
<p>Where:</p> 
<ul> 
  <li class="equation">det(M) = I<sub>xx</sub> &middot; I<sub>yy</sub> − I<sub>xy</sub><sup>2</sup>: Measures the determinant of the gradient matrix.</li> 
  <li class="equation">trace(M) = I<sub>xx</sub> + I<sub>yy</sub>: Measures the sum of the diagonal elements of the gradient matrix.</li> <li class="equation">k = 0.04: A constant that controls sensitivity.
  </li> </ul>



<h4>Thresholding and Corner Marking</h4>
A threshold was applied to the Harris response values to identify strong corners.
Pixels with a response value above the threshold were marked as corners.
These corners were highlighted in red on the original image for visualization.


<h4>Results</h4>
The code produces the following outputs:
<ul>
  <li>Original Image: The input image uploaded by the user.</li>
  <li>Harris Response: A heatmap representing the corner strength at each pixel.</li>
  <li>Corners Detected: The original image with detected corners marked in red.</li>
</ul>



<h1>Conclusion</h1>
The first assignment introduced me to image filtering techniques and how different filters can be combined to create hybrid images. The second assignment is the implementation of the Harris Corner Detection algorithm demonstrates the process of identifying corners in images, enhancing understanding of key computer vision concepts like gradients and feature detection. It serves as a solid foundation for exploring more advanced techniques.








