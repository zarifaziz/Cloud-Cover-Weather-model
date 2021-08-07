# Cloud-Cover-Weather-model
Modelling cloud cover at different heights based on Okta values. Creating by extracting METAR data from weather stations. 


## Getting Started

These instructions will get you a copy of the tool up and running on your local machine.

### Prerequisites

The program requires [Python >= 3.7](https://www.python.org/downloads/) to be downloaded and installed on the machine.
Last tested on Python 3.7.

#### 1. 'Weather Model US'
- Input: Iowa Environmental Mesonet (IEM) dataset of Cloud data
- Process: Shows the process of pulling 7 years of METAR data from the IEM and then processing it to
give a quantifiable measure of Okta (cloud cover) values throughout the U.S.
- Output: Dataframe containing average Okta value for each day of the year at 50 weather stations across the U.S. This
dataframe is called `US_weather_7yr_avg`
- Only edit this notebook if you want to pull more data (e.g. more weather stations across the U.S.)

#### 2. 'Spatial Interpolation of Weather Data'
- Input: `US_weather_7yr_avg` dataframe
- Process: An okta prediction model is trained using data points at 50 weather stations. This model is used to interpolate okta values across the U.S. interpolate them across the U.S. Now we can obtain average Okta values at any lat, lon position in the U.S.
- Output: Regression model trained over 5 years of weather data `gprs_7yr_pickled`
- Only edit this notebook if the prediction model needs to be trained again over new data, or change required in the model itself.

Visualisation of Cloud Cover across the U.S. on different days:
![Weather Model using METAR data | 30%](./images/weather_model.gif)
