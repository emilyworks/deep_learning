Overview:
The purpose of this analysis was to create a model that could accurately predict whether a grant application would be successful 75% of the time.
Results:
Data Preprocessing
The target variable was “IS_SUCCESSFUL” – i.e., the column that indicates whether the grant request was successful or not
The features were the application type, application classification, use case, organization, status, income amount, special considerations, and ask amount
The name and EIN of the applications were dropped and not considered either inputs or outputs
Compiling, Training, and Evaluating the Model
I originally used two neuron layers, each with 25 neurons, and each using RELU activation functions (the output layer leveraged a sigmoid activation function). 
To increase accuracy and successfully reach the 75% accuracy benchmark, I began to increase the number of layers and neurons, the number of epochs, different activation functions (e.g., testing tanh, and not just relu for the hidden layers). I also removed high-flying outliers (ask amounts above $150,000) among the grant ask amounts while being mindful of the need to not remove too much data as to undercut the purpose of creating a model in the first place

In the process of doing so, I successfully reached the 75% accuracy benchmark. The hyperparameters I settled on via KerasTuner included using the tanh activation function, with 7 neuron layers, and various combinations of the number of neuron units.

Summary: 
Overall, the deep learning model successfully learned how to predict whether grant applications would be successful based on a handful of features with 75% accuracy. However, to reach that 75% mark, I found it necessary to remove outliers/data points (e.g. grants requesting over 150k up to 8 billion dollars). Even with other fine tuning, it is plausible the model may be unable to reach that 75% accuracy benchmark if it sees similar “outlier” situations in real life. In that sense, its success is conditional.
An alternative supervised learning model may be able to tackle this kind of classification problem as well. Clustering, logistic regression, etc. approaches may be useful to experiment with to see if they can yield higher levels of accuracy and handle any outlying data more smoothly. A random forest approach may be particularly promising given that it is somewhat insensitive to outlying data.

