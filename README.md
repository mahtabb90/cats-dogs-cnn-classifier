# Cats vs Dogs CNN Classifier

A deep learning project for image classification using Convolutional Neural Networks (CNN).
The goal of the project is to classify images as either **cat** or **dog**.

## Team

* Mahtab
* Emmy
* Spirit

## Project Overview

This project was created as part of a Deep Learning CNN assignment.
We selected a Cats vs Dogs image dataset from Kaggle and built CNN models using TensorFlow/Keras.

The project includes:

* Dataset exploration
* Image preprocessing
* Simple CNN baseline model
* Improved CNN models
* Data augmentation
* Dropout
* Early stopping
* Model evaluation
* Confusion matrix
* Classification report
* Final model comparison

## Dataset

We used a Kaggle Cats vs Dogs dataset.

Dataset structure:

```text
dogcat/
├── train/
│   ├── cats/
│   └── dogs/
├── validation/
│   ├── cats/
│   └── dogs/
├── test1/
│   └── test1/
└── sampleSubmission.csv
```

The dataset contains:

| Dataset part    | Images |
| --------------- | -----: |
| Training data   | 25,000 |
| Validation data |  8,000 |
| Test data       | 12,500 |

The training and validation sets are balanced, with equal numbers of cat and dog images.

The test folder does not contain true labels, so it was used only for prediction examples.
The validation set was used for model evaluation.

## Preprocessing

Before training, the images were prepared for CNN input.

Preprocessing steps:

* Resize images to 128x128 pixels
* Convert images to RGB format
* Normalize pixel values from 0–255 to 0–1
* Load images in batches
* Use validation data for evaluation

## Models

### 1. Simple CNN Baseline

The first model was a simple CNN architecture using:

* Conv2D layers
* MaxPooling2D layers
* Flatten layer
* Dense layers
* Sigmoid output layer

Result:

| Model               | Validation Accuracy |
| ------------------- | ------------------: |
| Simple CNN Baseline |              87.46% |

### 2. Improved CNN V1

The first improved model used:

* Data augmentation
* Dropout
* Early stopping
* Google Colab GPU training

Result:

| Model           | Validation Accuracy |
| --------------- | ------------------: |
| Improved CNN V1 |              87.54% |

### 3. Improved CNN V2

The final improved model used a more tuned strategy:

* Milder data augmentation
* Lower dropout rate
* Lower learning rate
* More training epochs with early stopping
* Google Colab T4 GPU

Result:

| Model           | Validation Accuracy |
| --------------- | ------------------: |
| Improved CNN V2 |              91.72% |

## Final Results

| Model               | Validation Accuracy |
| ------------------- | ------------------: |
| Simple CNN Baseline |              87.46% |
| Improved CNN V1     |              87.54% |
| Improved CNN V2     |              91.72% |

The best model was **Improved CNN V2**, with a validation accuracy of **91.72%**.

## Evaluation

The models were evaluated using:

* Validation accuracy
* Validation loss
* Confusion matrix
* Classification report
* Visual prediction examples

The final model correctly classified **7,338 out of 8,000 validation images**.

Improved CNN V2 confusion matrix summary:

| Class | Correct | Misclassified |
| ----- | ------: | ------------: |
| Cats  |   3,535 |           465 |
| Dogs  |   3,803 |           197 |

## Prediction Analysis

In addition to numerical evaluation, we also analyzed individual image predictions.

This helped us understand:

* How confident the model was
* Which images were classified correctly
* Which images were misclassified
* What types of images were difficult for the model

Some difficult cases included images with unusual angles, poor lighting, multiple animals or unclear backgrounds.

## Tools and Technologies

* Python
* TensorFlow / Keras
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* Jupyter Notebook
* Google Colab
* GitHub

## How to Run the Project

1. Clone the repository:

```bash
git clone <repository-url>
```

2. Add the dataset locally in this structure:

```text
data/raw/dogcat/
```

3. Run the notebooks in order:

```text
01_dataset_exploration.ipynb
02_simple_cnn_model.ipynb
03_improved_cnn_model.ipynb
```

The dataset is not included in the repository because image datasets are large and should not be pushed to GitHub.

## Conclusion

The project shows that CNN models can learn meaningful visual patterns from image data.

The baseline model performed well, but the best result came after tuning the improved model.
Improved CNN V2 achieved the highest validation accuracy with **91.72%**.

This shows that model improvement requires testing, comparison and careful hyperparameter tuning.

