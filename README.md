# Models for early diabetes prediction

Using a sample of 4200 Chinese adults, which has 18 features collected from blood tests and triage, several data analysis were driven, in order to model a consistent way to predict if a patient is diabetic.

## Preliminary analysis

The first step was to plot histograms for each numerical feature and box plots for categorical features. The numerical exploration revealed either symmetric or slightly skewed distributions. Then, considering that some of the feats where combinations of other feats or weren't quiet relevant, we used GaussianNB, RandomForest and XGBoost to find the best combination of 7 diferent features, so the computational cost remains low while offering good metrics values. The 3 classifiers results provided the same features: FPG (fasting plasma glucose), FFPG (non-fasting plasma glucose), HDL(high-density lipoprotein), LDL(low-density lipoprotein), Age, Drinking and Smoking.

Dispersion plots and heat maps were made trying to find direct relationships between each numerical feature and diabetes, and box plots for categorical features, but results were not conclusive, since overlapping was observed between positives and negative cases for low HDL and LDL values. Also A low proportion of diabetic patients with alcoholism and smoking from none to moderate was noticed. Only a direct relationship was observed in cases of high alcoholism and smoking, and in elevated values of both HDL and LDL.

## Machine learning

The dataset was splitted into 3 subsets: train, cross validation (cv) and test, with a proportion of 60% 20% and 20% respectively. Then several classification algorithms were deployed: GaussianNB, RandomForest, XGBoost,  LogisticRegression, DecisionTree, KNeighbors and SVC. With the first set of results, Hyper parameter tunning was performed using (buscar en el repo) and a second train and test run was made, expecting an improvement in both accuracy and recall metrics. (oracion comentando los resultados) . Afterwards, Soft and Hard voting methods were used, but no aditional improvement was noticed.

## Neural network

## Conclusion
