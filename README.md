# Predicting Cardiovascular Disease

[Slide Deck](https://docs.google.com/presentation/d/1kPJgIdu8fuf2Ci5hB6wL9CPa2ewXVI9GY5zz5iTyj_w/edit#slide=id.p)

[Dashboard](https://signin.aws.amazon.com/oauth?response_type=code&client_id=arn%3Aaws%3Aiam%3A%3A015428540659%3Auser%2Fspaceneedle-prod&redirect_uri=https%3A%2F%2Fca-central-1.quicksight.aws.amazon.com%2Fsn%2Fdashboards%2Fbf9360c4-48b7-4e83-a389-e226f7c1da59%3Fstate%3DhashArgs%2523%26isauthcode%3Dtrue&forceMobileLayout=0&forceMobileApp=0)<br> 
An AWS account for is needed for this. Available upon request. Please view the dashboard demonstration video below as an example.

[Dashboard Demonstration Video](https://github.com/christopher-ko-law/predicting-cvd/blob/main/Resources/dashboard-demo.mov)<br>

[Web App Demonstration Video](https://github.com/christopher-ko-law/predicting-cvd/blob/main/Resources/website-demo.mov)<br>

## Project Overview

Cardiovascular Disease (CVD) is the leading cause of death globally, making up approximately 32% of deaths in 2019. In this project, we will analyze objective, examination, and subjective data of 70,000 patients. We will use classification machine learning models to predict the presence of CVD and determine which features are most determinative of the presence of CVD. 


## Project Description
The project focuses on using a database of 70,000 patients with key objective, subjective, and medical examination metrics in order to predict risk of cardiovascular disease. The raw data was uploaded to the database and merged to form one large table for machine learning. This included 3 tables with subjective, objective, and medical examination data. CDC data was also uploaded with data on key disease mortality rates in the United States to provide an impact report within the dashboard. Database setup can be found in the Technology and Pipeline folder. Data was preprocessed (see Preprocessing folder) and explored in AWS' Quicksight. The exploratory analysis/ dashboard can be found in the dashboard. Data was then put through multiple machine learning models (see below), with a 73% accuracy being achieved using a Neural Network. Finally, the presentation to key stakeholders began development this week. 

## Machine Learning Algorithm

For the Machine Learning portion of this project, we pre-processed data by removing patients with missing data and removing outliers based on medical cutoffs. We then used a simple logistic regression to test the classification problem because we were predicting a binary variable (yes vs no cardiovascular disease). However, the logistic regression classifier can be enhanced by the more complex neural network. We tested the neural network many times, changing the number of epochs, hidden layers, and neurons, as well as the activation functions, generating an accuracy of 73% at its highest. The limitation to using a neural network, however, is how prone it is to overfitting. 

## Analysis

Through our analysis, we found that a person's age, BMI, and blood pressure were the highest predictors of cardiovascular disease, with the greater the value of these features, the more likely the risk of cardiovascular disease. All other features, while not as predictive, were still used to achieve the 73% accuracy. 

## Web App

A form was designed as POC to show off the model. This form takes the following inputs: Age, Gender, Height, Weight, Systolic blood pressure, Diastolic blood pressure, Cholesterol level, Glucose level, Smoker, Alcoholic, Physically active. These inputs will be used to predict whether an individual is at risk of cardiovascular disease. <br>
![Web Form](/Resources/Presentation%20Files/webapp.PNG)<br>
Code for this form can be found in the Technology and Pipeline folder. <br>
The form was created using flask, and was deployed through AWS Elastic Beanstalk. This can be found under /Technology and Pipeline/eb-flask/.<Br>
The endpoint was deployed through AWS SageMaker. This can be found underneath /Technology and Pipeline/sageMaker/model/. 
In order to access the endpoint externally, an API Gateway and Lambda function was used. The configuration can be found in their respective folders.<br>
