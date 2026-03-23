# 🐾 Dogs vs Cats Image Classification

This project implements a Convolutional Neural Network (CNN) using TensorFlow/Keras to classify images of dogs and cats, achieving **~78.4% test accuracy**.

---

## 🚀 Features
- **Auto-Download:** Direct ingestion of dataset via Kaggle API.
- **Custom CNN Architecture:** 4 Convolutional layers + MaxPooling.
- **Visual Analytics:** Accuracy/Loss curves, confusion matrices, and ROC curves.
- **Inference Engine:** Ready-to-use function for single-image predictions.

---

## 🛠️ Installation & Setup

```bash
# 1. Clone the repo
git clone [https://github.com/yourusername/dogs-vs-cats-classification.git](https://github.com/yourusername/dogs-vs-cats-classification.git)
cd dogs-vs-cats-classification

# 2. Install dependencies
pip install tensorflow numpy matplotlib opencv-python pillow scikit-learn seaborn

# 3. Setup Kaggle API
# Drop your 'kaggle.json' (from Kaggle Profile -> Settings) into this root directory.
🏗️ Architecture & DatasetThe dataset contains 25,000 images (split Train: 20k, Val: 4k, Test: 5k).Input: Image resized to 150x150Layers: 4x Conv2D (32, 64, 128, 128 filters) + MaxPoolingDense: Flatten $\rightarrow$ Dense(512, ReLU) $\rightarrow$ Dense(1, Sigmoid)Total Parameters: 3,453,121📈 ResultsMetricTrainingValidationTestAccuracy94.1%78.3%78.4%🕒 Training LogsEpochTrain AccVal AccEpochTrain AccVal Acc149.6%51.7%675.1%76.2%258.1%61.5%779.4%77.6%362.7%65.7%883.9%76.7%466.8%68.1%988.7%78.8%571.0%73.2%1094.1%78.3%⚠️ Note: The model begins overfitting after Epoch 7. Consider adding Dropouts or Data Augmentation.🎯 Usage (Python)Pythonimport numpy as np
from tensorflow.keras.preprocessing.image import load_img, img_to_array

def make_prediction(image_path):
    img = load_img(image_path, target_size=(150, 150))
    img_array = img_to_array(img) / 255.0
    img_array = np.expand_dims(img_array, axis=0)
    
    prediction = model.predict(img_array)
    print("Predicted: Dog" if prediction[0][0] > 0.5 else "Predicted: Cat")

# Evaluate
test_loss, test_acc = model.evaluate(test_generator)
📁 Repository StructurePlaintext├── dogs_vs_cats.ipynb     # Main Notebook
├── kaggle.json            # Auth API file (Do not push to GitHub)
├── requirements.txt       # App requirements
└── results/
    ├── confusion_matrix.png
    └── training_history.png
📜 License & ContactsDistributed under the MIT License. For inquiries, please open a Repository Issue.
