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

## Pre-Trained Model

### Natural Language API
- Types of analysis that can be done here - 
	- **Entity analysis:** Identify entities within documents receipts, invoices, and contracts and label them by types such as date, person, contact information, organization, location, events, products, and media.
	- **Sentiment analysis:** Understand the overall opinion, feeling, or attitude sentiment expressed in a block of text.

## AutoML
- Designed for model builders with limited ML experience
- GUI for training, evaluating and tuning
- Services for sight, language and structured data
- AutoML tables uses structured data to build rgeression and classification models

# Deployment

## AI Platform
- Serverless GCP option
- Used to train and deploy ML models

## Cloud DataProc
- Spark includes MLlib
- Supports : 
	- Basic stastics
	- Classification
	- Regression
	- Clustering
	- Dimension Reduction
	- Collaborative Filtering

## Self-managed Deployements
### Compute Engine
- Deploy model to VM as a service
- [GPU and TPU](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/tree/main/study_material/others/definitions) available
### Kubernetes Engine
- Deploy model withing a container
- Cloud run alternative for container
- [GPU and TPU](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/tree/main/study_material/others/definitions) available
