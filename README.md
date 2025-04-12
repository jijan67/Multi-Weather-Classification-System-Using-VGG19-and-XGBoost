# 🌦️ Multi-Weather Classification System Using VGG19 and XGBoost

This documentation provides a detailed explanation of the Weather Classification System implemented using VGG19 for feature extraction and XGBoost for classification. The goal of this system is to accurately classify weather conditions from images across 7 different categories.

---

## Overview

The project uses a dataset of weather images containing various classes: Cloudy, Fog, Rain, Sand, Shine, Snow, and Sunrise. The model employs transfer learning with VGG19 for feature extraction followed by XGBoost for classification, achieving an overall accuracy of 89.26%.

## Libraries Used

The following Python libraries were used to implement the model:

- **NumPy:** For numerical operations and array handling
- **Pandas:** For data manipulation and analysis
- **Matplotlib:** For data visualization and confusion matrix plotting
- **Scikit-learn:** For model evaluation, data splitting, and preprocessing
- **TensorFlow/Keras:** For using the pre-trained VGG19 model
- **XGBoost:** For the classification algorithm

## Project Structure

**1. Data Loading and Organization:**
- The dataset is loaded from the "MultiWeatherDataset" directory
- Image paths and corresponding labels are extracted
- The data is organized into a pandas DataFrame
- The dataset is split into training (80%) and test (20%) sets using stratified sampling

**2. Feature Extraction:**
- A pre-trained VGG19 model is used as a feature extractor
- Each image is resized to 224×224 pixels, preprocessed, and passed through VGG19
- The extracted features form the input for the XGBoost classifier

**3. Model Training:**
- Labels are encoded using LabelEncoder
- An XGBoost classifier is trained on the extracted features
- The model is configured for multi-class classification

**4. Model Evaluation:**
- Classification reports are generated for both training and test sets
- A confusion matrix visualizes the model's performance across classes
- ROC curves and AUC scores are calculated for each class

## Evaluation Results

- **Test Accuracy:** 89.26%
- **Class-specific Performance:**
  - Cloudy: Precision 0.96, Recall 0.90, F1-score 0.93
  - Fog: Precision 0.82, Recall 0.78, F1-score 0.80
  - Rain: Precision 0.93, Recall 0.93, F1-score 0.93
  - Sand: Precision 0.86, Recall 0.83, F1-score 0.84
  - Shine: Precision 0.90, Recall 0.92, F1-score 0.91
  - Snow: Precision 0.82, Recall 0.90, F1-score 0.86
  - Sunrise: Precision 0.93, Recall 0.99, F1-score 0.96

The confusion matrix shows strong diagonal values, indicating good classification across all weather types. ROC curves demonstrate the model's ability to distinguish between different weather conditions with high AUC values.

## Conclusion

This weather classification system successfully combines deep learning feature extraction (VGG19) with a gradient boosting classifier (XGBoost) to achieve high accuracy in distinguishing between 7 different weather conditions. The model performs particularly well on Sunrise, Cloudy, and Rain classes, with slightly lower but still strong performance on Fog and Sand conditions.

The approach demonstrates the effectiveness of transfer learning for image classification tasks where limited training data is available, leveraging pre-trained networks to extract meaningful features from weather images.
