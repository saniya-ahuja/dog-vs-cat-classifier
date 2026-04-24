🐶🐱 Cats vs Dogs Image Classification

This project builds a deep learning model to classify images of cats and dogs using a pre-trained MobileNetV2 model with TensorFlow. The model is trained on the popular Kaggle Dogs vs Cats dataset and achieves good accuracy with transfer learning.

📌 Project Overview

The goal of this project is to develop an image classification system that can automatically distinguish between cats and dogs. It uses:

Image preprocessing and resizing
Label generation
Train-test split
Transfer learning with MobileNetV2
Neural network training and evaluation
A prediction system for new images
📂 Dataset
Dataset: Dogs vs Cats (Kaggle)
Contains images labeled as:
cat → 0
dog → 1

Steps:

Download dataset using Kaggle API
Extract training and test images
Use a subset (2000 images) for faster training
⚙️ Installation & Setup
1. Install dependencies
pip install kaggle tensorflow tensorflow-hub opencv-python pillow matplotlib scikit-learn
2. Setup Kaggle API
Upload your kaggle.json
mkdir -p ~/.kaggle
mv kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
3. Download dataset
kaggle competitions download -c dogs-vs-cats
unzip dogs-vs-cats.zip
unzip train.zip
🧪 Data Preprocessing
Images resized to 224 × 224
Converted to RGB format
Normalized pixel values (0–1)
Labels assigned:
Dog → 1
Cat → 0
🧠 Model Architecture
Base Model: MobileNetV2 (pretrained on ImageNet)
Feature extractor from TensorFlow Hub
Custom classification layer:
model = tf.keras.Sequential([
    pretrained_model,
    tf.keras.layers.Dense(2)
])
Loss Function: Sparse Categorical Crossentropy
Optimizer: Adam
🏋️ Training
Train-Test Split: 80% / 20%
Epochs: 5
Training images: 1600
Testing images: 400
📊 Evaluation

Model performance is evaluated using:

Test Loss
Test Accuracy
🔮 Prediction System

You can classify your own image:

Steps:
Input image path
Resize to 224×224
Normalize
Predict using trained model
Output:
0 → Cat 🐱
1 → Dog 🐶
🚀 Example Usage
input_image_path = input('Path of the image: ')

Model will display the image and predict whether it's a cat or dog.

🛠️ Technologies Used
Python
TensorFlow / Keras
OpenCV
NumPy
Matplotlib
Scikit-learn
