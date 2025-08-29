# Test/Train
I had seperated my data set so that a random 80% was trained and a random 20% was tested - WRONG!!


Initially I wanted to create three seperate models. Linear Regression (LR), Neural Network (NN), and Random Forest (RF). However, I came across a problem as the error predictive nature of each was significantly low. Therefore, I decided to only do LR and in the future look into the other two.


## Before Feature Engineering:

**LR R^2 value** - 0.2171938793737126 

The higher the error prediction th better the model.

As my data has been cleaned (anomalies an unknowns removed), I found that feature engineering needed to be done to increase these values.
And I potenitally need to split my model into training and test sets differently.

## 1. Feature Engineering 
- Extract date and time features including sine and cosine waves
- Data spans from 2008-2018 making it cyclical


#### Cylical Data 
- As the hours go from 0 to 23 then back to 0 and days of week (as assigned by me) go from 0 to 6 and back to 0. The machine learning model may think these numbers ae far apart when in fat they are adjacent tp one another
- By conerting a cyclical variable into a sine and cosine components it allowstransitions to 0 an the maximum value to be smooth

- x(sin) ​= sin(2πx/max_val​),   x(cos​) = cos(2πx​/max_val)

#### Intoducing a Lag
- This provides temporal contxt so the model has 'memory' of past values

## 2. Splitting into train/test sets
   - Initially I did it randomly into 80/20, howeer this is not representative of real life so instead I made one year a test set (2018) and the remaining trainign sets
 
  ## After Featue Engineering: 

  **LR R^2 value** - 0.9609149070390977

  
