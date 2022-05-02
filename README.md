# Detecting Onsets Using EEG Signals
Project for 11-785 Introduction to Deep Learning.

This is the Github Repo for the 11785 IDL Course Project.

## Abstract
In this project, we are addressing the issue of how to predict the onsets in music using physiological data obtained from participants listening to the music. We solve the problem using Deep Learning technologies such as Recurrent Neural Networks and Long Short Term Memory models to extract onsets in music using EEGs. We consider a window of one second of EEG obtained from participants during music listening sessions using the NMED dataset. The dataset consisted of 10 songs and concurrently recorded EEG from 20 users. We improved upon the existing baseline using the concept of context which considers the previous and future locations of onsets to correctly detect a current onset, obtaining a AUC score of 0.74, precision of 0.55, recall value of 0.925 and f1 score of 0.67. The results illustrate the feasibility of building a deep learning network to identify onsets of acoustic events in music and provide a basis for future work.

## Data
We use the NMED-T dataset, a collection of EEG signals of 20 users as they listened to 10 songs. The dataset is pre-processed to some extent, with basic artifact removal and filtering. We restructure the dataset from a per song basis to a per user basis, i.e. each file contains one user's eeg signal data for all songs.

The songs are collected in a wav format. There are no ground truths for out tasks so we generate the true labels based on the baseline paper using python's madmom library's RNN Onset detection function. These are converted into one-hot labels for training and timestamps for evaluation

## Baseline MLP and RNN
A standard MLP with our custom Dataloader which trains on 19 users and validates on 1 user's signals. Simply running the cells should give you the result
