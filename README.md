# Building Accurate Weather Prediction Models with Neural Networks

## Overview

This project demonstrates the use of a feedforward neural network to predict weather conditions based on various input features. Leveraging synthetic weather data from Kaggle, the model classifies weather into four categories: Rainy, Sunny, Cloudy, and Snowy.
## Dataset
This project used the following dataset:

https://www.kaggle.com/datasets/nikhil7280/weather-type-classification

### Dataset Description

The dataset consists of **13,200 observations** and includes the following features:

| Feature Name         | Type        | Description                                                                 |
|----------------------|-------------|-----------------------------------------------------------------------------|
| Temperature          | Numeric     | Temperature during the day in Celsius.                                     |
| Humidity             | Numeric     | Percentage of humidity recorded.                                           |
| Wind Speed           | Numeric     | Speed of wind in kilometers per hour.                                      |
| Precipitation        | Numeric     | Amount of rainfall.                                                        |
| Cloud Cover          | Categorical | Likelihood of precipitation (percentage).                                  |
| Atmospheric Pressure | Numeric     | Atmospheric pressure in hPa.                                               |
| UV Index             | Numeric     | UV index for the day.                                                      |
| Season               | Categorical | Season during which data was recorded.                                     |
| Visibility           | Numeric     | Visibility recorded during the day (kilometers).                           |
| Location             | Categorical | Type of location: Mountain, Coastal, or Inland.                            |
| Weather Type         | Categorical | Target variable: Rainy, Cloudy, Snowy, Sunny.                              |

---

## Preprocessing Steps

### Addressing Data Issues
1. **Outlier Removal**:
   - Unusually high temperatures (e.g., 109°C) and other feature outliers (e.g., Wind Speed, Atmospheric Pressure) were removed.
   - Impossible UV Index values (<1 or >11) were deleted.
   - Humidity and Precipitation values >100% were corrected.

2. **Categorical Feature Cleanup**:
   - Removed trivial categories (e.g., Cloud Cover with only 18 observations of "Cloudy").

3. **Label Encoding**:
   - Used `LabelEncoder` from `scikit-learn` for encoding categorical variables.

| Feature Name  | Encoded Values                |
|---------------|-------------------------------|
| Cloud Cover   | Clear: 0, Overcast: 1, Partly Cloudy: 2 |
| Season        | Autumn: 0, Spring: 1, Summer: 2, Winter: 3 |
| Location      | Coastal: 0, Inland: 1, Mountain: 2 |
| Weather       | Cloudy: 0, Rainy: 1, Snowy: 2, Sunny: 3 |

---

## Model Architecture

### Initial Setup
- Split data into **70% training** and **30% testing** sets.
- Configured a **feedforward neural network** using TensorFlow/Keras:
  - One hidden layer with **20 neurons**.
  - Optimizer: **Adam**.
  - Initial accuracy: **95%** on training and testing data.

### Enhanced Model
- Standardized data using `StandardScaler`, improving accuracy:
  - Training: **98%**
  - Testing: **97%**

- Expanded network architecture:
  - Three hidden layers:
    - Layer 1: **256 neurons**
    - Layer 2: **128 neurons**
    - Layer 3: **64 neurons**
  - Accuracy after enhancements:
    - Training: **99%**
    - Testing: **98%**

---


## Results

The neural network demonstrated **strong accuracy** and generalization capabilities. 

### Future Enhancements
1. Integrate advanced architectures like **Convolutional Neural Networks (CNNs)** for spatial pattern recognition.
2. Deploy the model in production for real-time weather forecasting.

---



## Installation

To run this project locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/weather-prediction-neural-network.git
   cd weather-prediction-neural-network
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the script:
   ```bash
   python main.py
   ```

---
## Acknowledgements

- Dataset sourced from [Kaggle](https://www.kaggle.com/).
- Developed using **Python**, **TensorFlow**, and **scikit-learn**.

---
