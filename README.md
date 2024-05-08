# DeepMicro Replication Project

This repository contains the code and resources for replicating the DeepMicro research paper, "DeepMicro: Deep Representation Learning for Disease Prediction based on Microbiome Data" by Oh and Zhang (2020). The project was completed as part of the Deep Learning in Healthcare course by Joaquin Ugarte, Prasad Gole, and Ehit Agarwal.

## Team Members

- Joaquin Ugarte (jugarte2@illinois.edu)
- Prasad Gole (gole2@illinois.edu)
- Ehit Agarwal (ehitda2@illinois.edu)

## Project Overview

DeepMicro is a deep representation learning framework that exploits various autoencoders to learn robust low-dimensional representations from high-dimensional microbiome data and trains classification models based on the learned representations. The original study demonstrated that DeepMicro outperformed current best approaches in five out of six datasets.

The goal of this project was to replicate the DeepMicro study and test its hypotheses:
1. Training classifiers using a lower dimensional representation will result in more accurate predictions.
2. Training classifiers using a lower dimensional representation will speed up the model training and hyperparameter tuning process.

## Repository Structure

- `data/`: Contains the preprocessed microbiome datasets used in the project.
- `models/`: Contains the implementation of the autoencoder and classifier models.
- `results/`: Contains the results of the experiments, including model performance metrics and visualizations.
- `notebook/`: Contains Jupyter notebooks used for data exploration, preprocessing, and analysis.
- `requirements.txt`: Lists the required Python packages and their versions.
- `README.md`: Provides an overview of the project and instructions for running the code.

## Getting Started

1. Clone the repository:
```
git clone https://github.com/Prasad-py/DLH_Project
cd deepmicro-replication
```

2. Install the required packages:
```
pip install -r requirements.txt
```

3. Set the Parameters and Dataset number you wish to Train in the second cell of DL4H_Team_43.ipynb notebook:

4. Run the Notebook - DL4H_Team_43.ipynb

## Results and Discussion

Our replication study found that classifiers trained on the original data consistently performed better than those trained on encoded representations, which is different from the findings of the original DeepMicro paper. However, we did find that classifiers trained faster on the learned representations, supporting the second hypothesis.

Possible explanations for the discrepancy in results include differences in the implementation (PyTorch vs. Keras/TensorFlow) and the need for better tuning of training hyperparameters. Future work will focus on implementing missing models, conducting a proper hyperparameter search, and adding new datasets from recent studies.

## References

Oh, Min, and Liqing Zhang. "DeepMicro: deep representation learning for disease prediction based on microbiome data." Scientific Reports 10.1 (2020): 1-9. https://doi.org/10.1038/s41598-020-63159-5.
