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

### COuntry Total Energy Consumption
![image](https://user-images.githubusercontent.com/97785087/171768867-a9996eae-df75-4a2c-bbf8-e4313bbbfe7c.png)

![image](https://user-images.githubusercontent.com/97785087/171768878-b480e9b7-81cb-4ba8-884a-26b41062757e.png)

