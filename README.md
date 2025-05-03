# 🧠 Image Classification Using CNNs (CIFAR-10)

This repository contains an end-to-end deep learning project aimed at classifying images from the CIFAR-10 dataset using Convolutional Neural Networks (CNNs). The project follows a structured approach from data exploration to model evaluation and improvement.

## 📌 Objective

Understand and implement a basic CNN architecture for image classification on the CIFAR-10 dataset using TensorFlow/Keras. Evaluate model performance and explore techniques to improve results.

---

## 📂 Project Structure

```
.
├── notebooks/
│   └── cnn_image_classification.ipynb   # Main project notebook
├── models/
│   └── baseline_model.h5                # Saved model file
├── outputs/
│   ├── accuracy_loss_curves.png
│   ├── confusion_matrix.png
│   └── sample_predictions.png
├── README.md
└── requirements.txt
```

---

## 🔍 Task Breakdown and Insights

### ✅ Task 1: Data Exploration & Preparation

* Loaded CIFAR-10 dataset using `tensorflow.keras.datasets`.
* Displayed 5 sample images with their labels for visual understanding.
* Data shapes:

  * `Training data shape: (50000, 32, 32, 3)`
  * `Test data shape: (10000, 32, 32, 3)`
* Normalized pixel values to \[0, 1] for efficient model training.
* Dataset split:

  * 80% training
  * 20% validation (from training set for internal validation)

### 🏗️ Task 2: Build & Train CNN Model

* Designed a CNN architecture:

  * `Conv2D` → `ReLU` → `MaxPooling2D` → `Dropout` layers (x2)
  * `Flatten` → `Dense` → `Output (Softmax)`
* Compiled using:

  * `loss = 'sparse_categorical_crossentropy'`
  * `optimizer = Adam`
  * `metrics = ['accuracy']`
* Trained over **15 epochs** with early stopping.
* Plotted **loss** and **accuracy** over epochs.

  * 📉 **Observation**: Slight overfitting visible after epoch 10; dropout helped reduce it.

### 📊 Task 3: Model Evaluation

* Achieved **Test Accuracy: \~72–75%**.
* Generated:

  * Confusion Matrix (see `outputs/confusion_matrix.png`)
  * Classification Report: precision, recall, f1-score.
* Visualized:

  * Correctly classified examples.
  * Misclassified examples (useful for understanding model limitations).

### 🧪 Task 4: Model Improvement

* Tested different optimizers:

  * Baseline: `Adam`
  * Alternate: `SGD` and `RMSProp`
* 🧾 **Performance Comparison Table**:

| Optimizer | Accuracy | Comments               |
| --------- | -------- | ---------------------- |
| Adam      | \~75%    | Fast convergence       |
| SGD       | \~68%    | Slower, less effective |
| RMSProp   | \~73%    | Comparable to Adam     |

---

## 📈 Key Insights

* **Normalization** improves training efficiency.
* **Dropout** reduces overfitting effectively.
* **Optimizer choice** significantly affects performance.
* **Visualization of predictions** helps diagnose model behavior.

---

## 🛠️ Setup Instructions

1. Clone the repo:

   ```bash
   git clone https://github.com/yourusername/cifar10-cnn.git
   cd cifar10-cnn
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:

   ```bash
   jupyter notebook notebooks/cnn_image_classification.ipynb
   ```

---

## 📚 Requirements

See `requirements.txt`:

* `tensorflow`
* `matplotlib`
* `numpy`
* `seaborn`
* `scikit-learn`

