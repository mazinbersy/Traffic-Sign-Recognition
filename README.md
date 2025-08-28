# 🚦 Traffic Sign Classification with CNN

This project implements a **Convolutional Neural Network (CNN)** in **TensorFlow/Keras** to classify German Traffic Signs using the [GTSRB dataset](https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign).  
The model is trained on images of 43 classes of traffic signs and evaluated using accuracy and a confusion matrix.  

---

## 📂 Project Structure
```
├── Data/
│ └── Train/ # Training images (43 class folders)
│ └── Test/ # Test images (unlabeled)
├── model.ipynb # Main script
└── README.md # Documentation
```
---
## 🧪 Model Architecture
- Input: 32×32 RGB images
- Conv2D(16) + MaxPooling2D
- Conv2D(32) + MaxPooling2D
- Flatten + Dense(64, ReLU) + Dropout(0.3)
- Dense(43, Softmax)
- Optimizer: Adam
- Loss: SparseCategoricalCrossentropy
- Metrics: Accuracy
---
## 🔄 Preprocessing & Augmentation
- Rescaling: pixel values divided by 255.0
- Data augmentation:
  - Random Rotation (±10%)
  - Random Zoom (±10%)
  - Random Contrast (±10%)
---
## 📊 Evaluation
- After training:
  - Accuracy is computed on the validation set
  - A confusion matrix is plotted for detailed error analysis
  - Example confusion matrix:
<img width="1220" height="972" alt="image" src="https://github.com/user-attachments/assets/dd81cf55-8784-4fb1-9888-183e413dbed2" />

---
## 🖼️ Testing on New Images
- The script loads test images from Data/Test/, resizes them to 32×32, normalizes, and predicts labels.
Predictions are shown in 10×10 image grids:
<img width="1320" height="769" alt="image" src="https://github.com/user-attachments/assets/e2cbcd61-c1b6-4601-bc3d-50d0d308d874" />


---
## ✅ Results
- Validation accuracy: ~97% (depends on training)
- The confusion matrix highlights classes with the most misclassifications.
- Works well for distinguishing most traffic signs.
---
## ⚙️ Requirements
Install dependencies with:
```bash
pip install tensorflow scikit-learn matplotlib numpy os
```
