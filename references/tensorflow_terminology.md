# Tensorflow Terminologies
(Taken from this [link](https://medium.com/google-cloud/a-tensorflow-glossary-cheat-sheet-382583b22932))
-   **Train/Eval/Test** — Training is data used to optimize the model, evaluation is used to asses the model on new data during training with new data, test is used to provide the final result
-   **Classification/Regression —** Regression is prediction a number (e.g. housing price), classification is prediction from a set of categories or output classes (e.g. prediction the color of a house from red/blue/green).
-   **Linear regression-** A classic way of predicting an output by multiplying and summing input features with weights and biases. Useful for regression
-   **Logistic regression —** Similar to linear regression but predicts a probability, useful for classification.
-   **Neural network —** Like linear/logistic regression, but with the addition of an activation function, that makes it possible to predict outputs that are not linear combinations of inputs. Often intermediate layers of nodes are used “deep learning”.
-   **Weights / biases** — Weights are values that the input features are multiplied by to predict an output value. Biases are the value of the output given a weight of 0.
-   **Converge —** An algorithm that converges will eventually reach the optimal answer, even if very slowly. An algorithm that doesn’t converge may never reach the optimal answer.
-   **Learning rate**  — How quickly the optimizers changes weights and biases. Generally a high learning rate trains faster but risks not converging, whereas a lower rate trains slower
-   **Overfitting —** When the model performs great on the input data but poorly on the eval or test data
-   **Bias/Variance** —How much the output is determined by the features. more variance often can mean overfitting, more bias can mean a bad model
-   **Regularization**  — Variety of approaches to reduce overfitting, including adding the weights to the loss function, randomly dropping layers (dropout).
-   **Epochs** — How many times you run the optimization over the training data
-   **Batch size —** How many training examples you optimize for a time
-   **Ensemble learning** — Training multiple models with different parameters to solve the same problem
-   **Numerical instability —** Many deep learning algorithms can run issues with very large or very small values due to the limits of floating point number representations in computers
-   **Gradient explosion**- A common case of numerical instability
