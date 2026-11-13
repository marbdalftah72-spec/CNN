# 🖼️ Project Documentation: Digital Image Processing Pipeline (ELE 261)
**Author**: Ammar Abdelfattah & Project Team  
**Institution**: Faculty of Engineering – New Ismailia National University (NINU)  
**Academic Year**: 2026/2027  

---

## 1. Project Overview & Scope
This project presents a comprehensive, modular computer vision and digital image processing pipeline built in accordance with the NINU ELE 261 syllabus. The project establishes theoretical formulation, algorithmic implementation, and empirical verification across six key modules:
1. **Intensity Transformations & Point Processing**: Dynamic range adaptation (Negative, Power-law $\gamma$-correction, Logarithmic transformations).
2. **Contrast Enhancement & Histogram Manipulation**: Global Histogram Equalization (GHE) vs. Contrast Limited Adaptive Histogram Equalization (CLAHE).
3. **Spatial Filtering & Convolution**: Linear smoothing (Gaussian, Box), Non-linear order-statistic filtering (Median for impulse/salt-and-pepper noise), Sharpening (Laplacian $\nabla^2 f$), and Edge Detection (Sobel $G_x, G_y$, Canny).
4. **Frequency Domain Image Enhancement**: 2D Fast Fourier Transform (2D FFT), centering DC spectrum, Butterworth Low-pass (BLPF) and High-pass (BHPF) filtering.
5. **Mathematical Morphology & Segmentation**: Binary/Grayscale operations (Dilation, Erosion, Opening, Closing), Otsu's optimal variance thresholding, Connected Component Analysis (CCA).
6. **Automated Inspection Capstone**: End-to-end defect and dimensional feature profiling with bounding boxes, area, perimeter, and circularity metrics.

---

## 2. Mathematical Formulations

### 2.1 Point Transformations
- **Power-Law (Gamma)**: $s = c \cdot r^\gamma$  
  For $\gamma < 1$, dark values are mapped into higher output values (enhancing under-exposed shadows). For $\gamma > 1$, bright regions are compressed.
- **Log Transformation**: $s = c \cdot \log(1 + r)$  
  Expands dark pixel intensities while compressing high dynamic range peaks (ideal for Fourier magnitude spectra).

### 2.2 Histogram Equalization
Given an image with $L$ gray levels and total pixels $n$:
$$p_r(r_k) = \frac{n_k}{n}, \quad s_k = T(r_k) = (L - 1) \sum_{j=0}^{k} p_r(r_j)$$
GHE maps the cumulative distribution function (CDF) to a linear uniform distribution, maximizing image entropy.

### 2.3 Frequency Domain Filtering (Butterworth)
For an image of size $M \times N$ shifted to frequency center $(u_0, v_0)$:
$$D(u, v) = \sqrt{(u - u_0)^2 + (v - v_0)^2}$$
- **Butterworth Low-Pass Filter (BLPF)**:
  $$H_{LP}(u, v) = \frac{1}{1 + \left(\frac{D(u, v)}{D_0}\right)^{2n}}$$
- **Butterworth High-Pass Filter (BHPF)**:
  $$H_{HP}(u, v) = \frac{1}{1 + \left(\frac{D_0}{D(u, v)}\right)^{2n}}$$

---

## 3. Comparative Experimental Results

| Technique | Primary Strengths | Computational Complexity | Best Use Case |
|---|---|---|---|
| **Box / Mean Filter** | Linear, highly vectorized | $O(k^2)$ per pixel | Uniform background smoothing |
| **Gaussian Filter** | Rotationally symmetric, preserves edges better than mean | $O(k)$ separable | Preprocessing for Canny/Sobel edge detection |
| **Median Filter** | Preserves sharp step edges, eliminates outliers | $O(k^2 \log k)$ | Salt-and-pepper impulse noise removal |
| **Global HE** | Maximizes contrast across whole image | $O(N)$ | Under-exposed or washed-out images with unimodal histograms |
| **CLAHE** | Prevents noise amplification in flat regions | $O(N \cdot B)$ | Medical X-rays, unevenly illuminated outdoor scenes |
| **Otsu Threshold** | Zero manual tuning, maximizes inter-class variance $\sigma_B^2$ | $O(L)$ where $L=256$ | Bi-modal foreground/background segmentation |

---

## 4. Execution Guide
To run the interactive notebook:
```bash
jupyter notebook Digital_Image_Processing_Project.ipynb
```
Dependencies:
```bash
pip install -r requirements.txt
```
