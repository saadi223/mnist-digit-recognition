# Mnist-digit-recognition
# 🧠 MNIST Digit Recognition Project

This project demonstrates how to build and deploy a machine learning model that recognizes handwritten digits (0–9) using the famous MNIST dataset.

## 📂 Dataset

The MNIST dataset contains:
- **70,000 grayscale images (28x28 pixels)**
- **60,000 training samples**
- **10,000 test samples**
- Each image contains a single digit (0–9), written by hand.

## 🚀 Technologies Used

- Python
- NumPy, Pandas
- Scikit-learn
- Matplotlib / Seaborn
- Gradio (for Web UI)

## ⚙️ Models Implemented

| Model                   | Accuracy  |
|------------------------|-----------|
| K-Nearest Neighbors    | ~97% ✅    |
| Random Forest Classifier | ~96%     |
| SGD Classifier         | ~91%      |

> ✔️ GridSearchCV was used to tune hyperparameters.  
> ✔️ Data augmentation (image shifting) was applied to improve performance.

## 📊 Evaluation Metrics

- Confusion Matrix
- Classification Report (Precision, Recall, F1-score)
- Accuracy Score
- Visualization of misclassified digits

## 🧪 Data Augmentation

To increase dataset size and reduce overfitting, each training image was shifted:
- ➡️ Right
- ⬅️ Left
- ⬆️ Up
- ⬇️ Down

This increased model robustness and improved test accuracy.

---

## 🌍 Real-Life Applications

- 🏦 **Banking** – Recognize handwritten digits on cheques
- 📮 **Postal Services** – Scan and sort handwritten ZIP codes
- ✍️ **Mobile Apps** – Convert handwriting to text/digits
- 🏫 **Education** – Auto-grade math worksheets
- 🏥 **Healthcare** – Digitize handwritten medical forms

---

## 🌐 Web App (Gradio)

An interactive Gradio app is included, allowing users to:

- ✍️ Draw a digit (0–9) with a mouse or touchscreen
- 🖼️ Upload a handwritten digit image
- 🤖 Get real-time prediction

```python
gr.Interface(
    fn=predict_digit,
    inputs=gr.Image(type="pil", image_mode="L", invert_colors=True, tool="sketch"),
    outputs=gr.Textbox()
).launch()
