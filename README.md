# Cifar-100_using-VGG-16
CIFAR-100 image classification using VGG16 with transfer learning and fine-tuning. CIFAR images (32×32) are resized to 224×224 for VGG16 compatibility. Includes data augmentation, feature extraction, fine-tuning, and model evaluation for higher accuracy.

# 🚀 Project Overview

✔ Uses **VGG-16 pretrained on ImageNet**  
✔ Resizes **CIFAR-100 (32×32)** images to **224×224**  
✔ Includes **data augmentation** to reduce overfitting  
✔ Two-stage training approach:
- **Feature Extraction** (VGG frozen)
- **Fine-Tuning** (last layers unfrozen)

✔ Achieves significant accuracy improvement over a baseline CNN  

This project demonstrates strong understanding of **deep learning**, **transfer learning**, **fine-tuning**, and **model optimization**, all of which are essential skills for real-world AI applications.

---

# 📊 Dataset: CIFAR-100

The CIFAR-100 dataset contains:

- **60,000 images** (32×32×3)
- **100 fine-grained categories**
- **500 training images per class**
- **100 testing images per class**

It is more challenging than CIFAR-10 due to its larger number of classes and smaller image resolution.

**Dataset Source:**  
https://www.cs.toronto.edu/~kriz/cifar.html

---

# 🧠 Model Architecture (VGG-16)

The **VGG-16 base model** is loaded without its top layers:

- `weights = 'imagenet'`
- `include_top = False`
- Input images resized to **224×224×3**

### Custom classifier added:
- `Flatten`
- `Dense` with ReLU activation
- `Dropout (0.5)`
- `Dense` with **100-class softmax** for CIFAR-100 output

---

# 🔧 Training Strategy

### **1️⃣ Feature Extraction Phase**
- Freeze all VGG-16 convolutional layers  
- Train only the custom Dense layers  
- Learning Rate: **1e-4**

### **2️⃣ Fine-Tuning Phase**
- Unfreeze the last few VGG-16 layers  
- Train the full model with a **very low LR**  
- Learning Rate: **1e-5**

This allows the model to adapt high-level ImageNet features to CIFAR-100 without overwriting pretrained knowledge.

---

# 📈 Results

| Model Type              | Accuracy |
|-------------------------|----------|
| CNN from scratch        | 40–50%   |
| VGG16 (frozen)          | 55–65%   |
| **VGG16 + Fine-Tuning** | **65–72%** |

VGG-16 greatly improves performance on CIFAR-100 compared to traditional CNNs.

---

# 🛠 Technologies Used

- TensorFlow / Keras  
- VGG-16 Pretrained Model  
- Data Augmentation  
- Python  
- GPU Acceleration  

---

# 📜 License

- CIFAR-100 dataset is licensed under the **MIT License**.  
- The CIFAR-100 dataset is licensed under the MIT License by the University of Toronto.

---

# 👤 Author

**DARSHINI**  
Machine Learning | Deep Learning | Computer Vision  
GitHub: *https://github.com/darshinio-debug*
