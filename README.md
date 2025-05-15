# 🐶 DOG BREED CLASSIFICATION USING ENSEMBLE TRANSFER LEARNING

## 🏆 OVERVIEW  
This project classifies dog breeds using an **ensemble of pretrained CNNs** — combining the strengths of multiple architectures to boost performance.  
The final model leverages **InceptionV3**, **Xception**, **NASNetLarge**, and **InceptionResNetV2** for feature extraction, and a custom classifier for final prediction.

---

## 📂 DATASET  
📸 A labeled dataset of dog images covering various breeds.

### 🔍 Preprocessing & Augmentation  
- **Image Resizing** – Standardized input dimensions  
- **Normalization** – Scaled pixel values to [0, 1]  
- **Data Augmentation** – Applied flipping, rotation, zoom, and shifting  
- **Label Encoding** – Converted labels into one-hot format

---

## ⚙️ MODEL ARCHITECTURE

### 🔴 ENSEMBLE MODEL (FINAL ARCHITECTURE)  
**Feature Extractors Used:**  
- ✅ InceptionV3  
- ✅ Xception  
- ✅ NASNetLarge  
- ✅ InceptionResNetV2

**Pipeline Overview:**  
- Images passed through each pretrained model (with weights frozen)  
- Extracted feature vectors from each model  
- Concatenated features into a single vector  
- Fully connected classifier trained on combined features

📌 **Note:** All pretrained models were used **only for feature extraction**. No fine-tuning was applied due to computational constraints.

---

## 📊 PERFORMANCE SUMMARY

- 🎯 **Training Accuracy:** 97.64%  
- 🎯 **Test Accuracy:** 88.54%  
- 📉 **Train Loss:** 1.4568  

📌 **Observation:**  
- High initial accuracy even without fine-tuning  
- Stable performance across different dog breeds  
- Minor overfitting expected due to model complexity and limited data  

---

## ✅ FINAL RECOMMENDATION

✔️ **Use the ensemble model** combining *InceptionV3, Xception, NASNetLarge, and InceptionResNetV2* for the best results.  
✔️ Use pretrained models **only for feature extraction** (freeze their weights).  
✔️ Train **only the classifier layers** to save computation.  
✔️ If the ensemble is too heavy, consider using a lighter model like **MobileNetV2** or **EfficientNetB0**.

---

## ❗ CHALLENGES FACED

🔸 **High Dimensionality**  
- Feature fusion from models like NASNetLarge (4032-dim) creates massive input vectors  
- Leads to long training time and overfitting risk  

🔸 **Computational Complexity**  
- Ensemble of deep models requires significant memory and compute  
- Slower predictions compared to single-model setups  

🔸 **Difficult Error Diagnosis**  
- With multiple feature sources, it’s harder to interpret misclassifications  
- Limits explainability and debugging

---

## 📉 VISUALIZATIONS

- 📈 Training vs Validation Accuracy & Loss  
- 📊 Confusion Matrix  
- 📝 Classification Report (Precision, Recall, F1-Score)  

---

## 🛠 TECH STACK

- Python  
- TensorFlow / Keras  
- OpenCV  
- NumPy, Pandas  
- Matplotlib, Seaborn  

---

## 🚀 FUTURE WORK

- Try dimensionality reduction (PCA, Autoencoders) before classification  
- Optimize ensemble by pruning redundant branches  
- Integrate Grad-CAM for model interpretability  
- Deploy model via Streamlit or Flask as a web application  

---

## 📝 LICENSE  
This project is licensed under the **MIT License**.

---

## 🙌 CREDITS  
- TensorFlow Hub & Keras Applications  
- Public dog breed datasets  
- Researchers behind pretrained CNN architectures
