# Speech Emotion Recognition (SER) in Noisy Environments

## Overview
This repository contains the complete pipeline for a Speech Emotion Recognition system tested under real-world noise constraints. The project evaluates the robustness of standalone architectures against a Soft-Voting Ensemble "Super Model," utilizing a 781-dimensional hybrid feature space (Wav2Vec2 + MFCC). The study covers the full pipeline from raw audio to noise-robust classification.

## Project Title
Robust Speech Emotion Recognition: MFCC + Noisy + Enhancement using CTSP + wav2vec

## Methodology
1. **Feature Extraction:** Integration of 13-D MFCCs with 768-D Wav2Vec2 contextual embeddings.
2. **Noise Injection:** Stress-testing clean audio using Cafe, Street, and White noise at various SNR levels (-10dB to 15dB).
3. **Signal Enhancement:** Comparison of Digital Signal Processing techniques including CTSP (Cascaded Time and Spectral Processing) and MMSE (Minimum Mean Square Error).
4. **Classification:** Evaluation across SVM (Linear/RBF), MLP (Neural Network), and Ensemble Voting methods.

## Key Findings
* **Architecture Performance:** The Multilayer Perceptron (MLP) Neural Network emerged as the most robust architecture. It maintained superior classification accuracy in high-stress environments, such as Cafe and Street noise at low SNR, occasionally outperforming the Voting Ensemble.
* **Optimal Training Domain:** Models trained on MMSE-enhanced data showed significantly better generalization. MMSE-trained classifiers consistently outperformed those trained on clean or CTSP-enhanced data when tested on unseen noise.
* **Feature Superiority:** The 781-dimensional Hybrid feature set proved essential for noise robustness. The inclusion of Wav2Vec2 contextual embeddings provided a vital accuracy buffer that traditional MFCCs alone could not maintain under degradation.

## Repository Structure
* **evaluation_results:** Comprehensive Excel and CSV metrics mapping precision, recall, and F1-scores across all SNR levels and noise types.
* **presentation_plots:** High-quality visual analysis including Cross-Condition Ablation Heatmaps, Radar Charts, and SNR Robustness curves.
* **Python Notebooks:** Modular scripts for noise injection, signal enhancement, hybrid feature extraction, and model training.
* **Project Documentation:** Includes Mid-term, Final Evaluation, and References PDF reports.
---
**Note:** Raw audio datasets, enhanced audio and large .npy feature arrays are excluded from this repository due to size constraints.
