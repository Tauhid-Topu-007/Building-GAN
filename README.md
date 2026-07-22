# GAN for MNIST Digit Generation

<div align="center">
  <img src="image_at_epoch_0200.png" alt="Generated Digits" width="400">
  <br>
  <em>Generated handwritten digits after 200 epochs of training</em>
</div>

## 📋 Table of Contents
- [Overview](#overview)
- [Model Architecture](#model-architecture)
- [Requirements](#requirements)
- [Implementation Details](#implementation-details)
- [Training](#training)
- [Results](#results)
- [Usage](#usage)
- [Files Structure](#files-structure)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project implements a **DCGAN (Deep Convolutional Generative Adversarial Network)** to generate synthetic handwritten digits. The GAN consists of two competing neural networks:

- **Generator**: Creates fake images from random noise
- **Discriminator**: Distinguishes between real and fake images

The model is trained on the MNIST dataset (60,000 training images of 28x28 grayscale digits).

## 🏗️ Model Architecture

### Generator Architecture

Input: Random noise (100 dimensions)

↓

Dense Layer (7×7×256)

↓

Batch Normalization + LeakyReLU

↓

Reshape (7×7×256)

↓

Conv2D Transpose (128 filters, 5×5 kernel)

↓

Batch Normalization + LeakyReLU

↓


Conv2D Transpose (64 filters, 5×5 kernel)

↓

Batch Normalization + LeakyReLU

↓

Conv2D Transpose (1 filter, 5×5 kernel, tanh)

↓

Output: 28×28×1 grayscale image


**Total Parameters**: ~2.33 million

### Discriminator Architecture
Input: 28×28×1 image

↓

Conv2D (64 filters, 5×5 kernel, stride 2)

↓

LeakyReLU + Dropout (0.3)

↓

Conv2D (128 filters, 5×5 kernel, stride 2)

↓

LeakyReLU + Dropout (0.3)

↓

Flatten

↓

Dense (1 neuron)

↓

Output: Real/Fake


**Total Parameters**: ~212,865

## 📦 Requirements

```bash
tensorflow>=2.12.0
numpy>=1.24.0
matplotlib>=3.7.0
Pillow>=9.4.0
imageio>=2.31.0
IPython>=8.12.0```



