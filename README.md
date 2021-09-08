## DL-wine-quality

## Mission objectives

- Use a deep learning library
- Prepare a data set for a machine learning model
- Put together a simple neural network
- Tune parameters of a neural network

### Content
![NYC Picture (Image)](https://www.wine-searcher.com/images/news/74/12/faves1-10007412.jpg)
 - For the experiments device shown on the picture was constructed. Two bearings were installed on the shaft. The rotation speed changed from 0 to 1500 rpm, was held for 10 seconds, and decreased to 250 rpm. 
 - The shaft was rotated using an DC motor connected to the shaft through a coupling. A radial load of 3.5 kg is applied to the shaft using a balanced weight.
The bearings were mounted on the shaft as shown in Figure 1. 
- GY-61 ADXL3353 accelerometers were mounted on the bearing housing 
- The sensor location is also shown in Figure. 
- The recording was saved along the x, y, z axes.
#### Datasets: 
   - wine.csv. Contains data recordings of the wine.
#### Number of Instances
   - Red wine - 1599; white wine - 4898.
### Attribute information:
   For more information, read [Cortez et al., 2009].
   
   Input variables (based on physicochemical tests):
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
   Output variable (based on sensory data): 'type' (1: red wine 0:white wine)
   
### Contributor
* Hoang Minh (@Minh6019)

### Method
Below are provided the steps that were followed for this project. Each step and classifiers have their own document.

 1. Data visualization: ploting data to detect missing values, outliers, data relations and usefulness of features

![](plot/Distribution_vibration.png)

![](plot/boxplot_hert.png)


 3. Preprocessing: apply preprocessing of data including dealing with missing values, drop unuseful features and build new features
    - Build Features and Target: 
         - Feature selection: 
         - Target: 'type' of the wine {1: red, 0: white}


 3. Classifier: build classifiers based on the preprocessed data using a variety of techniques
   - Define the problem as a classification problem
   - Define the problem as a regression problem
   - Feature engineering
   - Feature normalization
   - Resampling
   - Hyper-parameter tuning
      - Change the learning rate
      - Change the loss function
  - etc...
  - Modify the architecture
      - Number of layers
      - Number of neurons per layer
      - Activation functions
      - etc...
      - etc...
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

