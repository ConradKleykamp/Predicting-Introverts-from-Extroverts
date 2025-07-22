# Predicting-Introverts-from-Extroverts
Leveraging and tuning a LGBM model to predict whether an individual is an introvert or an extrovert based upon their social behavior and personality traits

<img width="612" height="612" alt="image" src="https://github.com/user-attachments/assets/2b58825c-2ee8-4ed8-9837-5aee756afdb1" />

---

### About the Project

This project has been completed both as part of Kaggle's competition series and as part of my continued practice and learning of data science techniques. In this particular [Kaggle competition](https://www.kaggle.com/competitions/playground-series-s5e7/overview), we are tasked with predicting whether or not a person is an Introvert or Extrovert, based on their social behavior and personality traits. 

This task poses a binary classification problem, in which a model must correctly determine the correct class (Introvert or Extrovert). The evaluation metric for this project is accuracy score. [Accuracy](https://developers.google.com/machine-learning/crash-course/classification/accuracy-precision-recall) is the proportion of all classifications that are correct. 

<img width="521" height="69" alt="image" src="https://github.com/user-attachments/assets/fc838730-d198-4472-b09b-8c183080fcad" />


The model used for this project is a [LightGBM](https://github.com/microsoft/LightGBM) model.  LightGBM (LGBM) is a fast, distributed, high performance gradient boosting framework that is based on decision tree algorithms. This type of model is typically effective in classification tasks. LGBM is developed by Microsoft and is publicly available for usage. 

In order to identify the best model parameters, I use [Optuna](https://optuna.org/), which is a hyperparameter optimization framework. Optuna will create and run through 100 trials to determine the ideal hyperparameters for the final LGBM model.

To further boost accuracy, I also use ensemble learning. This is a technique that combines multiple models to improve predictive performance. The final, tuned LGBM model will be combined with XGBoost and CatBoost models.

I hope you find this project interesting! If you have any questions or suggestions for improvement, please let me know. I am always looking to improve my data skills!

---

### About the Data

This project utilizes three datasets. Two datasets (training and testing) are provided by Kaggle. These datasets have been generated from a deep learning model trained on the original [Extrovert vs. Introvert Behavior](https://www.kaggle.com/datasets/rakeshkapilavai/extrovert-vs-introvert-behavior-data/data?select=personality_datasert.csv) dataset. 

Kaggle explicitly states that the feature distributions of the synthetic datasets are 'close to, but not exactly the same' as the original. Because of this, I will be using adversarial validation to determine how similar (or different) the distributions of these datasets are.

Target Variable:
- Personality: Extrovert/Introvert

Numeric Features:
- id
- Time_spent_Alone
- Social_event_attendance
- Going_outside
- Friends_circle_size
- Post_frequency

Categorical Features:
- Stage_fear
- Drained_after_socializing

Both the Kaggle and original datasets are available for public use under the CC BY-SA 4.0 license.

---

### Methods
Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- catboost
- sklearn
- lightgbm
- xgboost
- optuna
- tqdm
- shap

---

### Results
<img width="720" height="557" alt="image" src="https://github.com/user-attachments/assets/adc52a0d-dde7-4c6e-bece-b86522c69d51" />

<img width="530" height="441" alt="image" src="https://github.com/user-attachments/assets/f73fda9f-8cfe-4125-a3c7-06ac633f448d" />

<img width="777" height="463" alt="image" src="https://github.com/user-attachments/assets/9946eded-d7f2-4b86-b2a8-431683017cf6" />


Final Model Performance: LGBM

Across folds the best accuracy score of the final LGBM model was 0.97138 and the mean accuracy score was 0.96901.

In terms of feature importance, 'Time_spent_alone' was the most impactful feature on the model, followed closely by 'Friends_circle_size'.

Ensemble Performance

By combining the tuned LGBM model with XGBoost and CatBoost models, I was able to achieve higher accuracy. In terms of competition scoring, the ensemble model yielded an accuracy of 97.4089% (public score).
