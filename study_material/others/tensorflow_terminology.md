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
-   **Bias/Variance —** How much the output is determined by the features. more variance often can mean overfitting, more bias can mean a bad model
-   **Regularization**  — Variety of approaches to reduce overfitting, including adding the weights to the loss function, randomly dropping layers (dropout).
-   **Epochs** — How many times you run the optimization over the training data
-   **Batch size —** How many training examples you optimize for a time
-   **Ensemble learning** — Training multiple models with different parameters to solve the same problem
-   **Numerical instability —** Many deep learning algorithms can run issues with very large or very small values due to the limits of floating point number representations in computers
-   **Gradient explosion**- A common case of numerical instability
- **Label**: The correct classification/value
- **Input**: Predictor Variables - Example: Input + Label sample to train your model
- **Model**: Mathematical function, Some work is done on inputs for an output
- **Training**: Adjusting Variable weights in a model to minimize error
- **Prediction**: Using the model to guess the label for an input - Supervised Learning: Training your model using examples data to predict future data
- **Unsupervised Learning**: Data is analyzed without labels for patterns or clusters
- **Neuron**: A way to combine inputs and weighting them to make a decision (it is one unit of input combination)
- **Gradient Descent**: The process of testing error in order to minimize its value iteratively decreases towards a minimum. (This can be global or local maximum and starting points and learning rates are important to ensure the process doesn’t stop at local minima. Too low a learning rate and your model will train slowly, too high and it may miss the minimum)
- **Hidden Layer**: A set of neurons that act on the same input data.
- **Features**: The data values/fields you choose to model, these can be transformed (x^2, y^2, etc)
- **Feature Engineering**: The process of building a set of feature combinations to act on inputs
- **Precision**: The positive predictive value how many times it correctly predicted a thing as its classification (eg cat)
- **Recall**: The true positive rate, How many times a think is in the class (the actual number of cats)

# Common Facts/Terminologies for examination

### Clustering
It is unsupervised learning technique for identifying group of similar entities

### Normalization
It is a transform that scales numeric value to the range 0 to 1

### Bucketing
It is used to convert a feature bin to multiple binary features that is typically based on a value range.
Ex: A grade for marks 80 - 100, B grade 60 - 79 and so on

### Regularization
Limiting the information captured by model to prevent overfitting.

### Overfitting
- When the model performs great on the input data but poorly on the test data
- Sufficient complex models can lead to overfitting

### Underfitting
- When the model performs poorly on the input data but great on the test data. 
- Insufficiently complex models can lead to underfitting.

### High Variance
 - Small changes in a few features leads to large differences in the output.
 - Low variance is desired

### High Bias
- Occurs when relationships are missed.
- Low bias is desired

### Learning rate
- Increasing the learning rate = Fast learning (at the risk of possibly missing the absolute optimal solution)
- Decreasing the learning rate = Slow learning

### Difference between of Features and Labels
|Features|Labels|
|--|--|
|Attribute of an entity|Attribute that is predicted|
|Describe characteristics of an entity|Category of an entity|
|Acts as I/P variable|Acts as O/P|

### Example of Features and Labels
|Features|Labels|
|--|:-:|
|No. of rooms, no. of bedrooms, size of kitchen, zip code etc.|Selling Price|
|Petal length, petal widh, sepal length, sepal width|Flower Species|
|Amount, product purchased, time of day, location|Fraud/Not Fraud|
|Age, occupation, zip code, no. of years of education|Income|
