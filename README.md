# Predicting Accident Severity for Taxis in the UK

***Code files uploaded as pdf above***

## 1. Project Overview

This project predicts the severity of taxi accidents in the UK before they occur using historical accident data.

This was originally developed as part of my Master's in Business Analytics - ML course at Aston University. 

The model uses road conditions, weather conditions, driver-related information and other key metrics to predict accident severity

## 2. Problem Definition

Taxi and ride hailing apps face the risk of accidents which can affect passenger satisfaction, claims against the company and pricing. Traditional operational strategies ignore pre-trip information such as weather, road conditions and other key details. This leads to missed opportunities for risk reduction, cost optimisation and safer fleet management

## 3. Goal

Predict severity of taxi collisions for ride hailing apps before trip begins, using pre-accident data available at time of booking

## 4. Data

Source: Data was sourced from data.gov.uk. The link to the datasets used can be found at https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-accidents-safety-data
(Specific Data files used: 'Road Safety - Vehicles last 5 years' and 'Road Safety - Collisions last 5 years')

Original Data size: Vehicles data - 34 Columns and 953,000+ rows, Collisions data - 27 Columns and 500,000+ rows (After filtering, the total rows were 12,808)

## 5. Methodology

The project was developed in 2 main phases
a. EDA and preprocessing ('Predicting Taxi accidents severity in UK - Part 1 - EDA and preprocessing.pdf')
  - Identifying key trends and relationships
  - Outlier detection
    
b. Model Development ('Predicting Taxi accidents severity in UK - Part 2 - Model Development.pdf')
  - Class imbalance handling
  - Dummy variable encoding
  - Model development and Hyper Parameter tuning

## 6. Results

Initial testing with the training data showed the following results:

<img width="434" height="326" alt="image" src="https://github.com/user-attachments/assets/e2aad1ae-5f2b-4595-92ac-5613f709915f" />

The best 2 models were re-trained with more hyperparameter tuning and evaluated on the test data. Further feature selection was also done.

The results of the decision tree were as follows:

<img width="338" height="100" alt="image" src="https://github.com/user-attachments/assets/6ac043d1-435f-4d76-9158-46f2f38fbddb" />

<img width="594" height="336" alt="image" src="https://github.com/user-attachments/assets/3232407c-78c4-4ec5-8800-f2b76015b097" />


The results of the random tree were as follows:

<img width="348" height="117" alt="image" src="https://github.com/user-attachments/assets/ae7617b1-094f-4450-8d22-23784339ef1e" />

<img width="584" height="338" alt="image" src="https://github.com/user-attachments/assets/0b2d2fc9-714e-4f0c-88e0-7db088c6b6ba" />

## 7. Conclusions and limitations

The aim of this project was to build a machine learning model that can effectively predict the severity of an accident for taxi and ride hailing companies during trip booking. This can allow them to price the trips accordingly, assist them in negotiating insurance prices and plan out better routes. The data used ranged from 2019 to 2023 and was filtered to include only taxis or private car hires.

After feature selection and some further tuning, the decision tree performed slightly better on the training data than with the previous inputs, suggesting model imporovement. The same was not true for the random forest model, but the difference in model scores was too small to make a significant difference.

On the test data, the random forest model performed better than the Decision Tree model with an F-score of 0.533 and a **higher recall** score as well. It also made better predicitions with the majority class of non-severe accidents with 65.3% correct predictions in this class.

However, the decision tree was better at **predicting severe cases** correctly with 61.4% severe cases predicted correctly.

Overall, the random forest got 63% of the predictions correctly while the decision tree got only 52.3% of the predictions correct. This makes the random forest much better at prediction of severity of cases

### Limitations and future improvements

a. Because of limited computing power, some key variables were left out such as latitude and longitude which would give better location information. As such, the goal of route planning may not be achieved with the models created above but the other goals can be met.
   
b. For the same constraint above, limited hyper parameters were tuned on the different models tested with. For instance, the CATBoost model which I anticipated would provide the best results did not perform as well. There is a possibility that if more hyperparameters were tuned, better models might have been created.

c. An accuracy score of 63% with an fscore of 0.533 is not the best model to use. Adding more recent data (2024) is essential and trying out better models might be critical if the model is to be used in real life.

## 8. Technologies Used
- Python (Pandas, Numpy, Matplotlib, Plotly, Scikit-learn )
- Jupyter Notebooks


