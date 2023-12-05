# Assignment-20-Machine-Learning
This is a repository for module challenge 20 which focus on supervised machine learning with the loan as an example.

<h2> The Datasource</h2>
There are two files in the repository:
1. The lending_data.csv which resides in the Resources folder contains the data used for machine learning
2. credit_risk_classification.ipynb which is the main code script containing the script for supervised machine learning. </br>

![image](https://github.com/Nisloen/Assignment-20-Machine-Learning/assets/134130254/c9cfddeb-9921-4e28-aae3-dd3e4b064745)


<h3> Overview of Analysis</h3>
The main point of the script is to take known data from previous results to train the machine to learn its pattern in order to 
make predictions in the future. In this repository, the datasource contains various financial data, however the main column in which the machine learning is collecting training data from 
is the loan_status that reads out two results;
'0' meaning healthy loan (good loan)
'1' meaning high-risk loan (dangerous loan)

The idea of having the machine to learn the training data is that the known loan status are refering to the overall loan information from interest rate to debt to income etc. Therefore, when
a new data comes in, the machine would then make a prediction on whether that loan is good or dangerous based one two aspects:
- what are current financial and loan information it gives
- what the historical/training data suggest in references

<h4>Process in creating the supervised machine learning</h4>
The first thing to do was to create the DataFrame through Panda (which was edited through Jupyter Notebook). Then the main column ["loan_status"] was chosen has the training data, so it was remove 
and kept as a seperate variable (X) while the remaining columns reside in a different variable (y).
With sklearn.model import, traing data and test data for both variables are created with a set random_state for consistency.
For the chosen model, the logistic Regression model was chosen for the training data.

<h5> What's logistic regression?</h5>
the logistic regression is a model that has a two value from the y-axis (0 and 1) and it will end in one of the two group based on the variables or values. This is used in the assignment as a way to take
all of the financial information and convert the data to either lean to 0 or 1. </br>

![image](https://github.com/Nisloen/Assignment-20-Machine-Learning/assets/134130254/b0d7ae43-0319-47c5-9765-747aa61f37ca)


### Results
With the supervised machine learning, through logistic regression, the overall confusion matrix result that was achieved is shown below: </br>
![image](https://github.com/Nisloen/Assignment-20-Machine-Learning/assets/134130254/15be2132-7ef2-4dc8-8498-c1f078b1e6e1)

And below is the classification report in reference to the model's performance: </br>
![image](https://github.com/Nisloen/Assignment-20-Machine-Learning/assets/134130254/906263d5-a15e-4aef-a344-68176adf80a8)

The result shows that the machine can accurately predict the '0' perfectly, however for the '1' with a precision score of 0.85, it means that 15% of the time it wouldn't get it right, this is also supported
with the recall score with a score of 0.91. This means that out of all of the data from all of data indentified as positive from the machine, 91% are correct. The accuracy of the overall result is 0.99 (99%)
which is true as the confusion matrix showed about 102 of the tested data are in the false positive. 

### Summary

Based on the model's performance, it's likely that this model can be a usefule tool in predicting good loans from the bad loans, despite not being 100% precise. Although the accuracy score of 0.99 isn't convincing
enough. Both the precision and recall does help in that factor. For the 0 which is the good loan, the score is close 1.00 which a strong support in stating that it is very good at predicting good loans.
Although, for the 1 which is the bad loan, the machine did struggle a bit, but I presume it's due to the wide margin in what is a bad loan.
Realistically, the model takes all of the financial statistics are a factor to determine whether it leans towards 0 or 1. There may be some loans where one of the data may have outweigh the other data.
