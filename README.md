# Dogs vs Cats Image Classification

This project implements a Convolutional Neural Network (CNN) to classify images of dogs and cats using deep learning techniques. The model is trained on the popular Dogs vs Cats dataset from Kaggle and achieves approximately 78% accuracy on test data.

## 🚀 Features

- **Data Loading**: Automatic download of Dogs vs Cats dataset from Kaggle
- **Data Preprocessing**: Image resizing, normalization, and augmentation
- **CNN Architecture**: Custom CNN with 4 convolutional layers
- **Training**: 10 epochs with validation split
- **Evaluation**: Comprehensive metrics including confusion matrix and ROC curve
- **Prediction**: Single image prediction with visualization

## 📋 Prerequisites

- Python 3.x
- Kaggle account with API credentials
- Required packages (automatically installed):
  - TensorFlow 2.x
  - Keras
  - NumPy
  - Matplotlib
  - Seaborn
  - scikit-learn
  - OpenCV
  - PIL

## 🛠️ Installation & Setup

1. **Clone the repository**:
```bash
git clone https://github.com/yourusername/dogs-vs-cats-classification.git
cd dogs-vs-cats-classification
Install required packages:

bash
pip install tensorflow numpy matplotlib keras opencv-python pillow scikit-learn seaborn
Set up Kaggle API credentials:

Download your kaggle.json from Kaggle account settings

Place the file in the project directory

The notebook will automatically configure the API

📊 Dataset
The dataset contains 25,000 images of dogs and cats:

Training data: 20,000 images (10,000 dogs, 10,000 cats)

Validation data: 4,000 images (2,000 dogs, 2,000 cats)

Test data: 5,000 images (2,500 dogs, 2,500 cats)

🏗️ Model Architecture
The CNN model consists of:

Convolutional Layers:

Conv2D (32 filters, 3x3) + MaxPooling (2x2)

Conv2D (64 filters, 3x3) + MaxPooling (2x2)

Conv2D (128 filters, 3x3) + MaxPooling (2x2)

Conv2D (128 filters, 3x3) + MaxPooling (2x2)

Fully Connected Layers:

Flatten layer

Dense (512 units, ReLU activation)

Dense (1 unit, Sigmoid activation)

Total Parameters: 3,453,121

📈 Training Results
Training Accuracy: 94.1%

Validation Accuracy: 78.3%

Test Accuracy: 78.4%

Training History
text
Epoch 1: Accuracy: 49.6%, Val Accuracy: 51.7%
Epoch 2: Accuracy: 58.1%, Val Accuracy: 61.5%
Epoch 3: Accuracy: 62.7%, Val Accuracy: 65.7%
Epoch 4: Accuracy: 66.8%, Val Accuracy: 68.1%
Epoch 5: Accuracy: 71.0%, Val Accuracy: 73.2%
Epoch 6: Accuracy: 75.1%, Val Accuracy: 76.2%
Epoch 7: Accuracy: 79.4%, Val Accuracy: 77.6%
Epoch 8: Accuracy: 83.9%, Val Accuracy: 76.7%
Epoch 9: Accuracy: 88.7%, Val Accuracy: 78.8%
Epoch 10: Accuracy: 94.1%, Val Accuracy: 78.3%
📊 Evaluation Metrics
Confusion Matrix Results
True Positives (Dogs): 1,861

True Negatives (Cats): 2,059

False Positives: 441

False Negatives: 639

Performance Metrics
Precision (Dogs): 0.81

Recall (Dogs): 0.74

F1-Score (Dogs): 0.77

Precision (Cats): 0.76

Recall (Cats): 0.82

F1-Score (Cats): 0.79

🎯 Usage
Training the Model
The model is automatically trained when running the notebook:

python
history = model.fit(
    train_generator,
    epochs=10,
    validation_data=validation_generator
)
Making Predictions
python
# Predict on a single image
def make_prediction(image_path):
    # Load and preprocess image
    img = load_img(image_path, target_size=(150, 150))
    img_array = img_to_array(img)
    img_array = np.expand_dims(img_array, axis=0)
    img_array = img_array / 255.0
    
    # Make prediction
    prediction = model.predict(img_array)
    
    # Display result
    if prediction[0][0] > 0.5:
        print("Predicted: Dog")
    else:
        print("Predicted: Cat")
Batch Prediction on Test Set
python
# Evaluate on test set
test_loss, test_accuracy = model.evaluate(test_generator)
print(f"Test Accuracy: {test_accuracy:.4f}")
📁 Project Structure
text
dogs-vs-cats-classification/
├── README.md
├── dogs_vs_cats.ipynb          # Main notebook
├── kaggle.json                 # Kaggle API credentials
├── requirements.txt            # Python dependencies
└── results/
    ├── confusion_matrix.png    # Generated confusion matrix
    ├── training_history.png    # Training/validation plots
    └── sample_predictions.png  # Sample predictions
🔧 Model Optimization
Potential improvements to consider:

Data augmentation techniques

Dropout layers to reduce overfitting

Transfer learning (VGG16, ResNet50)

Hyperparameter tuning

Early stopping

Learning rate scheduling

🐛 Known Issues
Model shows signs of overfitting after epoch 7-8

Test accuracy lower than validation accuracy

Some misclassification in similar-looking images

📝 Future Work
Implement transfer learning with pre-trained models

Add more data augmentation techniques

Fine-tune hyperparameters using GridSearchCV

Deploy model using Flask/FastAPI

Create a web interface for predictions

Add support for video classification

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments
Dataset: Dogs vs Cats Dataset on Kaggle

TensorFlow/Keras team for the deep learning framework

Kaggle platform for providing the dataset and computational resources

📧 Contact
For questions or suggestions, please open an issue in the GitHub repository.

Note: Make sure to place your kaggle.json file in the project directory before running the notebook. The file is used to authenticate with the Kaggle API for dataset download.

text

This README provides comprehensive documentation for your Dogs vs Cats classification project, including setup instructions, model architecture, training results, and usage examples. It's structured to help both users and developers understand and use your project effectively.
