# CSST106-4A-GARCIA

# Hands-On Exploration:

Chosen Real-World AI Application: Lane Detection for autonomous vehicles

``` python
# Import necessary libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a synthetic road image
road_image = np.zeros((256, 512, 3), dtype=np.uint8)

# Draw road lanes (white lines) on the synthetic image
cv2.line(road_image, (100, 256), (180, 0), (255, 255, 255), 5)  # Left lane
cv2.line(road_image, (400, 256), (330, 0), (255, 255, 255), 5)  # Right lane

# Draw a dashed middle line (white dashes)
for i in range(20, 256, 40):
    cv2.line(road_image, (255, i), (255, i + 20), (255, 255, 255), 2)

# Step 1: Convert the image to grayscale
gray_image = cv2.cvtColor(road_image, cv2.COLOR_BGR2GRAY)

# Step 2: Apply Gaussian filter to reduce noise
blurred_image = cv2.GaussianBlur(gray_image, (5, 5), 0)

# Step 3: Use Canny edge detection
edges = cv2.Canny(blurred_image, 50, 150)

# Step 4: Display the original, grayscale, and edge-detected images using plt.subplot
plt.figure(figsize=(10, 6))

# Original Image
plt.subplot(1, 3, 1)
plt.title('Original Image')
plt.imshow(cv2.cvtColor(road_image, cv2.COLOR_BGR2RGB))
plt.axis('off')

# Canny Edge Detected Image
plt.subplot(1, 3, 2)
plt.title('Edge Detection')
plt.imshow(edges, cmap='gray')
plt.axis('off')

# Display all images
plt.tight_layout()
plt.show()


```
![image](https://github.com/user-attachments/assets/65ce1a14-d5ef-46e4-9ee1-861b1d846703)




https://github.com/user-attachments/assets/306ef956-9e2e-4ca3-bd75-d09636e7fe4e


# Introduction to Computer Vision and Image Processing

Computer Vision is a field of AI that enables machines to interpret and analyze visual data from the world.
Image processing plays a critical role by enhancing, manipulating, and preparing images for AI systems to analyze. 
It helps AI systems recognize patterns, detect objects, and understand visual information accurately.

# Types of Image Processing Techniques

1. Filtering: Used to remove noise and improve image quality.
Example: Gaussian filter in medical imaging to enhance clarity.

2. Edge Detection: Identifies object boundaries within images.
Example: Canny edge detection for lane detection in autonomous vehicles.

3. Segmentation: Divides images into regions for better analysis.
Example: Facial feature isolation in facial recognition systems.

# Case Study Overview: Autonomous Vehicles​

In autonomous vehicles, image processing techniques such as edge detection and segmentation are crucial. Edge detection helps recognize road lanes, while segmentation separates road from objects.
These techniques enable real-time visual analysis, helping the vehicle navigate safely. Challenges include dealing with poor lighting conditions and detecting complex road obstacles.​

# Image Processing Implementation: Lane Detection​

The model uses the Canny edge detection algorithm to identify lane markings on the road.​

1. Convert the image to grayscale.​

2. Apply Gaussian filter to reduce noise.​

3. Use Canny edge detection to highlight lane lines.​

This helps the autonomous vehicle maintain its course by recognizing lane boundaries effectively.​

# Conclusion​

Effective image processing is essential for AI systems to analyze and interpret visual data accurately. Through this activity, 
we explored how techniques such as edge detection and segmentation solve real-world AI problems, such as lane detection in autonomous vehicles. 
These methods enable AI to perform tasks that involve complex visual interpretation.​

Emerging Technique: Deep Learning-based Image Analysis​

-Deep learning-based image analysis, such as using convolutional neural networks (CNNs), allows for automatic feature extraction and high-accuracy image recognition.​

-Potential Impact: This technique is likely to revolutionize areas like medical imaging, autonomous navigation, and security systems, offering more precise and scalable solutions for complex visual tasks.​



