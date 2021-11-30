# Charity-Funding-Predictor
Deep Learning/ Machine Learning

## Objective
A non-profit foundation, Alphabet Soup, wants to create an algorithm to predict whether applicants for funding will be successful. With my knowledge of machine learning and neural networks. I will use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Data Preprocessing

<b>What variable(s) are considered the target(s) for your model? </b> <br>
My target of choice was  "IS_SUCCESSFUL" primarily because it captures prior charity fundings that were successful in the past, whereas a non-successful wouldn't be beneficial. 

<b>What variable(s) are considered to be the features for your model? </b> <br>
The 2 main features are "APPLICATION_TYPES" & "CLASSIFICATION".
<br>
<b>What variable(s) are neither targets nor features, and should be removed from the input data?</b><br>
<br>
There were several columns that could be used but right off the bat, I removed EIN & NAME, as they were not needed for this dataset. <br> 
<br>
On my <b>2nd</b> attempt on "AlphabetSoupCharity_Optimzation.ipynb" I removed "INCOME_AMT_5M-10M, INCOME_AMT_50M+, & AFFILIATION_CompanySponsored" as I wanted to lower the amount of larger numbers that may have too many outliers. <br>
<br>
On my <b>3rd</b> attempt, I removed "INCOME_AMT_10M-50M, INCOME_AMT_1M-5M, & ORGANIZATION_Corporation", to lower the larger numbers even more. <br>
<br>
On my <b>4th</b> and final attempt, I created another bin "ASK_AMT" but filtered it for numbers less than 2000, which reflects only the $5k ask amounts. <br>

## Compiling, Training, and Evaluating the Model

<b>How many neurons, layers, and activation functions did you select for your neural network model, and why?</b><br>
<br>
For the <b>Starter Code</b>, I had the following: <br>
* 3 layers (2 hidden node layers, 1 output layer).<br>
* 8 nodes on 1st hidden node layer, 5 on 2nd hidden node layer.<br>
* 3 activation functions: relu, relu, sigmoid (in that order, per layer). <br>
<br>
I attempted to do a basic layer/node/activation setup to start to get the general basis of what I was looking at and looking for, before attempting the other trials. 
<br>
Results: <br>


<br>
For my <b>Optimzation</b>:
<br>
<br>
Attempt 1: <br>
* 4 layers (3 hidden node layers, 1 output layer)<br>
* 10 nodes on 1st hidden node layer, 5 on 2nd hidden node layer, 1 on 3rd hidden node layer.<br>
* 4 activation functions: relu, sigmoid, relu, sigmoid (in that order, per layer). <br>
<br>
Attempt 2:
* 




