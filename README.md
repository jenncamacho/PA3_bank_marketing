# PA3_bank_marketing

# Documents
Notebook: https://github.com/jenncamacho/PA3_bank_marketing/blob/main/prompt_III_PREP.ipynb

bank-additional-full.csv with all examples (41188) and 20 inputs

## Business Understanding 
 The objective is to develop the best model to classify whether a client will subscribe to a term deposit (variable y). Through this exploration, key features used to generate the models will be identified and bank marketing teams can develop a more effective campaign. The goal is to increase efficiency of directed campaigns for long-term deposit subscriptions by reducing the number of contacts to do. 

By understanding the best features and attributes to generate the best models, the bank's marketing team can divert their attention and resources to leverage these features to increase the number of subscriptions for term deposits.

## Data Understanding

- ### Summary and Insights of the Dataset for Predicting Term Deposit Subscriptions

This dataset pertains to direct marketing campaigns conducted by a Portuguese banking institution, where the primary mode of outreach was through phone calls. The goal is to accurately predict whether a bank client will subscribe to a term deposit based on the provided data.

Using classification to predict if the bank client will subscribe a term deposit. 

#### Dataset Overview

There are four distinct datasets available, data modeling is conducted on the following dataset:
The data pertains to direct marketing campaigns (phone calls) conducted by a Portuguese banking institution.

- **bank-additional-full.csv**: Contains 41,188 examples with 20 input features, ordered chronologically from May 2008 to November 2010. 

#### Data Collection and Characteristics

- **Time Frame**: The data spans from May 2008 to June 2013, encompassing a total of 52,944 phone contacts.
- **Imbalance**: The dataset is notably unbalanced, with only 6,557 (12.38%) instances of successful term deposit subscriptions.
- **Training and Test Split**: For evaluation, a time-ordered split is used:
  - **Training Data**: Consists of contacts up to June 2012, totaling 51,651 examples. This data is used for feature and model selection.
  - **Test Data**: Comprises the most recent 1,293 contacts from July 2012 to June 2013, used to measure the prediction capabilities of the model.

#### Target Variable

- **Output Variable**: `y` - Indicates whether the client subscribed to a term deposit (binary: "yes", "no").

By utilizing this dataset, the aim is to develop a machine learning model that can accurately predict whether a client will subscribe to a term deposit, aiding the bank in targeting their marketing efforts more effectively. The detailed feature set and extensive historical data provide a solid foundation for building robust predictive models.

## Data Preparation and Visulalization

Explored the unique values, counts, and null values for all features

- removal of irrelevant features. 
- remove "unknown" values (these are the equivelant to NaN values)
- removing duplicate values (rows)

## Histogram showing distribution of numeric features
![image](https://github.com/jenncamacho/PA3_bank_marketing/assets/161406309/c40ef5c5-56cc-4846-91a2-fa82aeea07cf)
## Pairplot

![image](https://github.com/jenncamacho/PA3_bank_marketing/assets/161406309/62693a29-eebd-4437-9bcc-99d7f76791dc)

# List of columns to drop
columns_to_drop = ['duration', 'default', 'day_of_week', 'pdays']

## The Plot demonstrates that the dataset needs to be scaled:

![image](https://github.com/jenncamacho/PA3_bank_marketing/assets/161406309/3bfd6252-c41a-40b7-84b3-9e5b45d65a22)

## This plot shows that the dataset has been successfully scaled:

![image](https://github.com/jenncamacho/PA3_bank_marketing/assets/161406309/b785a444-4116-423f-9c3e-c55c44d03ecc)


## Data Processing and Modeling
<pre>
Code Used: Python
Packages: Pandas, sklearn, numpy, scipy
Instructions: Please run the notebook in sequence
<<Notebook link>>
</pre>

### Train/Test Split
With your data prepared, split it into a train and test set.
The goal was to develop the best model to predict whether a client will subscribe a term deposit by: 

- Building a Baseline Model before building the first model
- Applying various classification methods to the business problem
- Comparing the results of k-nearest neighbors, logistic regression, decision trees, and support vector machines


### Recommendations

#### The bank should consider the following numeric features which provide the greatest impact to the best model and target marketing campaign strategies based on these features:

- age
- campaign
- previous
- emp.var.rate
- cons.price.idx
- cons.conf.idx
- euribor3m
- nr.employed

#### The best model based on accuracy of the test dataset is Logistic Regression with an accuracy of 87.3%


| Model              | Train Time (s) | Train Accuracy | Test Accuracy | Train Precision | Test Precision | Train Recall | Test Recall |
|--------------------|----------------|----------------|---------------|----------------|---------------|--------------|-------------|
| LogisticRegression | 0.398813       | 0.871146       | 0.873367      | 0.727586       | 0.714596      | 0.562705     | 0.556600    |
| KNearestNeighbors  | 0.028972       | 0.892789       | 0.869883      | 0.794366       | 0.697347      | 0.674464     | 0.618765    |
| SVC                | 3.387884       | 0.866269       | 0.870580      | 0.433134       | 0.435290      | 0.500000     | 0.500000    |
| DecisionTree       | 0.047040       | 0.952447       | 0.848284      | 0.962203       | 0.642278      | 0.829642     | 0.611516    |

### Model Performance
Logistic Regression has the highest test accuracy (0.873367) and a balanced precision (0.714596) and recall (0.556600). It performs consistently well on both the training and test sets, indicating a good generalization. K-Nearest Neighbors also shows high test accuracy (0.869883) and relatively balanced precision (0.697347) and recall (0.618765). It has the fastest training time, which might be an advantage if training speed is crucial. SVC has similar test accuracy (0.870580) to Logistic Regression and KNN but shows significantly lower precision and recall. This suggests that while it can separate the classes well, it might not be as reliable for imbalanced classes or more nuanced predictions. Decision Tree has the highest train accuracy (0.952447) but lower test accuracy (0.848284), indicating overfitting. Although it has high precision (0.642278) and recall (0.611516) on the test data, the drop from training performance suggests it may not generalize as well as the other models.

### Model Stability and Generalization:
Logistic Regression shows stable performance with minimal overfitting, making it a reliable choice. K-Nearest Neighbors also shows minimal overfitting with a slightly lower but still competitive test accuracy. SVC's low precision and recall might make it less desirable unless further tuning or different kernel functions can improve its performance. Decision Tree shows signs of overfitting, indicating it might need pruning, more data, or additional tuning to improve generalization.

### Training Time Consideration:
K-Nearest Neighbors has the fastest training time, which might be beneficial for very large datasets or when quick retraining is necessary. Logistic Regression has a reasonable training time and good performance, making it a balanced choice. SVC takes significantly longer to train, which might not be ideal for all applications. Decision Tree also has a quick training time but suffers from overfitting.

### Final Recommendation:
**Based on the analysis, the best models for predicting whether a client will subscribe to a deposit term are Logistic Regression and K-Nearest Neighbors.**

Logistic Regression is recommended for its overall balance between accuracy, precision, recall, and training time. K-Nearest Neighbors is also a strong candidate, especially if training time is a critical factor.



### License

This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
This allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.
This project is open source.

