# Predicting Customer Churn In Banking

## Dataset

The dataset 'Churn_Modelling.csv' contains records of 10,000 customers of bank with following columns:

- RowNumber
- CustomerId
- Surname
- CreditScore
- Geography
- Gender
- Age
- Tenure
- Balance
- NumOfProducts
- HasCrCard
- IsActiveMember
- EstimatedSalary
- Exited

By using all the the features we have to predict whether the user will exit the bank or not.

## Data Preprocessing

- Removing unnecessary features
- Label Encoder
- One Hot Encoder
- Train Test Split
- Standard Scaler


## Simple ANN Model using Keras

- Create ANN with total 4 layers:
    - One input layer with 11 input features and 6 output features
    - Hideen layer with 6 output features
    - Final layer with 1 output feature

- Activation Functions
    - 1st layer: Relu
    - 2nd layer: Relu
    - 3rd layer: Sigmoid

- Hyperparameters
    - optimizer: `'adam'`
    - loss: `'binary_crossentropy'`
    - metrics: `'accuracy'`
    - batch_size: `10`
    - epochs: `100`

- Accuracy(Subject to change)
    - Training Set: 0.8610
    - Testing Set:0.86

## Imporoving ANN

- Use k-fold classifier to split training set in say 10 parts and applying training on 9 out of 10 parts and testinh on another every time to decrease fluctuation in acccuracy every time you run the code.

- Use Dropout technique with certain threshold to decreses overfitting on training set. Applying on this dataset gives accuracy of 0.8321 which meance now data is less overfitted to this tarining set.

- Use `GridSearchCV` to find best parameters automatically. Enter all the hyperparameters you want to test your network on and after testing averythin it will give best possible accuracy and parameters. I tried with following parameters:
    - batch_size
        - `25`
        - `32`
    - epochs
        - `100`
        - `500`
    - optimizer
        - `adam`
        - `rmsprop`

- After waking in the morning(yes, it takes long time...), this is what I found:
    - best_parameters
        - batch_size: `25`
        - epochs: `500`
        - optimizer: `rmsprop`
    - accuracy
        - 0.8545

## Further Improvements

You can further imporve this model by changing hyperparameters and trying other range of values in GridSearchCV. But it is important to note that, as you will increase number of parameters in GridSearchCV, your time for training will also increase.

Any suggestions, always welcome! 

Send a pull request, if you see any errors...