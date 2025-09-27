# Deep Learning Image Denoising using Autoencoders

This project develops and evaluates **deep learning autoencoder models** for **image denoising** — the process of removing noise from images to reconstruct clean versions. The dataset consists of peanut images that have been artificially corrupted with noise, and the models aim to recover the original details.

---

## Project Objective
To build and compare **three autoencoder models**:
1. **Baseline Model** – basic convolutional autoencoder.
2. **Modified Model** – improved architecture with tuning.
3. **Fine-Tuned Model** – model with additional fine-tuning for better performance.

The models are evaluated based on how well they reconstruct the original images from noisy inputs.

---

## Dataset & Preprocessing
- **Dataset**: Peanut images (`.jpg`) extracted from a ZIP archive  
- **Image Size**: Resized to `(100, 100)` pixels  
- **Normalization**: Pixel values scaled to `[0, 1]`  
- **Noise Addition**: Gaussian noise added to simulate noisy images  

Each model is trained to **map noisy images → clean images**.

---

## Model Architecture
All models are **Convolutional Autoencoders**, with layers such as:
- `Conv2D`, `MaxPooling2D`, `UpSampling2D`
- Activation: `ReLU`
- Optimizer: `Adam` / `RMSProp`
- Loss Function: `Mean Squared Error (MSE)`

Models are implemented in **TensorFlow / Keras**.

---

## Evaluation & Results

### Heatmap: Model Reconstruction Error
Below is the **heatmap** comparing reconstruction error across 3 models and 5 test samples:

> **Darker color** = lower error (better reconstruction)  
> **Lighter color** = higher error (worse reconstruction)

| Model | Description |
|-------|--------------|
| **Baseline** | Lowest and most consistent error (best performance) |
| **Modified** | Moderate performance, improved on certain features |
| **Fine-Tuned** | Slightly higher variation, less consistent than baseline |

**Conclusion**:  
The **Baseline Model** achieves the most stable and lowest reconstruction error, indicating the best denoising capability among the three.
