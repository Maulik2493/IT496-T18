# IT496: Introduction to Data Mining (IDM)
# Course Project - 1

Project on Metro Train Dataset (Dataset-4)

### DOPE-a-MINE (Team-18)
* Maulik Thakkar (202101415)
* Maharshi Pipaliya (202101210)
* Sameer Sonara (202101489)
* Harshil Patel (202101019)
* Kunj Kapadiya (202103018)

### Abstract :
Urban metro systems are the arteries of modern cities, facilitating the rapid movement of commuters and goods. Ensuring the reliability and efficiency of these systems is very important.
Our core objective is to develop predictive models that accurately forecast the target parameter based on historical data and the interrelationships among these features. By achieving this, we can anticipate parameter fluctuations and performance variations. Such predictive insights empower decision-makers to optimize maintenance schedules, enhance efficiency, and minimize downtime.

### Dataset Description :
This Dataset contains readings from pressure, temperature, motor current, and air intake valves collected from a compressor's Air Production Unit (APU) from a metro train. It consists of 15169480 data points collected at 1Hz from February to August 2020 and is described by 15 features from 7 analog (1-7) and 8 digital (8-15) sensors:
1. **TP2 (bar)** - Pressure on the compressor.
1. **TP3 (bar)** - Pressure generated at the pneumatic panel.
1. **H1 (bar)** - Pressure generated due to pressure drop when the discharge of the cyclonic separator filter occurs.
1. **DV pressure (bar)** - Pressure drop generated when the towers discharge air dryers; a zero reading indicates that the compressor is operating under load.
1. **Reservoirs (bar)** - Downstream pressure of the reservoirs, which should be close to the pneumatic panel pressure (TP3).
1. **Oil Temperature (ºC)** - Oil temperature on the compressor.
1. **Motor Current (A)** - Current of one phase of the three-phase motor; it presents values close to 0A - when it turns off, 4A - when working offloaded, 7A - when working under load, and 9A - when it starts working.
1. **COMP** - The electrical signal of the air intake valve on the compressor; it is active when there is no air intake, indicating that the compressor is either turned off or operating in an offloaded state.
1. **DV electric** - The electrical signal that controls the compressor outlet valve; it is active when the compressor is functioning under load and inactive when the compressor is either off or operating in an offloaded state.
1. **TOWERS** - The electrical signal that defines the tower responsible for drying the air and the tower responsible for draining the humidity removed from the air; when not active, it indicates that tower one is functioning; when active, it indicates that tower two is in operation.
1. **MPG** - The electrical signal responsible for starting the compressor under load by activating the intake valve when the pressure in the air production unit (APU) falls below 8.2 bar; it activates the COMP sensor, which assumes the same behavior as the MPG sensor.
1. **LPS** - The electrical signal that detects and activates when the pressure drops below 7 bars.
1. **Pressure Switch** - The electrical signal that detects the discharge in the air-drying towers.
1. **Oil Level** - The electrical signal detects the oil level on the compressor; it is active when the oil is below the expected values.
1. **Caudal Impulse** - The electrical signal that counts the pulse outputs generated by the absolute amount of air flowing from the APU to the reservoirs.

### Algorithms Used :

- For data pre-processing, we used pandas and numpy libraries.
- For Exploratory Data Analysis, we used matplotlib and seaborn libraries. Also, we used box plots, pair plots, scatter plots, and heat maps to identify the correlation between the data of different sensors.
- Though the dataset contained outliers, we used IQR robust scaling.
- For hyperparameter tuning, we used GridSearch.
- For regression analysis, we used LinearRegression, RandomForestRegressor, and XGBRegressor algorithms.

### Problems Identified and Results :

1) **To determine the value of TP2 (pressure on compressor) with the help of different readings of analog sensors**

* Note : here R^2 means coefficient of determination.

- Linear Regression : R^2 = 0.945 , MSE = 0.755 , MAE =0.394.
- RandomForest Regressor : R^2 = 0.998 , MSE = 0.136 , MAE =0.0338.
- XGBRegressor  : R^2 = 0.997 , MSE = 0.161 , MAE =0.033.

2) **To determine the value of Oil temperature of compressor with the help of different readings of analog sensors**

- Linear Regression : R^2 = 0.38 , MSE = 5.10 , MAE =3.96.
- RandomForest Regressor : R^2 = 0.66 , MSE = 3.75 , MAE =2.69.
- XGBRegressor  : R^2 = 0.67 , MSE = 3.67 , MAE =2.63.


3) **To determine the value of DV_pressure with the help of different readings of analog sensors**

- Linear Regression : R^2 = 0.18 , MSE = 0.34 , MAE =0.12.
- RandomForest Regressor : R^2 = 0.82 , MSE = 0.15, MAE =0.03.
- XGBRegressor  : R^2 = 0.78 , MSE = 0.17 , MAE =0.03.


4) **To determine the value of Motor_Current with the help of different readings of analog sensors**

- Linear Regression : R^2 = 0.72 , MSE = 1.2 , MAE =0.97.
- RandomForest Regressor : R^2 = 0.906 , MSE = 0.70, MAE =0.28.
- XGBRegressor  : R^2 = 0.907 , MSE = 0.69 , MAE =0.28.

### References :

- Terminologies and understanding of the dataset : [nature.com](https://www.nature.com/articles/s41597-022-01877-3), [kaggle.com](https://www.kaggle.com/datasets/anshtanwar/metro-train-dataset)
- EDA : [analyticsvidhya.com](https://www.analyticsvidhya.com/blog/2022/07/step-by-step-exploratory-data-analysis-eda-using-python)
- Regression Analysis : [Lab 2 (House Rent Prediction)](https://colab.research.google.com/drive/15agvlFnfyNJ-47GcAqFhSJeeUVMfUh5F)

### Acknowledgements :

We would like to express our sincere gratitude and appreciation to the [Prof. Arpit Rana](https://www.daiict.ac.in/faculty-details/3407) for his invaluable support and contributions to this project, and that to Vipasha Vaghela, Himanshu Beniwal, Aksh Patel, Parth Thakrar, Aditya Nawal, and Priyanshi Parmar.


