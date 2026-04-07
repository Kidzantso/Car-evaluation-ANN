# Car Evaluation ANN

## 📌 Project Overview
This project implements an **Artificial Neural Network (ANN)** in PyTorch to classify car acceptability using the **Car Evaluation Dataset** from the UCI Machine Learning Repository.  
The dataset is derived from a hierarchical decision model and contains only categorical features.  

The goal is to:
- Preprocess categorical data correctly using **Sum coding** and **Backward Difference coding** (as suggested in the referenced paper).
- Build and train an ANN classifier.
- Evaluate performance using accuracy, precision, recall, and F1-score.

---

## 📊 Dataset
**Features:**
- `buying` — buying price (vhigh, high, med, low)  
- `maint` — maintenance cost (vhigh, high, med, low)  
- `doors` — number of doors (2, 3, 4, 5more)  
- `persons` — capacity (2, 4, more)  
- `lug_boot` — luggage boot size (small, med, big)  
- `safety` — safety level (low, med, high)  

**Target:**
- `car_class` — car acceptability (`unacc`, `acc`, `good`, `vgood`)

There are **no missing values** in the dataset.

---

## ⚙️ Workflow
1. **Load dataset** from UCI repository.  
2. **Apply encoding**:
   - **Backward Difference coding** for ordered features (`buying`, `maint`).  
   - **Sum coding** for unordered features (`doors`, `persons`, `lug_boot`, `safety`).  
3. **Split data** into training and test sets (80/20).  
4. **Build ANN model**:
   - Input: encoded features  
   - Hidden layers: 64 → 32 → 16 (ReLU activations)  
   - Output: 4 neurons (Softmax for multi-class classification)  
5. **Train model** using Adam optimizer and CrossEntropyLoss.  
6. **Evaluate** with accuracy, precision, recall, and F1-score.

---

## 🧪 Results
- **Test Accuracy:** ~99.7%  
- **Macro F1-score:** ~0.99  
- Performance exceeds the reported benchmark (~96%) thanks to contrast coding.

---


## 📚 References
- [UCI Car Evaluation Dataset](https://archive.ics.uci.edu/dataset/19/car+evaluation)  
- IJCA Paper: *Comparative Study of Encoding Techniques for Neural Network Classification* (Sum coding & Backward Difference coding)
