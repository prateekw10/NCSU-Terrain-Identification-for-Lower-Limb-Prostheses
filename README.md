# NCSU-Terrain-Prediction-for-Lower-Limb-Prostheses

- The aim of the project is to be able to accurately identify the terrain based on the data streams from the inertial measurement unit (IMU) present on a lower limb prosthetic device.
- The dataset consists of IMU data from sensors attached to the lower limbs prostheses which consists of spatial data (xyz) from the accelerometer and the gyro sensor sampled at 40 Hz. The label data sampled at 10 Hz representing four classes of the terrain.
- Since the provided dataset has different sampling frequencies for the spatial data and labels, upsampling of feature data was done to match the timestamps of the label data.
- It was observed that there was significant imbalance between the terrain class distribution which was treated to promote generalization and reduce the chances of overfitting.
- Finally, a CNN and LSTM model is implemented to observe high validation accuracy and used to generate test data predictions.

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
