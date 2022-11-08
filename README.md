# Talent Model

The objective of this project is to use a dataset to build a hiring system that predicts “hire,” “rejected at interview,” or “rejected at pre-interview.”
Deploying models that impact people requires careful ethical decision-making. One of the components of ethical AI is Systematicity.
This project addresses systematicity by using an ensemble model method. 

The main code file is TalentModel.ipynb. It has the following functions:
1. clean_split_data(data_copy) This function takes the dataframe, cleans it, and splits it into two parts: one with 90% and one with 10% of the data. The 90% is used to create models, and the 10% is used to address systematicity. 

2. train_ensembleModel(x_train_systemicity, x_test_systemicity, y_train_systemicity, y_test_systemicity, ensembleModel): This function performs phase 1 of prediction, training the ensemble model. It trains and builds an ensemble model that contains a set of models (with similar accuracy). This function also stores the set of models in the ensembleModel folder to use at prediction time.

3. lst=predict(new_candidate_df,ensembleModel) function takes a dataframe (new_candidate_df) and randomly selects one model from the ensemble model set (ensembleModel) at prediction time.
This function can be called with the previous two on ensembleModel "RandomClassifierEnsembles1". The trained models are already in the repository. This function returns a NumPy array containing predictions for each candidate in the new_candidate_df dataframe.

4. evaluate(test_data,ensembleModel) this function takes a dataframe and the name of the ensemble model (ex. RandomClassifierEnsembles1) as input. It evaluates the ensemble model on the data given dataset and returns two values used as evaluation metrics called coverage and arbitrariness.


The file 'TalentModel_EDA.ipynb' contains the exploratory data analysis of the given dataset. 'Talent Model.pdf' is the presentation explaining the project.
