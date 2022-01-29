# Machine Learning
- Types
	- Supervised learning: 
		- Labels are provided. 
		- Types - 
			- Regression - Output predictions are continuous in nature. For ex, predicting out the price of a house which can lie in any range of numbers. Some regression ML algorithms are - 
				- Linear Regression: 
					- Random fact - Linear regression can be done on ordinary CPU's whereas Neural Networks(Feed Forward or Recurrent) require resource intensive machines(i.e GPU's) whereas 
				- Support Vector Regression(SVR)
				- Decision Tree Regressor
			- Classification - Output predictions are discrete in nature. For ex, sentiment analysis which can be positive or negative. Some classification algorithms are - 
				- Logistic Regression
				- Support Vector Machine(SVM)
				- Decision Tree Classification
	- Unsupervised learning: 
		- Labels are not provided. 
		- Find structure within the data
		- [Clustering](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/definitions/clustering.md) is unsupervised learning
```
GCP ML Solutions
├── Pre-Trained Model
│   ├── For generic use cases. Vision API, Speech API, Language API
│
├── AutoML
│   ├── Throw your data to GCP and rest GCP will take care
│
├── Custom Training
│   ├── Tensorflow, PyTorch, Scickit-learn
```

## Examples of Pre-Trained Model

### Natural Language API
- Types of analysis that can be done here - 
	- **Entity analysis:** Identify entities within documents receipts, invoices, and contracts and label them by types such as date, person, contact information, organization, location, events, products, and media.
	- **Sentiment analysis:** Understand the overall opinion, feeling, or attitude sentiment expressed in a block of text.

# Neural Networks and Deep Learning

## Feature engineering
To learn more about features, click [here](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/ai_ml_terminologies.md)
### Definition
Manipulation of features to improve the quality and predictive capabilities of machine learning models. This is known as feature engineering.
### Steps
- Identify useful features
- Features may be in original data but might need some transformations
- Features derived from other features.
### Ways to engineering features
- Transform the orginal features
	- Ex: Lower case words and remove punctuation
	- Map Numeric valriable to a scale of 0 to 1 if the different features are from different numeric range (**Normalization**)
- Bucketing
	- Create sub-groups of feature values
	- This reduces number of values
- Feature cross	
	- Cartesian product of two or more features
	- Helps when there are non-linear relationships
- Binary features
	- Ex: is_red, is_blue etc
- Decompose values to parts
	- Ex: From date extract year, month and day

## One-Hot Encoding
- Map from an attribute value to a single bit in a binary array
- Each postion in array represent a possible value
- Ex: Red represent 100, Blue represent 010 and Green represent 001. Here we mapped colors to three different binary arrays

