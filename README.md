# Hand Sign Digit Classification with Keras (Binary & Multi-Class)

This project was completed as part of the **"Basics of Deep Learning"** course at Colman College, 2024.

We built and trained deep learning models using TensorFlow/Keras to classify grayscale hand-sign digit images. The project includes both binary and multi-class classification tasks, model experiments, and accuracy comparisons.

## 👨‍💻 Authors
- Tal Levy
- Omer Virshovsky
  
## 📊 Dataset
- Grayscale 28x28 images representing digits 0–9
- **Binary Classification**: classes `2` and `4` only
- **Multi-Class Classification**: all 10 digit classes (0–9)
- Data normalized to [0, 1]
- Train/Validation/Test splits: 80/10/10

## 🧠 Models Overview

### 🔹 Binary Classification (2 vs 4)
- Sequential model: `Flatten → Dense(128, ReLU) → Dense(64, ReLU) → Dense(2, softmax)`
- Optimizer: Adam | Loss: Categorical Crossentropy | Epochs: 10
- **Accuracy**: 100%

**Confusion Matrix**  
| Actual \ Predicted | 0 | 1 |
|--------------------|---|---|
| 0                  | 82 | 0 |
| 1                  | 0  | 78 |

---

### 🔸 Multi-Class Classification (0–9)

#### Base Model:
- `Dense(24, sigmoid) → Dense(10, softmax)`  
- **Accuracy**: 51%

#### Experiment 1:
- Added layers: `128` and `64` neurons with ReLU  
- **Accuracy**: 91%

#### Experiment 2 (Best Model):
- ReLU + sigmoid activations + learning rate tuning  
- **Accuracy**: 98%

## 📈 Results Summary
- Adding hidden layers and ReLU activation greatly improved accuracy.
- Learning rate adjustment (from 0.0001 → 0.001) helped avoid overfitting.
- Model saved to Google Drive and validated successfully.

## 🗂 Files
- `keras_digits_classifier.ipynb` – Main notebook
- `report.pdf` – Project documentation
- `README.md` – You're here

## 🧠 What I Learned
- Building classification models in Keras
- Handling both binary and multi-class problems
- Effect of activation functions, depth, and learning rate
- Visualizing training curves and evaluating confusion matrices
