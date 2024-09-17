# Autoencoder for Anomaly Detection in Network Traffic (HTTP Service)

This project implements an autoencoder model for detecting anomalies in network traffic using the KDD Cup 1999 dataset, specifically focusing on HTTP service. The model is trained to learn the normal patterns in network traffic, and deviations from these patterns are classified as anomalies.

## Dataset
The dataset used for this project is the **KDD Cup 1999** dataset. It contains various features related to network connections and labels indicating normal or attack instances.

- **Training Data**: `kddcup.data_10_percent_corrected`
- **Test Data**: `corrected`

### Features:
- We filtered the data to only include HTTP service.
- Removed the `service` column after filtering, as it only contains HTTP service records.

## Data Preprocessing
1. **Label Encoding**: 
   - Categorical columns are label-encoded, including the `label` column, to convert them into numerical values.
   
2. **Standardization**:
   - Feature values are standardized using `StandardScaler` to normalize them before feeding into the model.

## Autoencoder Architecture
The autoencoder is a neural network designed to reconstruct its input. The model is composed of:
- **Input Layer**: The dimensionality of the input features.
- **Hidden Layer**: A dense layer with `relu` activation and dropout to prevent overfitting.
- **Output Layer**: A dense layer with `sigmoid` activation to reconstruct the original input.
