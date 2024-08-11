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
Four different optimizers were used to determine which would be the best. The optimizers used were Adam, SDG, Adagrad, RMSProp. These optimizers were selected because they are typically used for classification models. <br>
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Optimizer%20Training%20Data.png?raw=true" alt="Accuracy vs Epoch Per Optimizers Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Optimizer%20Validation%20Data.png?raw=true" alt="Accuracy vs Epoch Per Optimizer Validation Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Optimizer%20Training%20Data.png?raw=true" alt="Loss vs Epoch Per Optimizer Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Optimizer%20Validation%20Data.png?raw=true" alt="Loss vs Epoch Per Optimizer Validation Data" width="500">

When comparing accuracy and loss values for both training and validation data, the Adam and RMSprop optimizers demonstrated the lowest loss and highest accuracy. This is expected, as Adam's optimization technique incorporates aspects of RMSprop.

The poorest performing optimizer for both validation and training data was Adagrad, while SGD performed slightly worse than Adam and RMSprop. Choosing between RMSprop and Adam was difficult, but Adam was ultimately selected for its versatility.


### Neurons


<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Neurons%20Training%20Data.png?raw=true" alt="Accuracy vs Epoch Per Neurons Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Neurons%20Validation%20Data.png?raw=true" alt="Accuracy vs Epoch Per Neurons Validation Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Neurons%20Training%20Data.png?raw=true" alt="Loss vs Epoch Per Neurons Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Neurons%20Validation%20Data.png?raw=true" alt="Loss vs Epoch Per Neurons Validation Data" width="500">


### Activation Functions
Four different activation functions were used to determine which would be the best. The activation functions used were ReLU, LeakyReLU, PReLU, Swish. <br>
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Activation%20Function%20Training%20Data.png?raw=true" alt="Accuracy vs Epoch Per Activation Function Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Per%20Activation%20Function%20Validation%20Data.png?raw=true" alt="Accuracy vs Epoch Per Activation Function Validation Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Activation%20Function%20Training%20Data.png?raw=true" alt="Loss vs Epoch Per Activation Function Training Data" width="500"><img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Per%20Activation%20Function%20Validation%20Data.png?raw=true" alt="Loss vs Epoch Per Activation Function Validation Data" width="500">

When comparing the accuracy and loss values across training and validation data, all activation functions performed similarly. However, the validation data showed noticeable fluctuations in loss and accuracy, which could indicate potential overfitting. 

Ultimately, the Swish activation function was chosen for the final model because it produced the lowest loss and highest accuracy. That said, any of the activation functions used could be effective, yielding relatively low loss and high accuracy values.

### Final Model
The final model used the Adam optimizer, Swish activation functions, and had hidden layers structured with 64, 32, 16, and 8 neurons, respectively. It was trained for 20 epochs, rather than 50, as longer training resulted in noticeable overfitting on the training data. Twenty epochs were selected because the accuracy and loss values on the validation data did not show significant improvement beyond this point. The testing data achieved a loss value of 0.25 and an accuracy of 0.90, which showed little significant improvement over many other optimization models.<br>
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Final%20Model%20Training%20Data.png?raw=true" alt="Accuracy vs Epoch Final Model Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Accuracy%20vs%20Epoch%20Final%20Model%20Validation%20Data.png?raw=true" alt="Accuracy vs Epoch Final Model Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Final%20Model%20Training%20Data.png?raw=true" alt="Accuracy vs Epoch Final Model Training Data" width="500">
<img src="https://github.com/cassidyschul/weather_prediction/blob/main/Plots/Loss%20vs%20Epoch%20Final%20Model%20Validation%20Data.png?raw=true" alt="Accuracy vs Epoch Final Model Training Data" width="500">

## Presentation
https://docs.google.com/presentation/d/1gQU2lVztwKqTSSP8K1pZRyy6yLw16d4R6ynC-JBgMgI/edit?usp=sharing
