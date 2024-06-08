# PA3_bank_marketing
Using classification to predict if the bank client will subscribe a term deposit. 

The data pertains to direct marketing campaigns (phone calls) conducted by a Portuguese banking institution.

# Documents
Notebook: https://github.com/jenncamacho/
Presentation: https://docs.google.com/
bank-additional-full.csv with all examples (41188) and 20 inputs

## Business Understanding 
 The objective is to develop the best model to classify whether a client will subscribe to a term deposit (variable y). Through this exploration, key features used to generate the models will be identified and bank marketing teams can develop a more effective campaign. 

By understanding the best features and attributes to generate the best models, the bank's marketing team can divert their attention and resources to leverage these features to increase the number of subscriptions for term deposits.

## Data Understanding
From an original dataset containing information on 3 million used cars the dataset I’m working with has 426,880 rows with 18 columns or features that are numeric, categorical, and unstructured objects.
### Data Understanding and Features Related to the Business

- The dataset is unbalanced, with only 6557 records (12.38%) indicating successful outcomes.
## Data Preparation and Visulalization
<pre>
Code Used: Python
Packages: Pandas, plotly, matplotlib, seaborn
</pre>

Explored the unique values, counts, and null values for all features
- All NaN values in the 'condition' column have been replaced with 'good'  (170, 204)
- Count of 'salvage' values in 'condition' column: 225 - I will remove these rows
- Alot of values are missing in “drive” and does not account for all-wheel-drive and have two values for 4wd and fwd.  Since it is missing 130k values I will remove this column
-Transmission.  78.5% are automatic.  0.62 % is Nan values.  This column does not appear to provide distinguishable insights that would determine price. 
- Paint_color is missing 126,383.  I attempted to replace null values with car paint colors that tends to be price-neutral, such as white, black, silver, and gray are typically good choices. Since there is still high demensionality in the dataset and color does not significantly drive a high price, this column was removed. 
- Size is missing 72% and Cylinders is missing 42% of the vales.  Remove the Cylinder column.  Keep Size and remove missing rows.
- These tactics of dealing with Nan values is comparable to replacing with a mean value. 
- Filter rows where 'title_status' column contains 'clean' then removed the column since all values in the column are the same: 'clean'
- Rows with missing price, many rows with unbelievable car prices either too high (above $150,000 or too low, under $4,000)

## Data Processing and Modeling
<pre>
Code Used: Python
Packages: Pandas, sklearn, numpy, scipy
Instructions: Please run the notebook in sequence
<<Notebook link>>
</pre>

The goal was to develop the best model to predict whether a client will subscribe a term deposit by: 

⦁	Applying various classification methods to a business problem
⦁	Comparing the results of k-nearest neighbors, logistic regression, decision trees, and support vector machines
⦁	Developing a problem statement that includes a research question, expected data sources and structure, expected results, and expected techniques


### Next steps and recommendations

####The bank should consider the following features which provide the greatest impact to the best model

- feature 1 
- feature 2




## License
This project is open source.


