
# Stereo Matching and Disparity Computation

## Introduction

Stereo matching is a technique in computer vision that determines the depth of objects in a scene by comparing two images taken from slightly different viewpoints. The difference in the position of the same object in the two images is called disparity. The disparity map can then be used to reconstruct the 3D structure of the scene.

## Problem Description

In this project, we aim to compute the disparity map from a pair of stereo images (left and right images). The disparity map highlights the differences in pixel positions of the same object in the two images. This difference is then used to estimate the depth information of objects in the scene.

## Steps Involved

1. **Preprocessing:**
   - Convert the input images to grayscale (if they are not already).
   - Normalize the images for consistent intensity values.

2. **Computing Cost Volume:**
   - For each pixel in the left image, find the corresponding pixel in the right image by shifting along the horizontal axis.
   - Compute the cost (e.g., sum of absolute differences) for each disparity level and store it in the cost volume.

3. **Cost Aggregation using Integral Images:**
   - Use integral images to efficiently compute the sum of costs over a rectangular window.
   - This helps in smoothing the cost volume and reducing noise.

4. **Disparity Computation:**
   - For each pixel, find the disparity value that minimizes the aggregated cost.
   - Create the disparity map by assigning each pixel its corresponding disparity value.

5. **Post-Processing (Optional):**
   - Apply filtering techniques to refine the disparity map and reduce artifacts.

## Repository Structure

```

## How to Use

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Dovanvu09/Stereo-Matching.git
   cd Stereo-Matching
   ```

2. **Run the Disparity Computation:**

   Ensure you have the necessary libraries installed. You can install them using `pip`:

   ```bash
   pip install numpy opencv-python
   ```

   Execute the script to compute the disparity map:

   ```bash
   python src/compute_disparity.py --left images/left.png --right images/right.png
   ```

3. **Visualize the Results:**

   The resulting disparity map will be saved in the `images` folder. You can use any image viewer to see the output.

## Example Results

| Left Image | Right Image | Disparity Map |
|------------|--------------|---------------|
| ![Left](images/left.png) | ![Right](images/right.png) | ![Disparity](images/disparity.png) |

## Conclusion

This project demonstrates the basic steps involved in computing a disparity map from a pair of stereo images. The disparity map provides valuable depth information that can be used in various applications, including 3D reconstruction, robotics, and autonomous driving.

## References

- [Stereo Matching Wikipedia](https://en.wikipedia.org/wiki/Stereo_matching)
- [OpenCV Documentation](https://docs.opencv.org/)
- [Integral Images](https://en.wikipedia.org/wiki/Summed-area_table)

