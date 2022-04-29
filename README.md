# Early-Stage-Diabetes-Risk-Prediction-Classifier
We have a tabular dataset consisting mostly of binary data, the sole exception to this being the age field. We're attempting to create a machine learning model that can perform classification based on the data in this dataset. Being able to accurately predict whether or not a person has diabetes given whether or not they're positive for a range of symptoms could be of immense usefulness and importance in any medical system. An obvious example would be automated screenings through surveys that patients can fill out to get early predictions. Another example would be adding a similar model to an already existing medical database and notifying the people registered on that database of potential unknown conditions they might have.

# Method
In order to accomplish accurate classification easily and quickly, we've opted for the FastAI library as it has excellent support for tabular data and makes cutting edge mdoels and techniques readily available.
We use 20% of the dataset for validation, and the seed has been set to 123 to ensure that the dataset is split in the same way each time the code is run, to ensure repeatability.
We've set it to normalize any continuous data (the age), fill any missing fields and to categorify our variables (positive, negative, male, female, etc).
We've identified which columns are discrete and which are continuous too.

# batch size
*The* batch size is set to 256. After experimentation we found that this batch size provided good accuracy after 50 epochs or so. Decreasing the batch size leads to faster training and overfitting, but also gives over all lower accuracy.

# Experiment
A FastAI tabular learner object is instantiated. By default tabular learners have 2 hidden layers with 200 and 100 activations respectively, this was changed to 10,000 and 500 activations respectively as that gave on average 1-2% better accuracy. Adding more hidden layers did not seem to provide any significant advantages.
