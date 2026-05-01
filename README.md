# CT Image Denoising using U-Net (Deep Learning)

## 📌 Overview
This project presents a deep learning-based approach for denoising low-dose CT images using a U-Net architecture. The model is trained to reconstruct high-quality CT images from synthetically corrupted inputs, simulating realistic low-dose imaging conditions.

The pipeline is designed to reflect a research-oriented workflow, including data preprocessing, noise simulation, patch-based learning, and full-image reconstruction.

---

## 🧠 Problem Statement
Reducing radiation exposure in CT imaging (low-dose CT) introduces significant noise, which degrades diagnostic quality. The objective of this project is to develop a deep learning model capable of restoring image quality while preserving anatomical structures.

---

## ⚙️ Methodology

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

## 📊 Results

### Visual Results

| Noisy Input | Model Output | Ground Truth |
|------------|-------------|--------------|
| ![](results/noisy.png) | ![](results/output.png) | ![](results/clean.png) |

---

## 📈 Evaluation Metrics

| Metric | Noisy Input | Model Output |
|--------|------------|--------------|
| PSNR   | 26.83      | (to be updated) |
| SSIM   | 0.40       | (to be updated) |

> The model demonstrates significant improvement in structural preservation and noise reduction (quantitative results to be finalized).

---

## 🚀 How to Run

```bash
git clone https://github.com/your-username/CT-Image-Denoising-U-Net.git
cd CT-Image-Denoising-U-Net
pip install -r requirements.txt

🎯 Key Features
- Patch-based training and reconstruction
- Overlapping patch strategy
- U-Net architecture for medical imaging
- Full-image reconstruction pipeline

📌 Future Improvements
- Add PSNR and SSIM evaluation
- Compare with baseline filters
- Improve architecture (Attention U-Net)
- Extend to real low-dose CT datasets

👩‍💻 Author

- Biomedical Engineering Graduate               
- Focused on AI in Healthcare & Medical Imaging
