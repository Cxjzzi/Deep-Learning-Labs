# Deep Learning Laboratories 2 & 3

This lab compares a traditional supervised-learning model with a shallow neural network to predict the net electrical power output of a combined-cycle power plant.

## Problem

I am predicting the plant's net electrical power output from its operating and environmental conditions. This is a regression problem because the output is a continuous numerical value.

## Dataset

The notebook uses `power_plant.csv`, which contains 9,568 observations. The four inputs are:

| Input | Description |
|---|---|
| `AT` | Ambient temperature |
| `V` | Exhaust vacuum |
| `AP` | Ambient pressure |
| `RH` | Relative humidity |

The target is `PE`, the net electrical power output.

## Models

I compared linear regression as the baseline with a shallow neural network using one hidden layer and a ReLU activation. The data was split into training, validation, and test sets, and the input scaler was fit using only the training data.

## Evaluation

I used mean absolute error (MAE), root mean squared error (RMSE), and the coefficient of determination (\(R^2\)). The results below are from the notebook's final test-set evaluation.

| Model | MAE [MW] | RMSE [MW] | \(R^2\) |
|---|---:|---:|---:|
| Linear regression | 3.655 | 4.654 | 0.925 |
| Shallow neural network | 442.247 | 442.567 | -678.461 |

## Main Result

Linear regression performed much better on the final test set. The neural network's recorded test errors were extremely high, and its negative \(R^2\) indicates that it performed worse than predicting the test-set mean.

## Engineering Conclusion

Based on these results, I would not use the neural network in practice in its current form. Linear regression was far more accurate on this test set, but I would still check the neural network's training and scaling before drawing a final conclusion about the model. Before using either model at a power plant, I would also validate it on additional operating data and account for conditions that are not included in these four inputs.

## Notebook

[Open the lab notebook](https://github.com/Cxjzzi/Deep-Learning-Labs/blob/main/lab02-03/Deep_Learning_Lab2_3.ipynb)
