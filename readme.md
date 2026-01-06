# Unsupervised Music Clustering using Beta-VAE (IRMAS)

**Author:** Sourav Das  
**Student ID:** 23141072  
**Course:** Neural Networks (CSE425)

---

## 📌 Project Overview
This project explores unsupervised clustering of music audio using Variational Autoencoders (VAEs).  
I use log-Mel spectrograms extracted from the IRMAS dataset and compare multiple representation learning methods:

- PCA + K-Means
- Convolutional Autoencoder + K-Means
- **Convolutional Beta-VAE (Hard-level model)** + K-Means / Agglomerative Clustering

The goal is to learn structured latent representations that improve clustering quality without using labels during training.

---

## 🎵 Dataset
**IRMAS (Instrument Recognition in Musical Audio Signals)**  
- 6,705 audio samples  
- 11 instrument classes  
- WAV format  
- Folder names used only for evaluation (not training)

Official link:  
https://www.upf.edu/web/mtg/irmas

---

## 🧠 Method Summary
1. Extract log-Mel spectrograms (128 Mel bins, 3s audio)
2. Normalize spectrograms globally
3. Train:
   - PCA baseline
   - CNN Autoencoder
   - **CNN Beta-VAE (β = 4, latent dim = 32)**
4. Perform clustering on latent space:
   - K-Means
   - Agglomerative Clustering
5. Evaluate using:
   - Silhouette Score
   - Calinski–Harabasz Index
   - Davies–Bouldin Index
   - ARI, NMI, Purity (labels used only for evaluation)

---

## 📊 Results (Key Highlights)
- **Beta-VAE achieves Silhouette = 0.47**
- PCA baseline Silhouette = 0.13
- Autoencoder Silhouette = 0.11
- Significant improvement in cluster separability using Beta-VAE

