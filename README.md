# Models for early diabetes prediction

Employing a dataset comprising 4,200 Chinese adults, encompassing 18 distinct features derived from blood tests and triage, a comprehensive data analysis was conducted with the objective of establishing a robust predictive model for diagnosing diabetes in patients.
## Install
You can install the necessary dependencies by running the following command:
pip install -r requirements.txt

## Methodology

### Preliminary analysis

The first step was to plot histograms for each numerical feature and box plots for categorical features. The numerical exploration revealed either symmetric or slightly skewed distributions (Input 8). Then, considering that some of the feats where combinations of other feats or weren't quiet relevant, we used GaussianNB, RandomForest and XGBoost to find the best combination of 7 diferent features (Input 13), so the computational cost remains low while offering good metrics values. The 3 classifiers results provided the same features: FPG (fasting plasma glucose), FFPG (non-fasting plasma glucose), HDL(high-density lipoprotein), LDL(low-density lipoprotein), Age, Drinking and Smoking.

Dispersion plots and heat maps were made (Input 16 - 18) to find direct relationships between each numerical feature and diabetes, as well as box plots for categorical features, but results were not conclusive, since overlapping was observed between positives and negative cases for low HDL and LDL values. Also A low proportion of diabetic patients with alcoholism and smoking from none to moderate was noticed. Only a direct relationship was observed in cases of high alcoholism and smoking, and in elevated values of both HDL and LDL.

### Machine learning

The dataset was splitted into 3 subsets: train, cross validation (cv) and test, with a proportion of 60, 20, and 20% of the total dataset respectively. Then several classification algorithms were deployed: GaussianNB, RandomForest, XGBoost,  LogisticRegression, DecisionTree, KNeighbors and SVC. The first set of results (Input 19) was promising, where we highlight XGBoost and SVC for having the higest Recall and F1 scores respectively. Then hyper parameter tunning was performed (Input 20) and a second train and test run was made(Input 21), expecting an improvement in both accuracy and recall metrics, but there was no meaningful changes. Afterwards, Soft and Hard voting methods were used (Input 22 - 23), which further improved the prediction capabilities, particularly decreasing false negative predictions by 30%.

### Neural network

A Feedforward Neural Network (FNN) (Input 25), which consisted of 3 layers of 64, 32 and 1 neurons and relu as activation function for inner layers, and sigmoid for output layer, was trained using the same data division used on classification algorithms . It first results were on pair of the best results obtained via XGBoost, but further improvement was expected at this task, so optimizations were made. First L1 and L2 regularization methods were implemented (Input 27). Next, hyper parameters optimization algorithm using hyperopt was made (Input 29), and passed to the FNN (Input 30) . Finally, threshold parameter was tunned looking for the lowest amount of false negatives (Input 31). 

### Results

The FNN models demonstrated exceptional accuracy, achieving 95.59% and 93.38% accuracy rates, surpassing or matching traditional models like GaussianNB and RandomForest. Notably, the second FNN model's mere 10 false negatives is vital in a medical context where missing a diabetic patient can have severe consequences. These results align with established medical standards, highlighting the model's potential to aid early diabetes detection and prevent complications.

In the future, enhancing the model's accuracy through additional features or expanded datasets remains a focus. Robustness testing and practical applications in healthcare underscore its potential for real-world impact, enabling early identification of high-risk diabetic patients and timely interventions, ultimately improving patient care.

## Conclusion

This study delved into the realm of early diabetes prediction, employing machine learning and a Feedforward Neural Network (FNN). Our investigation unveiled the FNN's exceptional potential in early diabetes detection, with accuracy rates reaching 93.38% and a mere 10 false negatives in the optimized model.

Compared to traditional machine learning algorithms, the FNN consistently demonstrated superior or equivalent performance. Its low false negative rate is particularly noteworthy, reducing the risk of missing diabetic patients.

Our results align with clinical standards, emphasizing the FNN's promise in enhancing early diabetes diagnosis. This research lays the foundation for future healthcare applications, offering a proactive approach to diabetes management and improved patient outcomes. Further studies and real-world implementations hold the key to maximizing the FNN's impact on healthcare practices.
