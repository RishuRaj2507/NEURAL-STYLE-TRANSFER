# Neural Style Transfer

*Company* - *CODTECH IT SOLUTIONS*

*NAME* - *RISHU RAJ*

*INTERN ID* - *CT04DF2641*

*DOMAIN* - *ARTIFICIAL INTELLIGENCE*

*DURATION* - *4 WEEKS*

*MENTOR* - *NEELA SANTHOSH KUMAR*

## 🎨 Neural Style Transfer using PyTorch and VGG19

This project implements **Neural Style Transfer** in Python using PyTorch and the pre-trained VGG19 model. The goal is to generate a new image that combines the **content of one image** with the **style of another**, creating visually compelling artistic results.

---

### 🚀 Overview

Neural Style Transfer is a technique that uses deep neural networks to recompose the **content image** in the style of another image. This implementation uses the **VGG19 convolutional neural network**, a popular architecture pre-trained on ImageNet, to extract high-level features from both the content and style images.

---

### 📁 Features

* 🖼️ **Image Loader with Fallback**: If the content or style image file is missing, a placeholder white image is created automatically.
* 🧠 **VGG19 Feature Extraction**: Uses selected layers of VGG19 to extract features for computing content and style loss.
* 🎨 **Style Matching via Gram Matrix**: Captures style by comparing feature correlations between style and generated images.
* ⚙️ **Gradient-based Optimization**: Uses the Adam optimizer to iteratively refine the output image.
* 💾 **Image Saving**: Final image is saved as `output.jpg`.

---

### 📜 How It Works (Key Steps)

1. **Device Setup**:

   * Automatically selects the best available hardware (Apple MPS, CUDA GPU, or CPU).

2. **Image Preprocessing**:

   * Resizes and normalizes the input images.
   * Converts them to PyTorch tensors.

3. **Model Loading**:

   * Loads the pretrained VGG19 model and freezes it to extract fixed features.

4. **Feature Extraction**:

   * Defines which VGG layers to use for style and content representations.
   * Content features are extracted from layer `21`.
   * Style features are extracted from layers `0`, `5`, `10`, `19`, `28`.

5. **Style Representation**:

   * Style is captured using **Gram matrices**, which encode texture information by computing correlations between feature maps.

6. **Optimization**:

   * A random-noise-initialized copy of the content image is used as the starting point.
   * The image is optimized to minimize a weighted sum of **content loss** and **style loss**.

7. **Output**:

   * Progress is logged every 50 iterations.
   * Final image is saved as `output.jpg`.

---

### 🧪 Sample Use Case

Given:

* `content.jpg`: A photo of a cityscape.
* `style.jpg`: A painting by Van Gogh.

This code will generate an output image with the **content of the cityscape** and the **style of Van Gogh’s painting**.

---

### 📦 Requirements

Install dependencies with:

```bash
pip install torch torchvision pillow matplotlib
```

---

### 💡 Customization Tips

* Change `content_layers` or `style_layers` for different visual effects.
* Adjust `style_weights` or `total loss multiplier (1e6)` for stronger or subtler stylization.
* Modify `max_size` in `load_image()` for different resolutions.

---

### 📸 Output

<img width="1075" alt="Image" src="https://github.com/user-attachments/assets/1299ffb0-4a38-40b1-91c0-999afab66fc4" />

After 300 iterations, the result is saved as `output.jpg`. You can view it using any image viewer or integrate it into a GUI/web app.

---

Let me know if you'd like a simplified version, GUI wrapper, or want to generate a stylized image preview automatically!
