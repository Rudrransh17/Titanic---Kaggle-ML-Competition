# Titanic Survival Prediction

This repository contains a solution to the Titanic survival prediction competition on Kaggle. The goal of the competition is to develop a model that predicts the survival of passengers aboard the Titanic based on various features.

## Competition Details

Competition Link: [https://www.kaggle.com/competitions/titanic](https://www.kaggle.com/competitions/titanic)

## Data Description

The dataset used for this competition contains the following features:

- `Survival`: Survival (0 = No, 1 = Yes)
- `Pclass`: Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd)
- `Sex`: Sex
- `Age`: Age in years
- `SibSp`: Number of siblings/spouses aboard the Titanic
- `Parch`: Number of parents/children aboard the Titanic
- `Ticket`: Ticket number
- `Fare`: Passenger fare
- `Cabin`: Cabin number
- `Embarked`: Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

### Variable Notes

- `Pclass`: A proxy for socio-economic status (SES)
  - 1st = Upper
  - 2nd = Middle
  - 3rd = Lower
- `Age`: Age is fractional if less than 1. If the age is estimated, it is in the form of xx.5
- `SibSp`: The dataset defines family relations in the following way:
  - Sibling = brother, sister, stepbrother, stepsister
  - Spouse = husband, wife (mistresses and fiancés were ignored)
- `Parch`: The dataset defines family relations in the following way:
  - Parent = mother, father
  - Child = daughter, son, stepdaughter, stepson
  - Some children travelled only with a nanny, therefore `Parch = 0` for them.

## Approach

For building the prediction model, the following steps were taken:

1. Dropped the `Name` and `Ticket` columns as they were not considered relevant for the prediction.
2. Performed label encoding on the `Sex`, `Cabin`, and `Embarked` columns to convert them into numerical representations.
3. Filled the missing values in the `Age` column with the average age.
4. Split the data into training and validation sets with a validation size of 0.1.
5. Created a neural network model using TensorFlow's Keras API. The model architecture consisted of three dense layers with 2048 units each, followed by batch normalization and dropout layers. The final layer used the sigmoid activation function for binary classification.
6. Compiled the model using the Adam optimizer and binary cross-entropy loss function. Accuracy was used as the evaluation metric.
7. Trained the model on the training data for 50 epochs with a batch size of 512, using the validation data for validation during training.
8. Made predictions on the test data (`test.csv`) and saved them in `submission.csv`.
9. Submitted the predictions on Kaggle and achieved 71% accuracy on the test data.

## Repository Contents

- `notebook.ipynb`: Jupyter Notebook containing the code and explanation of the solution.  
- `train.csv`: CSV file containing the training data.
- `test.csv`: CSV file containing the test data.
- `submission.csv`: CSV file containing the predictions made on the test data.

## Requirements

The following dependencies are required to run the code:

- TensorFlow
- Pandas
- NumPy

## Usage

To reproduce the results or modify the solution, follow these steps:

1. Clone this repository: `git clone [repository_url]`
2. Navigate to the cloned repository.
3. Ensure that you have the required dependencies installed.
4. Open the Jupyter Notebook `notebook.ipynb` in Jupyter Notebook or any compatible environment.
5. Run the notebook cell by cell to execute the code and reproduce the solution.
6. Once the model is trained and the predictions are made on the test data, you can find the submission file `submission.csv` in the repository.
7. Use the `submission.csv` file to submit your predictions to the Kaggle competition and evaluate the accuracy of your model on the test data.

Feel free to explore the code, make modifications, and experiment with different models and hyperparameters to improve the prediction accuracy.

If you encounter any issues or have any questions, please feel free to reach out.
