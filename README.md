# EMIRNN
Faster Recurrent Networks for sensor data patterns 
This repository contains code base for experimenting sensor signal datasets for classification problems with RNNs

The study compares Standard or Baseline RNN models(LSTM & GRU) vs EMI RNN models (EMI-LSTM & EMI GRU)
This study also implements a set new architectures of RNN models called the FastGRNN and FastRNNs.

# Requirements: 
We require the EdgeML repository from link : https://github.com/microsoft/EdgeML to be cloned in order to access the EMIRNN models.
This needs to be downloaded and dependancies are installed from the requirements.txt file in this repository.

We experiment with Daphnet Dataset from UCI Machine Learning dataset collections. This dataset is about classifying gait modes of Parkinson's disease patients based on body worn accelerometer signals. 
It is assumed that the dataset folder is downloaded from the link :https://archive.ics.uci.edu/ml/datasets/Daphnet+Freezing+of+Gait

# File description:
DataPreprocessing.ipynb :The continuously logged and labelled accelerometer data from the patients is concatenated to a single dataframe. The unnecessary labels "debriefing-0" is removed and "Pre-FOG" label is concatenated. The continuous data is split into windows of 1,2,3,4 sec lengths and framed as dataframes with 3 labelled classes.  
 
trained baseline rnn models are saved as .h5 files  

00_baseline_LSTM&GRU_example.ipynb contains python script for training the model and load & testing it in runtime.
0x_emi_xxxx_example.ipynb files contains the script for training the model for that xxxx RNN model
0x_emi_xxxx_initialization_and_restoring.ipynb files contains the script for  loading and testing  that xxxx RNN model

Note: Files named as 1) 0x_emi_xxxx_example.ipynb and  2) 0x_emi_xxxx_initialization_and_restoring.ipynb are to be moved to 
..\EdgeML\tf\examples\EMI-RNN  in order to execute without dependancy issues.

Models will be stored in a folder once the training process in 1) is done. Can be restored and tested with 2)

During testing the inference times between baselines and EMI Rnns can be noted for faster on device computation. The model size of EMI RNNs are also smaller and Raspberry Pi compatible.
