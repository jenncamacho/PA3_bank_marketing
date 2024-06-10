# PA3_bank_marketing
Using classification to predict if the bank client will subscribe a term deposit. 

The data pertains to direct marketing campaigns (phone calls) conducted by a Portuguese banking institution.

# Documents
Notebook: https://github.com/jenncamacho/
bank-additional-full.csv with all examples (41188) and 20 inputs

## Business Understanding 
 The objective is to develop the best model to classify whether a client will subscribe to a term deposit (variable y). Through this exploration, key features used to generate the models will be identified and bank marketing teams can develop a more effective campaign. The goal is to increase efficiency of directed campaigns for long-term deposit subscriptions by reducing the number of contacts to do. 

By understanding the best features and attributes to generate the best models, the bank's marketing team can divert their attention and resources to leverage these features to increase the number of subscriptions for term deposits.

## Data Understanding

- ### Summary and Insights of the Dataset for Predicting Term Deposit Subscriptions

This dataset pertains to direct marketing campaigns conducted by a Portuguese banking institution, where the primary mode of outreach was through phone calls. The goal is to accurately predict whether a bank client will subscribe to a term deposit based on the provided data.

#### Dataset Overview

There are four distinct datasets available, data modeling is conducted on the following dataset:

1. **bank-additional-full.csv**: Contains 41,188 examples with 20 input features, ordered chronologically from May 2008 to November 2010. 

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

## Plot shows that the dataset needs to be scaled:

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

| Model              | Train Time (s) | Train Accuracy | Test Accuracy | Train Precision | Test Precision | Train Recall | Test Recall |
|--------------------|----------------|----------------|---------------|----------------|---------------|--------------|-------------|
| LogisticRegression | 0.398813       | 0.871146       | 0.873367      | 0.727586       | 0.714596      | 0.562705     | 0.556600    |
| KNearestNeighbors  | 0.028972       | 0.892789       | 0.869883      | 0.794366       | 0.697347      | 0.674464     | 0.618765    |
| SVC                | 3.387884       | 0.866269       | 0.870580      | 0.433134       | 0.435290      | 0.500000     | 0.500000    |
| DecisionTree       | 0.047040       | 0.952447       | 0.848284      | 0.962203       | 0.642278      | 0.829642     | 0.611516    |



### Next steps and recommendations

#### The bank should consider the following numeric features which provide the greatest impact to the best model:

- age
- campaign
- previous
- emp.var.rate
- cons.price.idx

#### The best model based on accuracy of the test dataset is Logistic Regression with an accuracy of 87.3%
- cons.conf.idx
- euribor3m
- nr.employed




## License

This dataset is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.
This allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.
This project is open source.

