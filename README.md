# Ensemble-Transfer-Learning-for-Gastric-Cancer-Prediction-Using-Electronic-Health-Records



## Data
- **nhis_data.csv** : 
- **kd_data.csv**
- **result.csv** : Ensemble transfer learning model's result csv file.
- **ensemble_data.csv** : Ensemble 


## Ensemble Transfer Learning for Gastric Cancer Model Plot
![그림2](https://github.com/YeabinLim/Ensemble_Transfer_Learning_for_Gastric_Cancer/assets/118752772/43f06ec5-a160-434e-b28a-5406103af22a)

### Transfer Learning
Three prediction models are employed, initially initialized with pre-trained data and later fine-tuned for the target dataset. Stacking Ensemble Learning combines predictions from these transfer learning models to make the final gastric cancer prediction, while a Deep Neural Network is utilized to improve prediction performance.

### Stacking Ensemble Learning
Stacking ensemble learning is applied to achieve the final prediction by combining the predictions of the transfer learning models.

### Explanation
The explanation process consists of two steps. For population-level explanation, permutation feature importance is applied to the source models, which are trained on extensive population health checkup data. For personal-level explanation, **SHAP (Shapley Additive Explanations)** is used on high-risk individual patients.


## Result
### Performance Evaluation
#### Learning from a single dataset
- Used only the small dataset from KSHH as the training data and test data.
  
| Model          | Sensitivity | Specificity | F1-Score | Accuracy | AUC   |
| -------------- | ----------- | ----------- | -------- | -------- | ----- |
| SVM            | 0.48        | 0.84        | 0.66     | 0.76     | 0.80  |
| Random Forest  | 0.44        | 0.74        | 0.58     | 0.67     | 0.71  |
| DNN            | 1.00        | 0.38        | 0.51     | 0.51     | 0.80  |


#### Learning from mixed datasets
- Used the NHIS dataset as training data and the KSHH dataset as test data.

| Model          | Sensitivity | Specificity | F1-Score | Accuracy | AUC   |
| -------------- | ----------- | ----------- | -------- | -------- | ----- |
| SVM            | 0.25        | 0.80        | 0.     | 0.76     | 0.80  |
| Random Forest  | 0.44        | 0.74        | 0.58     | 0.67     | 0.71  |
| DNN            | 1.00        | 0.38        | 0.51     | 0.51     | 0.80  |
