## DL-wine-quality

## Mission objectives

- Use a deep learning library
- Prepare a data set for a machine learning model
- Put together a simple neural network
- Tune parameters of a neural network

### Content
![NYC Picture (Image)](https://www.wine-searcher.com/images/news/74/12/faves1-10007412.jpg)
 
#### Datasets: 
   - wine.csv. Contains data recordings of the wine.
#### Number of Instances
   - Red wine - 1599; white wine - 4898.
### Attribute information:
   For more information, read [Cortez et al., 2009].
   
   -Input variables (based on physicochemical tests):
   1 - fixed acidity
   2 - volatile acidity
   3 - citric acid
   4 - residual sugar
   5 - chlorides
   6 - free sulfur dioxide
   7 - total sulfur dioxide
   8 - density
   9 - pH
   10 - sulphates
   11 - alcohol
   12 - quality (score between 0 and 10)
   
   -Output variable (based on sensory data): 'type' (1: red wine 0:white wine)
   
### Contributor
* Hoang Minh (@Minh6019)

### Method
Below are provided the steps that were followed for this project. Each step and classifiers have their own document.

 1. Data visualization: ploting data to detect missing values, data relations and usefulness of features

![](Images/corr_nn.png)



 3. Preprocessing: apply preprocessing of data including dealing with missing values, drop unuseful features and build new features
    - Build Features and Target: 
         - Feature selection: see above
         - Target: 'type' of the wine {1: red, 0: white}

 3. Classifier: build classifiers **{1: red wine, 0: white wine}** based on Neural Network (Keras)
   - Define the problem as a classification problem
  ![](Images/base_nn.png)

   - Hyper-parameter tuning:
  ![](Images/SGD_learn_rate001_nn.png)

  ![](Images/learn_act_nn.png)

  - Modify the architecture
      - Number of layers
      - Number of neurons per layer
      - Activation functions
     
### Classification techniques with the relative scores
- Option 1: 45 features
  | Classifier	Test     | Parameter  | F1-score  | CV_ROC_AUC_score|
  |---------------------|------------|------------|---------|
  |KNN	|k=5	| 0.95 	| 0.94	|
  |KNN with validation|	k=5	|0.95 |0.94 |
  |KNN with GridSearchCV	| k=1	|0.95	|0.94 |
  |Random Forest with GridSearchCV	| k=100,200	| 0.95	|1.0 |
  
  ![](plot/KNN_validation.png)
  
  #### Conclusion: With the model Random Forest, GridSearchCV gives the highest score.

- Option 2: 84 features
  | Classifier Test | Parameter | F1-Score | CV_ROC_AUC_score |
  | ----------------|-----------|----------|------------------|
  |KNN| k=5| 0.91| 0.89|
  |KNN with validation | k=5| 0.91|0.84|
  |KNN with GridSearchCV| k=4|0.91|0.87|
  |Random Forest with GridSearchCV| K=100,200|0.87|0.95|

   ![](plot/Knn_plot.png)

#### Conclusion: With the model Random Forest, GridSearchCV gives the highest score. 
  

### Folder structures
* Contains all of the jupyter's notebooks including classifiers, preprocessing and data visualization
  | File                     | Description                                                                 |
  |--------------------------|-----------------------------------------------------------------------------|
  | Images folder            | Contains plots' images|
  | 1.DL_wine_01.ipynb   | Python code written in "Jupyter Notebook"  <br>Code used to get the data ready for Machine Learning.  |
  | .README.md           | Information on the assignment                   |  

