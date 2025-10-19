# Non_local_means_denoising

This project implements and analyzes the Non-Local Means (NL-Means) algorithm for image denoising and compares its performance against traditional local filters such as Moving Average, Gaussian, Median, and Total Variation (TV) denoising.

---

## Overview

In digital images, pixel values are often corrupted by noise due to sensor imperfections or image enhancement operations. The goal of image denoising is to recover the original clean image from a noisy observation without losing fine details or textures.

The **Non-Local Means** algorithm improves upon local averaging techniques by computing each pixel’s value as a weighted average of all other pixels in the image. The weights are based on the similarity between image patches, rather than just spatial proximity.

---

## Methods Implemented

- **Moving Average Filter** – Simple neighborhood averaging.  
- **Median Filter** – Edge-preserving local filter.  
- **Gaussian Filter** – Weighted local smoothing using a Gaussian kernel.  
- **Total Variation (TV) Denoising** – Variational method minimizing total variation.  
- **Non-Local Means (NL-Means)** – Patch-based, non-local averaging for texture preservation.  

---

## Results Summary

| Method | PSNR ↑ | SSIM ↑ | Observation |
|:--------|:--------:|:--------:|:-------------|
| Moving Average | Low | Low | Blurs edges and textures |
| Median Filter | Moderate | Moderate | Good for salt-and-pepper noise |
| Gaussian Filter | Moderate | Moderate | Smooths details |
| TV Denoising | Variable | Low | Sharp edges but oversmoothing |
| **NL-Means** | **Highest** | **Highest** | Preserves textures and achieves best clarity |

---

## Key Insights

- **NL-Means** consistently achieved higher **PSNR** and **SSIM** values than other methods across all tested images and noise levels.  
- It preserves **texture** and **fine details** better than traditional local filters.  
- The algorithm’s performance depends on parameters such as **search window size**, **filtering parameter (h)**, and **Gaussian kernel width (a)**.  

---

## Limitations

- High computational cost for large images.  
- Sensitive to parameter tuning.  
- May introduce artifacts in flat or low-contrast regions.  

---

## Reference

Buades, A., Coll, B., & Morel, J.-M. (2005).  
"A Non-Local Algorithm for Image Denoising." *IEEE Computer Society Conference on Computer Vision and Pattern Recognition (CVPR’05),* San Diego, CA, USA.  
