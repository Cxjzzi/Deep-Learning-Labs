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

## Figures

The `figures/` folder contains the plots generated in the notebook:

- **Input relationships:** [Temperature](figures/01_temperature_vs_power.png), [exhaust vacuum](figures/02_exhaust_vacuum_vs_power.png), [ambient pressure](figures/03_ambient_pressure_vs_power.png), and [relative humidity](figures/04_relative_humidity_vs_power.png) compared with power output.
- **Linear regression:** [Actual vs. predicted](figures/05_baseline_actual_vs_predicted.png), [residual distribution](figures/06_baseline_residual_distribution.png), and [prediction sample](figures/16_linear_regression_prediction_sample.png).
- **Neural network:** [Training and validation curves](figures/07_neural_network_training_validation_loss.png), [4 hidden neurons](figures/08_hidden_neurons_4_training_validation_loss.png), [64 hidden neurons](figures/09_hidden_neurons_64_training_validation_loss.png), [256 hidden neurons](figures/10_hidden_neurons_256_training_validation_loss.png), [learning rate 0.1](figures/11_learning_rate_0.1_training_validation_loss.png), [learning rate 0.01](figures/12_learning_rate_0.01_training_validation_loss.png), [learning rate 0.001](figures/13_learning_rate_0.001_training_validation_loss.png), [512-neuron selection run](figures/14_512_neuron_selection_training_validation_loss.png), and [final evaluation run](figures/15_final_evaluation_training_validation_loss.png).

## Engineering Conclusion

Based on these results, I would not use the neural network in practice in its current form. Linear regression was far more accurate on this test set, but I would still check the neural network's training and scaling before drawing a final conclusion about the model. Before using either model at a power plant, I would also validate it on additional operating data and account for conditions that are not included in these four inputs.

## Notebook

[Open the lab notebook](https://github.com/Cxjzzi/Deep-Learning-Labs/blob/main/lab02-03/Deep_Learning_Lab2_3.ipynb)
