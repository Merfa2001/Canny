# Canny
```markdown
# Canny Edge Detector from Scratch

A Python implementation of the Canny edge detection algorithm without using high-level libraries (e.g., OpenCV's `Canny` function). This project demonstrates the step-by-step process of edge detection, including Gaussian smoothing, gradient computation, non-maxima suppression, and hysteresis thresholding.

![Sample Input](https://i.imgur.com/4.tif) | ![Canny Edges](https://i.imgur.com/canny_edges.jpg)
:-------------------------:|:-------------------------:
**Input Image**            | **Detected Edges**

---

## Table of Contents
- [Key Features](#key-features)
- [Installation](#installation)
- [Usage](#usage)
- [Parameters](#parameters)
- [Dependencies](#dependencies)
- [Comparison with OpenCV](#comparison-with-opencv)
- [License](#license)

---

## Key Features
- **Step-by-Step Implementation**:
  - Gaussian smoothing to reduce noise.
  - Sobel operators for gradient computation.
  - Non-Maxima Suppression (NMS) for thinning edges.
  - Hysteresis thresholding to detect strong and weak edges.
- **Customizable Thresholds** for fine-tuning edge detection.
- **Comparison** with OpenCV's built-in `Canny` function.

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/canny-edge-detector.git
   cd canny-edge-detector
   ```
2. Install dependencies:
   ```bash
   pip install opencv-python numpy matplotlib
   ```

---

## Usage
Run the Canny edge detector on an input image:
```bash
python canny_edges.py --input path/to/your/image.jpg --output edges.jpg
```

### Parameters
| Argument    | Description                          | Default       |
|-------------|--------------------------------------|---------------|
| `--input`   | Path to the input image.             | **Required**  |
| `--low`     | Low threshold for hysteresis.        | `30`          |
| `--high`    | High threshold for hysteresis.       | `90`          |
| `--output`  | Path to save the output edges.       | `edges.jpg`   |

---

## Results
The script generates:
1. **Gaussian-smoothed image** (`smoothed.jpg`).
2. **Non-maxima suppressed edges** (`suppressed.jpg`).
3. **Final Canny edges** (`edges.jpg`).

To visualize intermediate results:
```python
# Display results (example)
import matplotlib.pyplot as plt
smoothed = cv2.imread('smoothed.jpg', 0)
edges = cv2.imread('edges.jpg', 0)
plt.subplot(121), plt.imshow(smoothed, cmap='gray'), plt.title('Smoothed Image')
plt.subplot(122), plt.imshow(edges, cmap='gray'), plt.title('Canny Edges')
plt.show()
```

---

## Parameters
- **Low Threshold**: Detects weak edges. Increase to reduce noise.
- **High Threshold**: Detects strong edges. Decrease to capture finer details.
- **Default Values**: `low=30`, `high=90` (adjust based on your image).

---

## Dependencies
- Python 3.6+
- OpenCV (`opencv-python`)
- NumPy
- Matplotlib (for visualization)

---

## Comparison with OpenCV
The custom implementation matches OpenCV's `Canny` function when using identical thresholds. To compare:
```python
# Run OpenCV's Canny
opencv_edges = cv2.Canny(image, low_threshold, high_threshold)
cv2.imwrite('opencv_edges.jpg', opencv_edges)
```

![Custom vs OpenCV](https://i.imgur.com/canny_edges.jpg) | ![OpenCV](https://i.imgur.com/opencv_canny.jpg)
:-------------------------:|:-------------------------:
**Custom Implementation**  | **OpenCV Canny**

---

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

**Contributions welcome!** Feel free to open issues or submit pull requests.
``` 

This `README.md` provides a clear overview of the project, installation steps, usage examples, and visual comparisons. Customize the image paths and GitHub links as needed.
