# 🐶🐱 Cats vs Dogs Image Classification

This project builds a deep learning model to classify images of **cats 🐱 and dogs 🐶** using a pre-trained **MobileNetV2** model with TensorFlow.  
The model is trained on the **Kaggle Dogs vs Cats dataset** and achieves good accuracy using transfer learning.

---

## 📌 Project Overview

The goal of this project is to develop an image classification system that can automatically distinguish between cats and dogs.

### 🔹 Features
- Image preprocessing and resizing  
- Label generation  
- Train-test split  
- Transfer learning with MobileNetV2  
- Model training and evaluation  
- Prediction system for new images  

---

## 📂 Dataset

- Dataset: **Dogs vs Cats (Kaggle)**  

### Labels:
- Cat → 0  
- Dog → 1  

---

## ⚙️ Installation & Setup

### 1️⃣ Install dependencies

```bash
pip install kaggle tensorflow tensorflow-hub opencv-python pillow matplotlib scikit-learn
```

---

### 2️⃣ Setup Kaggle API

```bash
mkdir -p ~/.kaggle
mv kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```

---

### 3️⃣ Download dataset

```bash
kaggle competitions download -c dogs-vs-cats
unzip dogs-vs-cats.zip
unzip train.zip
```

---

## 🧪 Data Preprocessing

- Resize images to **224 × 224**  
- Convert images to RGB format  
- Normalize pixel values (0–1)  
- Assign labels:
  - Dog → 1  
  - Cat → 0  

---

## 🧠 Model Architecture

- Base Model: **MobileNetV2 (pretrained on ImageNet)**  

```python
model = tf.keras.Sequential([
    pretrained_model,
    tf.keras.layers.Dense(2)
])
```

### ⚙️ Configuration
- Loss: Sparse Categorical Crossentropy  
- Optimizer: Adam  

---

## 🏋️ Training

- Train-Test Split: **80% / 20%**  
- Epochs: **5**  
- Training Images: **1600**  
- Testing Images: **400**  

---

## 📊 Evaluation

- Model evaluated using test accuracy and loss  
- Achieves good performance with transfer learning  

---

## 🔮 Prediction

```python
input_image_path = input("Enter image path: ")
```

### Output:
- Cat 🐱  
- Dog 🐶  

---
