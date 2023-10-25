# Ensemble-Transfer-Learning-for-Gastric-Cancer-Prediction-Using-Electronic-Health-Records
> The code and data on this page for the realization of the paper


## Data
- **nhis_data.csv** : medical checkup data for patients with atrophic gastritis or gastric cancer from 2002 to 201 at 3National Health Insurance Service(NHIS) in South Korea, which were converted into the OMOP–CDM.
- **kd_data.csv** :  data of patients with atrophic gastritis or gastric cancer at the Kangdong Sacred Heart Hospital(KSHH), which were converted into the OMOP-CDM.
- **result.csv** : Ensemble transfer learning model's result csv file.
- **ensemble_data.csv** : Ensemble data csv file.
</br>

## Ensemble Transfer Learning for Gastric Cancer Model Plot
![그림2](https://github.com/YeabinLim/Ensemble_Transfer_Learning_for_Gastric_Cancer/assets/118752772/43f06ec5-a160-434e-b28a-5406103af22a)

### Transfer Learning
Three prediction models are employed, initially initialized with pre-trained data and later fine-tuned for the target dataset. Stacking Ensemble Learning combines predictions from these transfer learning models to make the final gastric cancer prediction, while a Deep Neural Network is utilized to improve prediction performance.

### Stacking Ensemble Learning
Stacking ensemble learning is applied to achieve the final prediction by combining the predictions of the transfer learning models.

### Explanation
The explanation process consists of two steps. For population-level explanation, permutation feature importance is applied to the source models, which are trained on extensive population health checkup data. For personal-level explanation, **SHAP (Shapley Additive Explanations)** is used on high-risk individual patients.
</br>
</br>

## Result
### Performance Evaluation
#### Transfer Learning
- . A pre-trained model was generated using the NHIS data, and then the pre-trained model was fine-tuned using the KSHH model.
  
| Model          | Sensitivity | Specificity | F1-Score | Accuracy | AUC   |
| -------------- | ----------- | ----------- | -------- | -------- | ----- |
| SVM            | 0.71        | 0.60        | 0.62     | 0.65     | 0.75  |
| Random Forest  | 0.44        | 0.74        | 0.58     | 0.67     | 0.72  |
| DNN            | 0.44        | 0.80        | 0.62     | 0.72     | 0.79  |


#### Ensemble Transfer Learning
- Applied the stacking ensemble to the three transfer learning models

| Sensitivity | Specificity | F1-Score | Accuracy | AUC   |
| ----------- | ----------- | -------- | -------- | -------- |
| 0.75        | 0.92        | 0.93     | 0. 88    | 0.86     

✔️ Ensemble Transfer Learning method outperformed all other methods in terms of specificity, F1-score, accuaracy, and AUC, which achieved 92%, 93%, 88%, 86%, respectively.

