# CS598 Deep Learning For Healthcare Group Project

# Reproduction of DeepMicro


This repository contains the code and resources for replicating the DeepMicro research paper, "DeepMicro: Deep Representation Learning for Disease Prediction based on Microbiome Data" by Oh and Zhang (2020). The project was completed as part of the Deep Learning in Healthcare course by Joaquin Ugarte, Prasad Gole, and Ehit Agarwal.

## Team Members

- Joaquin Ugarte (jugarte2@illinois.edu)
- Prasad Gole (gole2@illinois.edu)
- Ehit Agarwal (ehitda2@illinois.edu)

## Project Overview

DeepMicro is a deep representation learning framework that employs various autoencoders to learn robust low-dimensional representations from high-dimensional microbiome data and trains classification models based on the learned representations. The original study demonstrated that DeepMicro outperformed the current best approaches in five out of six datasets.

The goal of this project is to replicate the DeepMicro study and test its hypotheses:
1. Training classifiers using a lower dimensional representation will result in more accurate predictions.
2. Training classifiers using a lower dimensional representation will speed up the model training and hyperparameter tuning process.

## Repository Structure

- `data/`: Contains the preprocessed microbiome datasets used in the project.
- `results/`: Contains the results of the experiments, including trained models and visualizations.
- `DLH_Team_43.ipynb`: A Jupyter notebook that reproduces the DeepMicro project.
- `en_dict`: A pickled Python dictionary to store information of trained autoencoders.
- `clf_dict`: A pickled Python dictionary to store information of trained classifiers.
- `requirements.txt`: Lists the required Python packages and their versions.
- `README.md`: Provides an overview of the project and instructions for running the code.

## Getting Started

1. Clone the repository:
```
git clone https://github.com/Prasad-py/DLH_Project
```
2. Install the required packages:
```
pip install -r requirements.txt
```
3. In the Jupyter notebook, under the 'Data' section, the cell labeled ‘Configure Parameters’ can be used for tuning certain parameters.
  - DATASET is the index of the datasets dictionary, which can be used to select the dataset.
  - ALL_HPS is set to False in order to train with a small subset of hyperparameters for the purpose of illustration. It can be set to TRUE in order to train with the entire set of hyperparameters.
  - RANDOM_SEED: Random seed used for python, numpy and torch.
  - TEST_SIZE: Size of the test set.
  - NUM_FOLDS: Number of folds for cross-validation.
  - BATCH_SIZE: Batch size of the data loaders.
4. The cell under the 'Hyperparameters' section contains HYP_PARAMS, AES and CLFS, which can be configured to select specific hyperparameters, autoencoder or classifier models, respectively.
5. Run all the cells in order to run the entire DeepMicro pipeline.
6. A custom en_dict file, along with the corresponding autoencoder models saved in the results folder, can be used to begin execution from the get_best_aes() method.
7. Alternatively, a custom min_en_loss dictionary can be passed to the train_clf() method, in order to use specific autoencoder models saved in the results folder.
8. The best classifiers for a custom clf_dict file can also be computed by running the cells in the 'Results' section.
## Results and Discussion

Our replication study found that classifiers trained on the original data consistently performed better than those trained on encoded representations, which is different from the findings of the original DeepMicro paper. However, we did find that classifiers trained faster on the learned representations, supporting the second hypothesis.

Possible explanations for the discrepancy in results include differences in the implementation (PyTorch vs. Keras/TensorFlow) and the need for better tuning of training hyperparameters. The DeepMicro study compares its models to the MetAML study. It is likely that differences in the models developed by the two studies resulted in a discrepancy, which was interpreted as the encoded models being superior to the default models. Future work will focus on adding new datasets from recent studies, augmenting the current data sets with generative models and developing techniques to find the optimal training parameters for each combination of model type and dataset.

## Project Video

https://drive.google.com/drive/u/2/folders/1sulQR6U7-jwWe9gUHLjr473GJ04IxXl8

## References

Oh, Min, and Liqing Zhang. "DeepMicro: deep representation learning for disease prediction based on microbiome data." Scientific Reports 10.1 (2020): 1-9. https://doi.org/10.1038/s41598-020-63159-5.
