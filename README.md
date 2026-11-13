# 🖼️ Digital Image Processing & Computer Vision Pipeline (ELE 261)

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/Vision-OpenCV%20%7C%20SciPy-5C3EE8.svg)](https://opencv.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A comprehensive, modular digital image processing and computer vision pipeline authored by **Ammar Abdelfattah & Project Team** at the **Faculty of Engineering – New Ismailia National University (NINU)**.

---

## 📌 Pipeline Capabilities & Modules

The pipeline covers 6 fundamental computer vision modules with full theoretical formulations and interactive visualizations:

1. **Intensity Transformations & Point Processing**:
   - Power-law ($\gamma$-correction: $s = c \cdot r^\gamma$) for non-linear dynamic range adjustment.
   - Logarithmic transformation ($s = c \log(1 + r)$) for Fourier magnitude spectrum visualization.
   - Photographic negative mapping.

2. **Contrast Enhancement & Histogram Manipulation**:
   - Global Histogram Equalization (GHE).
   - Contrast Limited Adaptive Histogram Equalization (**CLAHE**) preventing noise over-amplification in uniform regions.

3. **Spatial Filtering & Edge Detection**:
   - Linear smoothing filters (Gaussian blur, Box filter).
   - Order-statistic non-linear filtering (Median filter for salt-and-pepper noise removal).
   - Second-order derivative sharpening with Laplacian ($\nabla^2 f$).
   - Multi-stage gradient edge detectors (Sobel gradient magnitude $G = \sqrt{G_x^2 + G_y^2}$ and Canny edge detector with non-maximum suppression and hysteresis).

4. **Frequency Domain Enhancement (2D FFT)**:
   - 2D Fast Fourier Transform and centered DC spectrum.
   - Butterworth Low-Pass (BLPF) and High-Pass (BHPF) filters with configurable order $n$ and cutoff frequency $D_0$:
     $$H(u, v) = \frac{1}{1 + \left[ \frac{D(u, v)}{D_0} \right]^{2n}}$$

5. **Morphological Operations & Segmentation**:
   - Structuring element kernels (Dilation, Erosion, Opening, Closing).
   - Otsu's optimal inter-class variance automatic thresholding.
   - Connected Component Analysis (CCA) with centroid labeling.

6. **Capstone: Automated Defect Inspection**:
   - End-to-end industrial inspection identifying crack/surface flaws.
   - Quantitative profiling: bounding boxes, defect area, perimeter, and circularity metrics.

---

## 📁 Repository Structure

```text
├── Digital_Image_Processing_Project.ipynb  # Interactive step-by-step pipeline notebook
├── Documentation.md                       # Comprehensive theoretical formulations
├── ammar_abdelfattah_cifar10_cnn_report.pdf # Course project report
├── requirements.txt                       # Dependencies
└── README.md                              # Project documentation
```

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/marbdalftah72-spec/CNN.git
cd CNN

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook Digital_Image_Processing_Project.ipynb
```

---

## 👨‍💻 Authors & Academic Attribution

- **Ammar Abdelfattah & Project Team**
- Department of Computer Engineering, Faculty of Engineering
- **New Ismailia National University (NINU)**
