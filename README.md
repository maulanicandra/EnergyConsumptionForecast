# EnergyConsumptionForecast
Energy Consumption Forecast towards Net Zero Transition

Quoting from Mc-Kinsey, “We’re in the midst of an energy transition that continues to evolve.”
With the increase in global temperature and climate change, an international program, namely Net Zero Emission, was established. Net Zero 2050 is an ambitious scenario that limits global warming to 1.5 °C through stringent climate policies and innovation, reaching net-zero CO₂ emissions around 2050. One strategy in energy use is to shift the use of energy from fossil energy sources to renewable energy (renewable energy) so that the Energy Mix target emerges, namely by targeting the composition of renewable energy, namely 32% in 2035 and 50% in 2050. This project mainly provides insights into the longer-term trends that will continue to be essential in shaping future energy systems.

![image](https://user-images.githubusercontent.com/97785087/171768216-f4d64550-fee7-40bb-a537-ba31f1dc7cf0.png)
![image](https://user-images.githubusercontent.com/97785087/171768224-2d7e0be6-cf9f-405f-9b45-d7f9e32d660a.png)
As shown in figure above, world energy consumption is increasing. It can be seen that most of the growth in global energy consumption was positive, except in 1980 due to the global recession, 2009 due to the global economic crisis, and 2020 due to COVID-19.

![image](https://user-images.githubusercontent.com/97785087/171768296-5ef92359-aeca-406e-95b6-82f11af4b9ec.png)
Based on the energy consumption data in 2020, renewable energy composition is only 14%, with the highest composition being hydro, wind, diesel, biofuels, and biomass.

The primary purpose of this analysis is to predict whether the energy mix composition from renewable energy will reach 32% in 2035 and 50% in 2050. Based on my purpose, I choose regression and time series machine learning to predict world energy consumption and renewable energy consumption in the future. Data-driven recommendations will be delivered at the end of the study.

## About Dataset
Dataset can be found at https://ourworldindata.org/grapher/primary-sub-energy-source. This dataset outlines the number of terawatt-hours (TWh) consumed from 1965 to 2020 through various energy sources. Energy consumption by source datasets provides context about the quantity of energy required, how it changes over time, and how we are transitioning from non-renewable to renewable energy use.

## Exploratory Data Analysis
### Total Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171768566-915ad9bd-124d-4778-882a-ce4e815019b8.png)
Most energy sources used are fossil energy, namely oil, coal, and gas. However, it can also be seen that renewable energy consumption is increasing every year. Meanwhile, from the correlation data, new renewable energy sources are correlated. In contrast, renewable energy sources developed longer, such as nuclear and hydro, are still correlated with non-renewable energy.

![image](https://user-images.githubusercontent.com/97785087/171768608-9017da2b-47d1-4913-8749-25dbbd5bc5e4.png)

Observation:
1.	 Wind energy is highly correlated with solar, biofuels, and biomass
2.	 Hydro is highly correlated with gas, oil, coal, and nuclear.
3.	 Solar energy is highly correlated with the wind.
4.	 Nuclear is highly correlated with gas, oil, biomass, and wind.
5.	 Biofuel is highly correlated with biomass and wind.
6.	 Biomass is highly correlated with gas, oil, biofuels, nuclear, and wind.
7.	 Coal is highly correlated with gas, oil, and hydro.
8.	 Oil is highly correlated with gas, coal, biomass, nuclear, and hydro.
9.	 Gas is highly correlated with oil, coal, biomass, biofuels, nuclear, and hydro.

### Organizational Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171768730-72eb14a8-c203-4065-92c4-32381d939213.png)

Initially, most energy uses was by OECD countries (countries in Europe and the US). Still, since 2008 the value has been followed by Non-OECD with the development of industry and shifting manufacturing in Non-OECD countries, especially the Asia Pacific.

![image](https://user-images.githubusercontent.com/97785087/171768747-1d981cbd-fa12-452e-8884-11a5dadd75ce.png)

Meanwhile, the use of renewable energy is still being led by OECD countries because a lot of research is being carried out in that country.

### Continent Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171768796-5bd44a53-a57f-4b01-9f6c-2c0acd872378.png)

![image](https://user-images.githubusercontent.com/97785087/171768807-769d0bf7-fc7b-49b1-9426-f48dfed241d4.png)

As for the energy consumption of each continent, the highest in the Asia Pacific, this is due to the shifting of the manufacturing area to Asia. Meanwhile, renewable energy is also the most abundant in the Asia Pacific because there is significant growth in China and many other countries with ambitious projects and energy councils.

### Country Total Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171768867-a9996eae-df75-4a2c-bbf8-e4313bbbfe7c.png)
![image](https://user-images.githubusercontent.com/97785087/171768878-b480e9b7-81cb-4ba8-884a-26b41062757e.png)

China has the highest energy consumption, followed by the US. The US rate is fixed because industrialization is already saturated. When viewed from the rank of 20 countries, it can be seen that the 18 countries with the highest energy consumption are G20 countries, so energy consumption is influenced by GDP.

![image](https://user-images.githubusercontent.com/97785087/171768974-e1048e68-0bb6-42fd-bf60-e52ec6b7973f.png)
![image](https://user-images.githubusercontent.com/97785087/171768986-ed487f02-8006-4a6c-b3ae-86577c10e6a0.png)

As for renewable energy, the highest is in China and followed by the United States. The amount of renewable energy is influenced by state policy and R&D, as well as global pressure.

## Modeling
### Simple Liniar Regression
Simple linear regression modeling has been conducted to obtain the coefficient and intercept. Simple linear regression is used as the baseline for selecting the forecast model in this study. MAE, MAPE, and RMSE parameters are used to check the error of the predicted value against the actual value. The values of MAE and RMSE are similar, so there are no anomaly errors, and the model can represent the data.

![image](https://user-images.githubusercontent.com/97785087/171769046-6daf8600-94ea-4942-a50b-7dd2076f2808.png)

### Ridge and Lasso Regression
Ridge and lasso regression was also performed on the data. Hyperparameter tuning is done to get the best alpha for ridge and lasso regression. The following are the results of the ridge and lasso regression and the values for MAE, MAPE, and RMSE.
![image](https://user-images.githubusercontent.com/97785087/171769208-05a75364-26d5-48e1-82d3-fc8199c867fc.png)

![image](https://user-images.githubusercontent.com/97785087/171769219-afe500ce-db84-450b-bc71-0411af422597.png)

### Time Series Forecasting for World Energy Consumption
Then, I conduct time series forecasting because the parameter that affects energy consumption is time. Time-series forecasting models can predict future values based on previous values. Time series can be divided into several parts, namely:
- Trend: increase or decrease in the value of the data. 
- Seasonality: repetitive pattern seen in the data series.
- Residue is the residual value of the data after extracting trend and seasonality.

![image](https://user-images.githubusercontent.com/97785087/171769280-8509a935-b1aa-45da-8fb0-2cd1c4cb2696.png)

The figure above shows that data has a trend and no seasonality.
Then a stationarity check is carried out to determine which time series analysis can be applied to our data. After the transformation using shift and log transformation, the transformed data is evaluated using Augmented Dickey-Fuller (ADF). The data is stationary. The augmented Dickey-Fuller Stationarity Test (ADF) is a test performed on time-series data to determine whether the time series data is stationary or not.

Some time-series analyses require that the data be stationary before further analysis, such as data analysis using ARIMA. Therefore, a stationarity test needs to be carried out to fulfil these requirements.

![image](https://user-images.githubusercontent.com/97785087/171769315-c914fd1b-57cd-4c17-8a70-d601b965db2a.png)

The figure above shows that data is stationary.
I tried to apply simple exponential smoothing, holt exponential smoothing, and ARIMA (Auto-Regressive Integrated Moving Average) in this study.

### Simple Exponential Smoothing and Holt Exponential Smoothing (World Energy Consumption)

![image](https://user-images.githubusercontent.com/97785087/171769367-247d32b1-3662-4380-a837-bb49deb33cbb.png)

The figure above shows that the values of MAE, MAPE, and RMSE, which tend to be larger because of their simple exponential characteristics, are suitable for data that does not have a trend but has seasonality. Meanwhile, in Holt's Exponential Smoothing, it can be seen that MAE, MAPE, and RMSE tend to be small because the data has a trend and does not have seasonality.

### ARIMA Time Series (World Energy Consumption)
Next, the ARIMA time series (Auto-Regressive Integrated Moving Average) is applied to the data. There are three variables in ARIMA, namely Auto-Regressive (p), Integrated (d), and Moving Average (q). The ARIMA variable value was calculated using the auto arima function. 

![image](https://user-images.githubusercontent.com/97785087/171769466-ec8145b8-cec3-4423-b297-68ccb7573536.png)

![image](https://user-images.githubusercontent.com/97785087/171769473-58069b0a-c9f9-4953-8489-303cddb5665a.png)

![image](https://user-images.githubusercontent.com/97785087/171769483-2730a7a8-5155-4be6-8f46-3ad2c7c109cc.png)

![image](https://user-images.githubusercontent.com/97785087/171769495-7d3856a0-1f6f-4f74-b90d-313d33319cd3.png)

The result is that the MAE, MAPE, and RMSE values remain relatively large because ARIMA is more suitable for data that has trend and seasonality.

### Time Series Forecasting for Renewable Energy
Stationary check has been done to renewable energy data.
![image](https://user-images.githubusercontent.com/97785087/171769538-7360d3db-0511-44bc-a30d-3eae9565adc0.png)

The figure above shows that data has a trend and no seasonality.

![image](https://user-images.githubusercontent.com/97785087/171769558-a994522f-5456-4efd-8fd1-5e91e3226ba6.png)

After the transformation using twice shift transformation, the transformed data is evaluated using Augmented Dickey-Fuller (ADF). The data is stationary.

![image](https://user-images.githubusercontent.com/97785087/171769573-e3c74ed9-7b9c-46b2-beea-24919822e15a.png)

The figure above shows that the values of MAE, MAPE, and RMSE, which tend to be larger because of their simple exponential characteristics, are suitable for data that does not have a trend but has seasonality. Meanwhile, in Holt's Exponential Smoothing, it can be seen that MAE, MAPE, and RMSE tend to be small because the data has a trend and does not have seasonality.

### ARIMA Time Series (Renewable Energy Consumption)
The ARIMA variable value was calculated using the auto arima function.
![image](https://user-images.githubusercontent.com/97785087/171769611-9a742478-fdf3-4c11-9c9e-7913bb69595b.png)

![image](https://user-images.githubusercontent.com/97785087/171769624-f07544a2-42cd-4c41-adab-9a55a85b11ad.png)

![image](https://user-images.githubusercontent.com/97785087/171769632-c70dd389-b6fc-4677-a113-25166e10a9d5.png)

![image](https://user-images.githubusercontent.com/97785087/171769647-b87f4f9a-da39-4c04-a8a0-a96d5cdce20f.png)

The result is that the MAE, MAPE, and RMSE values remain relatively large because ARIMA is more suitable for data that has trend and seasonality.

## Model Evaluation
### World Energy COnsumption
![image](https://user-images.githubusercontent.com/97785087/171769706-0e74b95c-af04-4be3-a353-80bc053ec9f6.png)

### Renewable Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171769740-ea78199b-bfa6-448a-827d-860d9e60399a.png)

Model evaluation was carried out using MAE mape and RMSE values. R square is not used for evaluation to avoid bias because r square is very suitable for linear regression.
Holt exponential smoothing was chosen to forecast world energy consumption and renewable energy consumption because it has the smallest MAE, MAPE, and RMSE values.

## Forecast
![image](https://user-images.githubusercontent.com/97785087/171769773-8c8b526a-2aeb-45b7-92eb-8c0aa3653edf.png)
![image](https://user-images.githubusercontent.com/97785087/171769839-2d782591-2ae5-47b7-87ed-e060a271fa71.png)

Prediction results with current energy consumption, the projection of renewable energy on world energy consumption in 2035 is only 15.70% of the 35% target. Meanwhile, in 2050 it will only reach 17.14% of the target, which is 50%. So there needs to be a disruption in energy use in 2 ways, namely reducing consumption, namely by energy efficiency and adding a renewable energy mix.

## Follow-up Action
For the follow-up action, I added clustering so that the regional solutions and policies provided are in accordance with the nature of the consumption pattern of the renewable energy mix. So that the policy can provide a smooth transition and significant results. Here I use Kmeans without PCA because I want to see the overall pattern of energy use. Based on the elbow method, the cluster can be divided into 4 and 5 clusters.

![image](https://user-images.githubusercontent.com/97785087/171769955-a86de86e-1fd6-4966-91be-a34012867d09.png)

Based on my personal judgment, I chose to divide the cluster into 4 based on the country based on the characteristics of the countries in the cluster. The four clusters are Agricultural and Service Based Country, Fossil Fuel Producers, Emission Intensive Producer, and Emerging Energy Consumer Countries.
From this division, the policy regarding renewable energy should be prioritized from emission-intensive producers, fossil fuel producers, emerging energy consumer countries, to agricultural and service based countries. The priority of renewable energy can also be adjusted by the majority of renewable energy in the country to accelerate the rate of increase in renewable energy.

![image](https://user-images.githubusercontent.com/97785087/171769993-8d25a6ad-0af4-489a-8fb6-3abb617e09ab.png)

## Conclusion
The forecast results show that the Net Zero Energy Mix target failed to meet the target of only 15.70% from 35% in 2035 and only 17.14% of 50% in 2050 so efforts were needed to accelerate an increase in the increase in renewable energy.
## Recommendation
To accelerate the process of achieving the Net Zero Energy Mix target, a regional policy variation and effort is required according to the nature of the consumption of each country according to the results of the clustering.
## Future Research and Improvement
Forecasting needs to be done with more advanced methods such as fbprophet or LSTM to forecast Total Energy Consumption and Renewable Energy Consumption.

