# NCSU-Terrain-Prediction-for-Lower-Limb-Prostheses

Here is a brief description of the data:

  - "_x" files contain the xyz accelerometers and xyz gyroscope measurements from the lower limb.
  - "_x_time" files contain the time stamps for the accelerometer and gyroscope measurements. The units are in seconds and the sampling rate is 40 Hz.
  - "_y" files contain the labels. (0) indicates standing or walking in solid ground, (1) indicates going down the stairs, (2) indicates going up the stairs, and (3) indicates walking on grass.
  - "_y_time" files contain the time stamps for the labels. The units are in seconds and the sampling rates is 10 Hz.

model_development.ipynb

  - Data Loading: Fetching data for model training
  - Data Prepocessing: Merging spatial data with label data by using Upsampling
  - Data Preparation: Reshaping the spatial data into windows of size 60 samples to be used for training with the neural network
  - Analyzing Data Imbalance: Interpretting the distribution of different terrain classes throughout the train data
  - Training the Model: Using CNN + LSTM model in conjuction with class weights for imbalance to traing the model
  - Cross Validation: Performing cross validation with a subject leave out logic to imporve robustness of the model
  - Model Inference: Generating predcitions for the Test Data using the trained model
