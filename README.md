# Speech-Based Detection of Alzheimer's Disease

This project investigates the use of speech features and machine learning to detect early signs of Alzheimer's Disease. By analyzing variations in vocal characteristics, the goal is to build a non-invasive, affordable diagnostic system that can aid early intervention.

## Project Overview

Alzheimer’s Disease affects cognitive abilities such as memory and communication. Subtle changes in speech—like irregular pauses, jitter, or reduced fluency—can serve as early indicators. This project leverages machine learning to identify such markers and distinguish between healthy individuals and those with neurological impairments.

## Dataset

The dataset used is the **Parkinson’s Speech Dataset with Multiple Types of Sound Recordings**, available from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/301/parkinson%2Bspeech%2Bdataset%2Bwith%2Bmultiple%2Btypes%2Bof%2Bsound%2Brecordings).

- 1040 samples from 20 Parkinson’s patients and 20 healthy controls
- 26 extracted speech features per sample
- Test set includes sustained vowels ('a' and 'o') from 28 Parkinson’s patients
- Due to class imbalance in the test set, the train and test data were merged and re-split using stratified sampling

## Methodology

### Preprocessing
- Combined train and test datasets
- Performed feature scaling using scikit-learn
- Split data using stratified sampling to maintain class balance

### Models Used
 1. **Voting Classifier**: SVM, KNN, and Random Forest with probabilistic voting
 2. **XGBoost Classifier**
 3. **Stacking Classifier**: Combines Random Forest, Gradient Boosting, and SVM
- **Shallow Neural Network**:
  - Activation function: PReLU
  - Loss function: BCEWithLogitsLoss
  - Dropout regularization (rate: 0.3)

### Model Tuning and Evaluation
- GridSearchCV was used for hyperparameter tuning
- Evaluation metrics included:
  - Accuracy
  - F1 Score
  - ROC-AUC

## Results

A comparison of model performances is shown below:

| Model               | Accuracy | F1 Score | ROC-AUC |
|---------------------|----------|----------|---------|
| Voting Classifier   | 0.71     | 0.750    | 0.785   |
| XGBoost             | 0.715    | 0.747    | 0.807   |
| Stacking Classifier | 0.727    | 0.759    | 0.806   |
| Neural Network      | 0.707    | 0.736    | 0.778   |

*(Replace '--' with actual performance metrics)*
