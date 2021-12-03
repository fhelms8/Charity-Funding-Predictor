# Charity-Funding-Predictor
Deep Learning/ Machine Learning
<br>
The files are in "Instructions". There is a "testing" file, in which you can see some of my pre-processing before actually attempting to start the starter code. I wanted to try and break down some of the columns before diving into it. 

## Objective
A non-profit foundation, Alphabet Soup, wants to create an algorithm to predict whether applicants for funding will be successful. With my knowledge of machine learning and neural networks, I will use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

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
<img src=https://github.com/fhelms8/Charity-Funding-Predictor/blob/main/Resources/Images%20&%20Results/Starting%20code%20attempt%20results.png?raw=true>

<br>
For my <b>Optimzation</b>:
<br>
<br>
Attempt 1: <br>
* 4 layers (3 hidden node layers, 1 output layer)<br>
* 10 nodes on 1st hidden node layer, 5 on 2nd hidden node layer, 1 on 3rd hidden node layer.<br>
* 4 activation functions: relu, sigmoid, relu, sigmoid (in that order, per layer). <br>
<br>
<br>
I added a layer, added more nodes and kept the same pattern going for the activations, primarily to see where it got me with the accuracy to see what I should adjust for the next. <br>
Results:<br>
<br>
There was a 1% increase in the accuracy.<br>
<img src=https://github.com/fhelms8/Charity-Funding-Predictor/blob/main/Resources/Images%20&%20Results/Attempt%201.png?raw=true>
<br>
Attempt 2: <br>
* 4 layers (3 hidden node layers, 1 output layer)<br>
* 10 nodes on 1st hidden node layer, 6 on 2nd hidden node layer, 3 on 3rd hidden node layer.<br>
* 4 activation functions: relu, sigmoid, relu, sigmoid (in that order, per layer). <br>
<br>
<br>
I had dropped income amounts that were large numbers (which could result in outliers), to see if it made any kind of impact on the results, along with changing some of the nodes. 
Results: <br>
<br>
There was a slight decrease in accuracy but also a slight decrease in the loss category. <br>
<img src=https://github.com/fhelms8/Charity-Funding-Predictor/blob/main/Resources/Images%20&%20Results/Attempt%202.png?raw=true>
<br>
<br>
Attempt 3: <br>
* 4 layers (3 hidden node layers, 1 output layer)<br>
* 4 nodes on 1st hidden node layer, 4 on 2nd hidden node layer, 4 on 3rd hidden node layer.<br>
* 4 activation functions: relu, sigmoid, relu, sigmoid (in that order, per layer). <br>
<br>
<br>
I had dropped more of the income amount and removed some of the nodes that I had added on. (same reason as Attempt 2). 
Results:<br>
<br>
There was a 1% loss in accuracy from Attempt 2 and a slight increase in the loss category. 
<img src=https://github.com/fhelms8/Charity-Funding-Predictor/blob/main/Resources/Images%20&%20Results/Attempt%203.png?raw=true>
<br>
<br>
Attempt 4: <br>
* 3 layers (2 hidden node layers, 1 output layer).<br>
* 5 nodes on 1st hidden node layer, 3 on 2nd hidden node layer.<br>
* 3 activation functions: relu, tanh, sigmoid (in that order, per layer). <br>
<br>
<br>
Prior to doing my other attempts, I made the observation that there were 23k customers that had requested $5000, which also seemed to be a minimum amount, as there were not others lower than that amount. With this in mind, I decided to filter only the $5k, to see if the numbers would change, since there wasn't going to be a big outliers in this column. 
Results: <br>
I was surprised with this result because the epoch accuracy was showing the majority were over 0.80, but allas, it had a lower score than all of the ones combined. I attempted several different ways (adding, removing layers, changing activations, changing node count etc) but this was the best I could get. 
<img src=https://github.com/fhelms8/Charity-Funding-Predictor/blob/main/Resources/Images%20&%20Results/Attempt%204.png?raw=true>


## Summary: 
<br>
Four out of five attempts averaged around 72-73%. There seems to be a consistent score, even with other attempts I had made that are not appart of this chart. I believe if I had more time, I may be able to filter out more of the dataset and run partial column anaylsis (by removing the majority of the columns to narrow it down) that I may be able to get a higher percentage, but I am not positive we will get a much better score. I believe a better dataset would be recommended by adding in some time frames, to get a better idea of which "Ask amt" tier is more successful and then narrowing down the field that way. It would help give more feedback to the company and would help them narrow down how much money they are giving out. 


