
# Source Code and Resources for the Paper ID 9222 - Journal IEEE Latin America Transactions 

This repository contains the source code, resource, dataset link and results from paper "**MACIEL J.M, SOUZA G.C, ZALEWSKI W., LEDESMA J.J.G., ANDO JUNIOR O. H. Optimizing Solar Irradiance Prediction: Feature Selection for All-Sky Image Processing Using a Hybrid Prediction Method (PAPER ID 9222). IEEE Latin America Transactions, 2024.** 

The source code is made available to encourage scientific reproducibility and to facilitate further research in solar irradiance prediction using all-sky images.

## Overview

In this repository, an Artificial Neural Network (ANN) is developed to predict the **Global Horizontal Irradiance (GHI)** using different sets of input features extracted from all-sky images. This ANN model is based on the Hybrid Prediction Method proposed in paper: [https://doi.org/10.1016/j.rser.2023.114185](https://doi.org/10.1016/j.rser.2023.114185). The main objective of this work is to evaluate the prediction accuracy of GHI based on different input feature sets, categorized as **Complete**, **Medium**, and **Reduced**. These features are generated using image processing techniques and then used as inputs for the ANN. The accuracy results between input sets are compared.

## Dataset

The original dataset with all-sky images from the **Folsom** dataset, can be accessed at: [https://doi.org/10.1063/1.5094494](https://doi.org/10.1063/1.5094494).

The dataset description with all input all-sky image features, used in this project,  can be accessed at: [https://doi.org/10.3390/data9100113](https://doi.org/10.3390/data9100113).

Please, if you use this code, part of it or the HPM dataset, cite these papers.

## All Sky Image Input Features

The input features for the ANN was selected based on **Pearson Correlation** analysis with GHI. The selected features are grouped into three sets:

### 1. Complete Set (9 Inputs) with pearson coefficient correlation:
- fitLuminanceCSI (pearson 0.97)
- clearSkyGhi (pearson 0.91)
- SunLuminance (pearson 0.84)
- cloudsSunAround (pearson -0.79)
- cloudsCoverage (pearson 0.76)
- cloudsMovement (pearson -0.70)
- sunLocated (pearson 0.56)
- whitePixelRatio (pearson 0.24)
- season (pearson 0.11)

### 2. Medium Set (6 Inputs):
- fitLuminanceCSI
- clearSkyGhi
- SunLuminance
- cloudsSunAround
- cloudsCoverage
- cloudsMovement

### 3. Reduced Set (3 Inputs):
- fitLuminanceCSI
- cloudsSunAround
- cloudsMovement

## Code Overview

The provided code implements the following steps:
1. **Data Preprocessing:** Converts timestamps, reorders columns, and processes input features based on the selected horizon.
2. **Model Training:** A Multi-Layer Perceptron (MLP) is trained using the different input feature sets (Complete, Medium, Reduced) across 3-folds for validation.
3. **Hyperparameter Optimization:** Hyperparameters are optimized using methods such as EarlyStopping and ModelCheckpoint.
4. **Model Evaluation:** The accuracy of the model is measured using metrics like MAE, RMSE, MAPE, and R² for each fold.
5. **Predictions:** The trained models are used to generate predictions, which are saved as `.xlsx` files for further analysis.

## Installation

To run this project, you will need the following dependencies:
- Python 3.x
- TensorFlow
- NumPy
- Pandas
- Matplotlib
- Scikit-learn

You can install the necessary packages using the following command:

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn
```

## Running the Code

1. Download the dataset described in [https://doi.org/10.17632/347p98c2rd.1](https://doi.org/10.3390/data9100113) 

2. Download and run the notebook (src-code-paper-id9222-ieeela.ipynb) to train the models and generate predictions.

3. The results, including the accuracy metrics and predictions, will be saved in the specified results directory.

## Authors

- Joylan Nunes Maciel, Gustavo Campoi de Souza, Willian Zalewski, Jorge Javier Gimenez Ledesma and Oswaldo Hideo Ando Junior

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

We thanks to the work and dataset provided by paper **[https://doi.org/10.1063/1.5094494](https://doi.org/10.1063/1.5094494)**
