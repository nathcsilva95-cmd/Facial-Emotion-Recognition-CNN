# Facial Emotion Recognition using Convolutional Neural Networks  (CNN)
**Final Deep Learning & AI Project – Nathalia Silva**  
Deep Learning & Artificial Intelligence – Fall 2025  

---

## 📘 Project Overview
This project implements a Convolutional Neural Network (CNN) to classify facial images into **seven emotion categories**:

- Angry  
- Disgust  
- Fear  
- Happy  
- Neutral  
- Sad  
- Surprise  

The model was trained on a FER-style dataset organized into **train**, **validation**, and **test** folders with 48×48 grayscale images.

---

## 🧠 Methodology

### **1. Data Preparation**
- Dataset format: `train/` and `test/` folders with 7 emotion subfolders  
- Images converted to 48×48 grayscale  
- 20% of the training data automatically used as validation  
- Applied **data augmentation**:  
  - rotation,  
  - width/height shift,  
  - zoom,  
  - horizontal flip  
to reduce overfitting and improve generalization.

---

### **2. CNN Architecture (Modeling)**
The CNN consists of **three convolutional blocks**, each containing:




Followed by:
- Fully connected layer (256 units + dropout)
- Softmax output layer for 7 classes

This structure progressively learns low-level → mid-level → high-level facial features.

---

### **3. Training Setup**
- **Optimizer:** Adam (learning rate = 0.001)  
- **Loss:** categorical crossentropy  
- **Batch size:** 64  
- **Epochs:** 35  
- **Callbacks used:**
  - EarlyStopping  
  - ReduceLROnPlateau  
  - ModelCheckpoint  

Training was run on Google Colab with GPU acceleration.

---

## 📊 Results

### **Training Performance**
- Validation accuracy increased steadily across epochs  
- Training/validation loss decreased without large divergence  
- No severe overfitting observed  

### **Test Performance**
- **Final test accuracy: ~59.53%**

### **Per-Class Insights**
- Strong performance for: **Happy**, **Surprise**  
- Moderate for: **Neutral**, **Angry**, **Sad**  
- Difficult classes: **Fear**, **Disgust** (subtle expressions, fewer samples)

A full confusion matrix and classification report are included in the notebook.

---

## 📁 Repository Structure

