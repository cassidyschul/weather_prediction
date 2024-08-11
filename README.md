# Weather Type Classification Model

Members: Abel Dumecha and Cassidy Schultheis

## Data Preprocessing
A weather type classification model was developed and optimized using data sourced from Kaggle (https://www.kaggle.com/datasets/nikhil7280/weather-type-classification).

The dataset includes various features such as Temperature (°C), Humidity (%), Wind Speed (km/h), Precipitation (%), Cloud Coverage, Atmospheric Pressure (hPa), UV Index, Season, Visibility (km), Geographical Location, and Weather Type.

For ease of access, the data was stored in an AWS S3 bucket and linked to a Google Colab notebook via a URL.

During preprocessing, categorical data was converted to numeric values using the get_dummies() function. The Weather Type was chosen as the target variable, with the remaining columns serving as features. Categorical variables were encoded using one-hot encoding, resulting in labels: 0 for ‘Cloudy’, 1 for ‘Rainy’, 2 for ‘Snowy’, and 3 for ‘Sunny’. The dataset was split into training (60%), validation (15%), and testing (25%) sets, and normalized using MinMaxScaler().

## Model Optimization
The model was then built, focusing on optimizing three key parameters: the number of units, the choice of optimizers, and the activation functions for hidden layers. The model's performance was assessed using loss and accuracy metrics on the training, validation, and testing datasets, along with confusion matrices and classification reports.

### Optimizers

Four different optimizers were used to determine which would be the best. The optimizers used were Adam, SDG, Adagrad, RMSProp. <br>

![Accuracy vs Epoch Per Optimizers Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Optimizer%20Training%20Data.png?raw=true)
![Accuracy vs Epoch Per Optimizer Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Optimizer%20Validation%20Data.png?raw=true)
![Loss vs Epoch Per Optimizer Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Optimizer%20Training%20Data.png?raw=true)
![Loss vs Epoch Per Optimizer Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Optimizer%20Validation%20Data.png?raw=true)

### Neurons


![Accuracy vs Epoch Per Neurons Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Neurons%20Training%20Data.png?raw=true)
![Accuracy vs Epoch Per Neurons Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Neurons%20Validation%20Data.png?raw=true)
![Loss vs Epoch Per Neurons Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Neurons%20Training%20Data.png?raw=true)
![Loss vs Epoch Per Neurons Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Neurons%20Validation%20Data.png?raw=true)

### Activation Function

Four different activation functions were used to determine which would be the best. The activation functions used were ReLU, LeakyReLU, PReLU, Swish. <br>
![Accuracy vs Epoch Per Activation Function Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Activation%20Function%20Training%20Data.png?raw=true)
![Accuracy vs Epoch Per Activation Function Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Activation%20Function%20Validation%20Data.png?raw=true)
![Loss vs Epoch Per Activation Function Validation Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Activation%20Function%20Validation%20Data.png?raw=true)
![Loss vs Epoch Per Activation Function Training Data](https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Activation%20Function%20Training%20Data.png?raw=true)

## Presentation
https://docs.google.com/presentation/d/1gQU2lVztwKqTSSP8K1pZRyy6yLw16d4R6ynC-JBgMgI/edit?usp=sharing
