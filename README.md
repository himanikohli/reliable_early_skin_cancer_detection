# Reliable Early Skin Cancer Detection

This repository provides the experimental setup, method adopted, and results for melanoma classification using deep feature extraction, classical machine learning classifiers, and ensemble learning. The study focuses on improving classification reliability, particularly by reducing false negatives.

## Dataset

This study uses the **HAM10000 Melanoma Skin Cancer dataset** for binary classification of skin lesion images into:

- **Benign**
- **Malignant**

The dataset used for the experiments is provided in the dataset file. 

## Methodology

The framework includes the following stages:

1. **Image preprocessing:** Prepare skin lesion images for the feature extraction networks.
2. **Feature extraction:** Extract image features using pretrained **ResNet50**, **VGG19**, and **EfficientNetB0** networks.
3. **Feature concatenation:** Combine features from the three networks to evaluate complementary representations.
4. **Classification:** Train and evaluate five classical machine learning classifiers:
   - K-Nearest Neighbors (KNN)
   - Support Vector Machine (SVM)
   - Random Forest (RF)
   - Logistic Regression (LR)
   - XGBoost
5. **Ensemble prediction:** Combine classifier predictions using hard majority voting.
6. **Misclassification reanalysis:** Examine incorrect predictions, particularly false negatives, to investigate opportunities for improving reliability.

## Experimental Setup

Experiments compare classifiers trained on features extracted from individual networks with classifiers trained on concatenated features. Ensemble predictions are evaluated alongside individual classifier predictions.
The experiments were performed using Python 3.10. The primary libraries included NumPy, Pandas, Scikit-learn, XGBoost, TensorFlow, Matplotlib, and Seaborn. All experiments were conducted on a Nova HPC CPU node equipped with dual Intel Xeon Gold 6244 processors running at 3.60 GHz, providing 16 physical cores, 32 logical CPUs, and 376 GiB of RAM.

## Results and Evaluation

Performance is examined using classification metrics and confusion matrices, with particular attention to:

- **Accuracy:** Overall proportion of correctly classified images.
- **Precision:** Proportion of predicted malignant lesions that are malignant.
- **Recall / Sensitivity:** Proportion of malignant lesions correctly identified.
- **F1-score:** Balance between precision and recall.
- **ROC–AUC:** Ability to distinguish benign and malignant lesions across classification thresholds.
- **False negatives:** Malignant lesions incorrectly classified as benign.
- **False positives:** Benign lesions incorrectly classified as malignant.
The Best_Combination.xlsx file contains extensive experimental results for best configurations using one, two, and three deep learning feature extractors, combined with different combinations of machine learning classifiers. Others are reported in Combinations_results.xlsx.

## Intended Use

This repository is intended for research and reproducibility. 
