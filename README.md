# 📊 INTRUSION DETECTION SYSTEMS (IDS)

A streamlined machine learning project utilizing a **reduced Decision Tree model** designed for efficient inference. This repository includes a complete pipeline—from preprocessing to serialized model artifacts—allowing for immediate deployment without the need for retraining.

---

## 🚀 Project Overview

This project demonstrates an end-to-end machine learning lifecycle:

- **Data Preprocessing**: Cleaning and preparing raw network traffic data.
- **Feature Engineering**: Encoding categorical variables and scaling numerical inputs.
- **Model Training**: Implementing an optimized Decision Tree classifier.
- **Persistence**: Serializing components using `joblib` for production use.
- **Inference**: Loading artifacts to make real-time predictions.

---

## ⚙️ Requirements

Ensure you have Python installed, then install the necessary dependencies:

```bash
pip install scikit-learn pandas numpy joblib

```

---

## ▶️ Usage

The following snippet demonstrates how to load the artifacts and process new data for prediction:

```python
import joblib
import pandas as pd

# 1. Load the serialized components
model = joblib.load("DT_Reduced_Model.joblib")
encoder = joblib.load("Reduced_Encoder.joblib")
scaler = joblib.load("Reduced_Scaler.joblib")

# 2. Prepare input data (Example)
data = pd.DataFrame([...])

# 3. Preprocessing Pipeline
# Transform categorical data and scale numerical features
encoded_data = encoder.transform(data)
scaled_data = scaler.transform(encoded_data)

# 4. Perform Inference
prediction = model.predict(scaled_data)
print(f"Model Prediction: {prediction}")

```

---

## 🧠 Model Details

| Attribute           | Description                              |
| ------------------- | ---------------------------------------- |
| **Model Type**      | Decision Tree Classifier                 |
| **Preprocessing**   | Label/One-Hot Encoding + Feature Scaling |
| **Optimization**    | Reduced complexity for faster inference  |
| **Primary Dataset** | CICIDS2017 (Network Intrusion Detection) |

---

## 📌 Features

- **Pre-trained**: Ready for immediate use without retraining.
- **Efficient**: Optimized pipeline for low-latency predictions.
- **Portable**: Lightweight `.joblib` files for easy deployment.
- **Modular**: Separate encoder and scaler for flexible data handling.

---

## 🔮 Future Improvements

- [ ] **API Deployment**: Wrap the model in a FastAPI or Flask wrapper.
- [ ] **Interactive UI**: Build a Streamlit dashboard for manual data input.
- [ ] **Automated Pipeline**: Add a script for automated model retraining.
- [ ] **Performance Tuning**: Hyperparameter optimization to further boost accuracy.

