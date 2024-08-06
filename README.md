# Final_Project_207
DataSCI 207 Final Project

Team Members: Elana Wadhwani, Lia Cappellari, Branndon Marion

Summer 2024 

Student dropout is a significant issue in the education system and can lead to several other problems in the future. High drop-out rates can contribute to a less skilled workforce, which in turn leads to higher unemployment rates and lower lifetime earnings. And then this not only affects the individual but also the overall economic growth of the community.  Secondly, increased drop-out rates are associated with higher crime rates and greater social dependency. Lastly, educational institutions also suffer when drop-out rates are high, as this negatively affects their reputation, funding, and morale. 

For our final project, we aimed to answer the research question of 'What are the leading factors of student dropout in higher education?' This is important because the ability to predict drop-out rates allows for proactive intervention and schools can implement targeted support and intervention programs to help these students stay on track. To predict student dropout rates, we created 4 different models (baseline, logistic regression, random forest, neural network) and compared their accuracy. 

We downloaded our dataset from this link: https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success

In our repository, you will find two Jupyter Notebooks. The first contains all of our exploratory data analysis and associated visuals. The second notebook contains our modeling and hyperparameter experiments. 


### Analysis of Hyperparameter Tuning:

1. Estimators:
- Increasing the number of trees (e.g., 1250) did not always improve performance.
- Models with 750 estimators often performed as well or better than those with 1250.
  - Tested values: 500, 750, 1250.
2. Max Depth:
- Deeper trees (e.g., max depth of 30) often led to worse performance, indicating overfitting.
- Shallower trees (e.g., max depth of 20) performed better on validation and test sets.
  - Tested values: 9, 12, 20, 25, 27, 30.
3. Min Samples Split and Min Samples Leaf:
- Smaller values for min_samples_split (e.g., 3) and min_samples_leaf (e.g., 2) generally improved performance.
- Finer splits were necessary to effectively capture patterns in the data.
- Tested values for min_samples_split: 3, 5, 6, 7, 9, 11.
  - Tested values for min_samples_leaf: 2, 4, 5, 7, 9, 11.
4. Max Features:
- The sqrt option for max_features consistently outperformed log2.
- Considering a larger subset of features for each split improved performance.
  - Tested values: 'log2', 'sqrt'.

Summary of Best Performing Models:
- The 8th model (750 estimators, max depth of 25, min samples split of 7, min samples leaf of 7, max features as 'sqrt') achieved the highest validation and test accuracies.
This model demonstrated a good balance between complexity and generalization.
The 5th model showed similar accuracies but with greater generalization ability.
In conclusion, careful tuning of hyperparameters, such as the number of estimators, max depth, min samples split and leaf, and max features, is crucial for optimizing the performance of a Random Forest Classifier.

![My Image](https://github.com/ewadhwan/Final_Project_207/blob/main/RFC.experiments.png?raw=true)
