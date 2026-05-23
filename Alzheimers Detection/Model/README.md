## Alzheimer's Detection

---

### 🎯 **Goal**

The goal of this project is to develop and compare deep learning models capable of classifying brain MRI scans into four stages of Alzheimer's Disease — **Non Demented, Very Mild Demented, Mild Demented, and Moderate Demented** — to support healthcare professionals in Alzheimer’s stage classification and analysis.

---

### 🧵 **Dataset**

**Source:** [Kaggle – Alzheimer's Dataset (4 Class of Images)](https://www.kaggle.com/datasets/tourist55/alzheimers-dataset-4-class-of-images)

The dataset contains **6,400 labelled MRI brain scan images** across four classes:

| Class | Description |
|---|---|
| NonDemented | No signs of cognitive decline |
| VeryMildDemented | Earliest detectable memory changes |
| MildDemented | Noticeable memory and cognitive issues |
| ModerateDemented | Significant impairment in daily functions |

---

### 🧾 **Description**

This project classifies brain MRI images into different stages of Alzheimer's disease using two deep learning architectures — an **Artificial Neural Network (ANN)** and a **Convolutional Neural Network (CNN)**. The models are trained on augmented and SMOTE-balanced MRI image data and evaluated using AUC score. A Streamlit web application is also included for live predictions.

---

### 🧮 **What I had done!**

1. Collected MRI scan dataset from Kaggle (4 classes, 6400 images).
2. Applied image augmentation using `ImageDataGenerator` (brightness range, zoom, horizontal flip, rescaling to 1/255).
3. Addressed class imbalance using **SMOTE** — dataset expanded from 6400 to 12800 balanced samples.
4. Split data into **Train / Validation / Test** sets using `train_test_split`.
5. Built and trained an **ANN model** as a baseline (Dense layers only).
6. Built and trained a deeper **CNN model** with SeparableConv2D, BatchNormalization, and Dropout layers.
7. Used **EarlyStopping** (patience=3, restoring best weights) to prevent overfitting.
8. Evaluated both models on AUC score and loss across 50 epochs.
9. Plotted Training vs Validation Accuracy and Loss curves for both models.
10. Saved the best model as `model.h5`.
11. Developed a **Streamlit web application** for live MRI image prediction.

---

### 🚀 **Models Implemented**

#### 1. Artificial Neural Network (ANN)

A fully connected baseline model. Flattens the MRI image pixels and passes them through Dense layers to classify into 4 Alzheimer's stages.

**Architecture:**
- `Flatten` input layer → `(176 × 176 × 3)`
- `Dense(100, relu)`
- `Dense(200, relu)` × 4
- `Dense(4, softmax)` — output layer

**Why this model?**
- Serves as a performance **baseline** before applying spatial feature extractors.
- Simple to train, fast to converge, and easy to interpret.

**Compiler settings:** Optimizer = `Adam` | Loss = `CategoricalCrossentropy` | Metric = `AUC`

---

#### 2. Convolutional Neural Network (CNN)

A deep convolutional model designed to capture spatial features from MRI images that an ANN cannot detect from raw flattened pixels.

**Architecture:**
- `Conv2D(16, 3×3, relu)` → `MaxPool2D`
- `Conv2D(32, 2×2, relu)` → `MaxPool2D`
- `SeparableConv2D(64, 3)` × 2 + `BatchNormalization` + `MaxPool2D`
- `SeparableConv2D(128, 3)` × 2 + `BatchNormalization` + `MaxPool2D` + `Dropout(0.2)`
- `SeparableConv2D(256, 3)` × 2 + `BatchNormalization` + `MaxPool2D` + `Dropout(0.2)`
- `Flatten`
- `Dense(512, relu)` + `BatchNormalization` + `Dropout(0.7)`
- `Dense(128, relu)` + `BatchNormalization` + `Dropout(0.5)`
- `Dense(64, relu)` + `BatchNormalization` + `Dropout(0.3)`
- `Dense(4, softmax)` — output layer

**Why this model?**
- Convolutional layers extract spatial and structural features from brain scans.
- `SeparableConv2D` is computationally efficient compared to standard `Conv2D`.
- `BatchNormalization` stabilizes training; `Dropout` prevents overfitting on medical image data.

**Compiler settings:** Optimizer = `Adam` | Loss = `CategoricalCrossentropy` | Metric = `AUC`

---

### 📚 **Libraries Needed**

- `numpy`
- `pandas`
- `matplotlib`
- `tensorflow`
- `keras`
- `scikit-learn`
- `imbalanced-learn` (imblearn / SMOTE)
- `opencv-python` (cv2)
- `streamlit`
- `pillow`
- `os`, `random`, `warnings` (standard library)

---

### 📊 **Exploratory Data Analysis Results**

**Sample MRI Brain Scan from Dataset**

![Sample MRI Brain Scan](../Images/image.jpg)

**Key EDA findings:**

- The dataset is **heavily imbalanced** — `NonDemented` contains ~3,200 images while `ModerateDemented` has fewer than 100. SMOTE was applied to balance all classes before training.
- Visual inspection of MRI scans across classes confirms **visible structural differences** — NonDemented brains show well-defined sulci and gyri, while ModerateDemented scans show enlarged ventricles and cortical atrophy.
- Image augmentation (brightness, zoom, horizontal flip) was applied to improve model generalisation across varied scan orientations.

---

### 📈 **Performance of the Models based on the Accuracy Scores**

| Model | Loss | AUC Score | Notes |
|---|---|---|---|
| **ANN (Artificial Neural Network)** | 0.5686 | **93.64%** | Best performer — stable convergence, strong generalisation |
| **CNN (Convolutional Neural Network)** | 1.4560 | **87.90%** | Overfits on this dataset size; benefits from further tuning |

> **Key finding:** The ANN outperformed the CNN in this run. While CNNs are typically stronger for image classification, the CNN showed signs of overfitting — training AUC approached ~100% while validation accuracy fluctuated. The ANN's simpler architecture generalised more reliably on this dataset. Transfer Learning or stronger regularisation would likely close this gap.

---

### 📢 **Conclusion**

This project demonstrates that deep learning can effectively classify Alzheimer's disease stages from brain MRI scans. The **ANN achieved the best AUC of 93.64%**, outperforming the CNN (87.90%) due to more stable generalisation. The CNN showed overfitting tendencies despite Dropout and BatchNormalization, suggesting the dataset size and current hyperparameters were not optimal for the deeper architecture.

**Future improvements could include:**
- Applying Transfer Learning (VGG16, ResNet50, EfficientNet) leveraging features from large image datasets.
- Using Grad-CAM to visualise which brain regions most influenced predictions.
- Stronger regularisation and learning rate scheduling to improve CNN stability.
- Deploying the best model as a clinical web application for real-world decision support.

---

### ✒️ **Your Signature**

**Rishi V**  
GitHub: [@kit29-25bad132](https://github.com/kit29-25bad132)  
LinkedIn: [rishivkit](https://www.linkedin.com/in/rishivkit/)  
Contributor — **GSSoC 2026**