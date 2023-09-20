### Models for early diabetes prediction


Using a sample of 4200 Chinese adults, which has 18 features collected from blood tests and triage, several data analysis were driven, in order to model a consistent way to predict if a patient is diabetic.
### Methodology

## Preliminary analysis

The first step was to plot histograms for each numerical feature and box plots for categorical features. The numerical exploration revealed either symmetric or slightly skewed distributions. Then, considering that some of the feats where combinations of other feats or weren't quiet relevant, we used GaussianNB, RandomForest and XGBoost to find the best combination of 7 diferent features, so the computational cost remains low while offering good metrics values. The 3 classifiers results provided the same features: FPG (fasting plasma glucose), FFPG (non-fasting plasma glucose), HDL(high-density lipoprotein), LDL(low-density lipoprotein), Age, Drinking and Smoking.

Dispersion plots and heat maps were made to find direct relationships between each numerical feature and diabetes, as well as box plots for categorical features, but results were not conclusive, since overlapping was observed between positives and negative cases for low HDL and LDL values. Also A low proportion of diabetic patients with alcoholism and smoking from none to moderate was noticed. Only a direct relationship was observed in cases of high alcoholism and smoking, and in elevated values of both HDL and LDL.

## Machine learning

The dataset was splitted into 3 subsets: train, cross validation (cv) and test, with a proportion of 60% 20% and 20% of the total dataset respectively. Then several classification algorithms were deployed: GaussianNB, RandomForest, XGBoost,  LogisticRegression, DecisionTree, KNeighbors and SVC. The first set of results (Input ) was promising, where we highlight x and y for having the least amount of false prediction and false negative respectively. Then hyper parameter tunning was performed (Input ) and a second train and test run was made(Input ), expecting an improvement in both accuracy and recall metrics. There was x decrease of false predictions.Afterwards, Soft and Hard voting methods were used (Input and ), but no aditional improvement was noticed.

## Neural network

A Feedforward Neural Network (FNN), which consisted of 3 layers of 64, 32 and 1 neurons and relu as activation function for inner layers, and sigmoid for output layer, was trained using the same data division used on classification algorithms (Input ). It first results were on pair of the best results obtained via XGBoost, but further improvement was expected at this task, so optimization was made(Input ). First L1 and L2 regularization methods were implemented (Input ). Next, hyper parameters optimization algorithm using hyperopt was made. Finally, threshold parameter was tunned looking for the lowest amount of false negatives (Input ). 

### Results

## Machine learning

## Neural network

## Conclusion
