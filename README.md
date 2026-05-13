# CT Image Denoising using U-Net (Deep Learning)

## Overview
This project presents a deep learning-based approach for denoising low-dose CT images using a U-Net architecture. The model is trained to reconstruct high-quality CT images from synthetically corrupted inputs, simulating realistic low-dose imaging conditions.

The pipeline is designed to reflect a research-oriented workflow, including data preprocessing, noise simulation, patch-based learning, and full-image reconstruction.

---

## Problem Statement
Reducing radiation exposure in CT imaging (low-dose CT) introduces significant noise, which degrades diagnostic quality. The objective of this project is to develop a deep learning model capable of restoring image quality while preserving anatomical structures.

---

## Methodology

### 1. Data Preparation
- CT images loaded in TIFF format  
- Min-Max normalization applied to scale intensities to [0, 1]

### 2. Noise Simulation
- Additive Gaussian noise applied to simulate low-dose CT conditions  

### 3. Patch-Based Learning
- Images divided into **64×64 patches**
- **Overlapping patch extraction (50% stride)** used to improve spatial consistency and reduce boundary artifacts  

### 4. Model Architecture
- U-Net (Encoder–Decoder CNN with skip connections)  
- Loss Function:
  - Mean Squared Error (MSE)
  - Structural Similarity Index (SSIM)
  - Combined loss for improved perceptual quality  

### 5. Reconstruction
- Patch-wise predictions aggregated using **overlapping averaging**
- Full-image reconstruction performed to ensure global consistency  

---

## Results

### Visual Results

## Evaluation Metrics

| Metric | Before (Noisy) | After (Denoised) | Improvement |
|--------|----------------|------------------|------------|
| PSNR (dB) | 26.84 | 39.74 | +12.9 dB |
| SSIM | 0.40 | 0.95 | +0.55 |

---

| Noisy Input | Model Output | Ground Truth |
|------------|-------------|--------------|
| ![](results/noisy.png) | ![](results/output.png) | ![](results/clean.png) |

---
## Interpretation

- Significant noise reduction is observed, with PSNR improving by approximately 13 dB.
- Strong structural preservation is achieved, as indicated by the SSIM increase toward 1.

The model demonstrates a clear improvement in image quality and structural fidelity after denoising.

Overall, the model:
- effectively removes noise from low-dose CT images  
- preserves important anatomical and structural details  
- reconstructs high-quality, diagnostically meaningful images  
---

## How to Run

```bash
git clone https://github.com/your-username/CT-Image-Denoising-U-Net.git  
cd CT-Image-Denoising-U-Net              
pip install -r requirements.txt
Run notebook:
   notebooks/ct_denoising_training.ipynb   
```
## Key Features
- Patch-based training and reconstruction
- Overlapping patch strategy
- U-Net architecture for medical imaging
- Full-image reconstruction pipeline
- Quantitative + visual evaluation

## Limitations
- Synthetic Gaussian noise (not real low-dose CT noise)
- Small dataset (100 images)
- 2D slice-based approach

## Future Improvements
- Compare with baseline filters
- Improve architecture (Attention U-Net/Residual U-Net)
- Extend to real low-dose CT datasets
- 3D Volumetric Reconstruction

## Author

- Biomedical Engineering & CS Graduate               
- Focused on AI in Healthcare & Medical Imaging
