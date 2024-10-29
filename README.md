# Weather Forecasting Project in Tunisia

## General Framework of the Project

This project is part of the **"Career Preparation Project" (P2M)** at SUPCOM, completed by a team of two under the supervision of a professor. The goal of the project is to develop an intelligent model for **weather forecasting** and to display the results on Google Maps.

### Context

In the agricultural sector, weather plays a crucial role in planning agricultural tasks (e.g., irrigation, planting, harvesting). This project focuses on predicting the **daily maximum temperature** in Tunisia, a key factor in managing agricultural resources and outdoor activities. The maximum temperature is used because it directly impacts decisions such as irrigation and the management of heat periods.

### Problem Statement

Weather, particularly the **maximum temperature**, is a critical parameter in agriculture and other sectors such as energy management and public health. This project addresses the following question:
- **How to effectively predict the daily maximum temperature from historical meteorological data to improve decision-making?**

---

## Project Objective

The objective is to design several time series models to predict the **daily maximum temperature (T2M_MAX)**. The models used are:
- **ARIMA** (AutoRegressive Integrated Moving Average)
- **SARIMAX** (Seasonal ARIMA with eXogenous variables)
- **LSTM** (Long Short-Term Memory), a recurrent neural network model.

The performance of these models will be evaluated and compared to determine the most suitable one for this type of forecasting.

---

## Data Description

The data used in this project comes from meteorological measurements taken over a long period in Tunisia. Here are the main **features** included in the data:

| Feature        | Description                                                        |
| -------------- | ------------------------------------------------------------------ |
| **LAT**        | Latitude of the measurement station.                               |
| **LON**        | Longitude of the measurement station.                              |
| **YEAR**       | Year of the measurement.                                           |
| **MO**         | Month of the measurement.                                          |
| **DY**         | Day of the measurement.                                            |
| **PRECTOT**    | Total precipitation (in mm).                                       |
| **QV2M**       | Specific humidity at 2 meters above ground (g/kg).                 |
| **RH2M**       | Relative humidity at 2 meters above ground (%).                    |
| **PS**         | Atmospheric pressure at the surface level (kPa).                   |
| **T2M_RANGE**  | Temperature range at 2 meters (°C).                                |
| **T2M_MAX**    | Maximum temperature at 2 meters (°C) — target variable.            |
| **T2M_MIN**    | Minimum temperature at 2 meters (°C).                              |
| **WS50M**      | Average wind speed at 50 meters (m/s).                             |
| **WS10M**      | Average wind speed at 10 meters (m/s).                             |

The **maximum temperature (T2M_MAX)** is the primary variable for predictions. Other variables, such as **relative humidity (RH2M)** and **wind speed (WS50M)**, are used as exogenous variables in some models.

---

## Model Descriptions

### 1. ARIMA Model
The **ARIMA** model is a classical model used for time series prediction. It captures autoregressive relationships and linear trends from historical data.

#### Visualization:
![ARIMA Plot](./visualisations/arima_plot.png)

**Interpretation**: The ARIMA model captures the overall temperature trends, but it may lack precision when predicting rapid or seasonal changes.

---

### 2. SARIMAX Model
The **SARIMAX** model accounts for the **seasonality** of the data and includes **exogenous variables** like humidity and wind speed. It is particularly effective in capturing cyclical variations.

#### Visualization:
![SARIMAX Plot](./visualisations/sarimax_plot.png)

**Interpretation**: The SARIMAX model improves the predictions by incorporating seasonal cycles and exogenous variables. It better adapts to temperature peaks.

---

### 3. LSTM Model
The **LSTM** model is a recurrent neural network designed to handle long-term sequences. It captures complex temporal relationships and is particularly effective for non-linear time series forecasting.

#### Visualization:
![LSTM Plot](./visualisations/lstm_plot.png)

**Interpretation**: The LSTM model offers the best performance, capturing non-linear temperature variations effectively. It handles sudden changes and long-term trends more efficiently.

---

## Model Comparison

The three models were evaluated using the **Root Mean Squared Error (RMSE)** metric, which measures the average error between the predicted and actual values:

| Model    | RMSE (°C) |
| -------- | --------- |
| **ARIMA**  | 2.50      |
| **SARIMAX**| 2.30      |
| **LSTM**   | 1.90      |

### Conclusion

The **LSTM model** showed the best performance with an **RMSE of 1.90°C**, effectively capturing long-term fluctuations and complex variations. The **SARIMAX model** also performed well by incorporating seasonality and exogenous variables. The **ARIMA model** remains simpler but less suited to handle complex data.

---

## How to Run This Project

1. **Clone the GitHub repository**:
   ```bash
   git clone https://github.com/your-username/MonProjetMeteo.git

