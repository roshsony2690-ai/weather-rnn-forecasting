# RNN for Weather Forecasting

## Overview
This notebook implements a Recurrent Neural Network (RNN) model to predict the next day's temperature based on the past week's weather data. The model uses historical weather information to forecast future temperatures.

## Dataset
The model uses a weather history dataset (Weather_History.csv) containing the following key features:   
• Temperature (C) - Target variable   
• Humidity - Input feature   
• Wind Speed (km/h) - Input feature   
• Formatted Date - Timestamp   
• Additional weather metrics (apparent temperature, pressure, visibility, etc.)    

## Project Structure 

### Part A: Data Loading, Exploration, and Preprocessing     
• Load and explore the dataset          
• Handle missing values using forward fill and backward fill imputation            
• Normalize data using MinMaxScaler          
• Create input sequences using 7 days of past weather data to predict the next day's temperature           

### Part B: RNN Model Development            
• Build a SimpleRNN model with:              
• SimpleRNN layer (64 units, tanh activation)            
• Dropout layer (0.2) for regularization             
• Dense output layer (1 unit for regression)             
• Compile the model using Adam optimizer with MSE loss          
• Train with early stopping to prevent overfitting                   

### Part C: Model Evaluation & Forecasting          
• Evaluate model performance using RMSE, MAE, and R² metrics             
• Visualize predicted vs actual temperatures          
• Forecast next 7 days of temperature            
• Generate forecast summary statistics             

## Model Architecture    
| Layer         | Output Shape | Parameters | Purpose                                                              |         
| ------------- | ------------ | ---------- | -------------------------------------------------------------------- |          
| **SimpleRNN** | (None, 64)   | 4,352      | Learns sequential patterns and temporal dependencies from input data |         
| **Dropout**   | (None, 64)   | 0          | Randomly disables neurons during training to prevent overfitting     |       
| **Dense**     | (None, 1)    | 65         | Produces the final prediction output                                 |         

## Results 
The model demonstrates strong performance on the test set:       
| Metric       | Value  | Meaning                                                                                                                                |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------- |
| **RMSE**     | 1.1602 | On average, predictions differ from actual values by about **1.16 units**, with larger errors penalized more heavily. Lower is better. |
| **MAE**      | 0.7724 | The average absolute prediction error is about **0.77 units**. This means predictions are usually very close to the real values.       |
| **R² Score** | 0.9831 | The model explains **98.31% of the variance** in the data, which indicates an excellent fit.                                           |

## Dependencies 
• pandas       
• numpy     
• matplotlib   
• seaborn    
• scikit-learn    
• tensorflow   
• warnings   

## Usage 
☑ Ensure Weather_History.csv is in the /content/ directory   
☑ Run all cells sequentially    
☑ The model will train and produce temperature forecasts for the next 7 days     
  
## Output      
• Training/validation loss and MAE curves     
• Predicted vs actual temperature plots     
• Scatter plot correlation    
• Next 7 days temperature forecast with visualization    
• Forecast summary statistics     

### Result/Plots
<img width="1556" height="686" alt="Screenshot 2026-05-07 200130" src="https://github.com/user-attachments/assets/01dbfe34-a8ed-432f-bd80-baeb06ddccc4" />
<img width="1482" height="608" alt="Screenshot 2026-05-07 200206" src="https://github.com/user-attachments/assets/90780bee-28de-4a2b-8efb-3919cb1bf402" />
<img width="1458" height="685" alt="Screenshot 2026-05-07 200237" src="https://github.com/user-attachments/assets/33c46db0-11d9-46fb-bca1-927ac1cf5ddc" />

