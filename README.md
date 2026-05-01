# CT Image Denoising using U-Net (Deep Learning)

## 📌 Overview
This project focuses on denoising low-dose CT images using a deep learning-based approach. A U-Net architecture is implemented to reconstruct clean CT images from artificially corrupted (noisy) inputs.

The goal is to simulate low-dose CT imaging conditions and improve image quality using supervised learning.

---

## 🧠 Problem Statement
Low-dose CT scans reduce radiation exposure but introduce significant noise, affecting diagnostic quality. This project aims to address this challenge using deep learning-based image reconstruction techniques.

---

## ⚙️ Methodology

### 1. Data Preparation
- CT images loaded in TIFF format
- Min-Max normalization applied (0–1 range)

### 2. Noise Simulation
- Gaussian noise added to simulate low-dose CT conditions

### 3. Patch-Based Learning
- Images divided into 64×64 patches
- Overlapping patches used to improve spatial consistency

### 4. Model Architecture
- U-Net (Encoder-Decoder CNN)
- Trained using combined loss:
  - Mean Squared Error (MSE)
  - Structural Similarity Index (SSIM)

### 5. Reconstruction
- Patch-wise predictions combined using averaging
- Full-image reconstruction performed

---

## 📊 Results

### Visual Results

| Noisy | Output | Ground Truth |
|------|--------|-------------|
| ![](results/noisy.png) | ![](results/output.png) | ![](results/clean.png) |

---

## 📈 Evaluation Metrics
(To be updated)

- PSNR (Peak Signal-to-Noise Ratio)
- SSIM (Structural Similarity Index)

---

## 🚀 How to Run

1. Clone repository:
  git clone https://github.com/your-username/CT-Image-Denoising-U-Net.git

2. Install dependencies:
   pip install -r requirements.txt
   
4. Run notebook:
- Open notebooks/training.ipynb    

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
