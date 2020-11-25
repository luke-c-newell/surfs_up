# surfs_up
## Overview
My client, Mr Avy, is looking to invest in a Surfing and Ice Cream store based on the island of Oahu, Hawaii. Mr Avy would like to understand the weather patterns on the island, in order to determine whether the investment is going to be fruitful. Using historical weather data from an SQLite database, I have created a program to extract the data into Pandas DataFrames and perform a statistical analysis on both the temperature and rainfall measurements. 

## Results
- Hawaii has an average temperature of 75.0F during the month of June and an average temperature of 71.0F during the month of December. Hawaii has an average rainfall of 0.13 inches during the month of June and an average of 0.21 inches during the month of December.
- The maximum temperature reached 85.0F in June and 83.0F in December. The maximum rainfall reached 4.43 inchces in June and 6.42 inches in December.
- The standard deviation for temperature is 3.3F in June and 3.7F in December. The standard deviation for rainfall is 0.14 inches in June and 0.54 inches in December.

### June Temperature
![June_temp](https://github.com/luke-c-newell/surfs_up/blob/main/Resources/June_temp.png "June_temp.png")

### December Temperature
![December_temp](https://github.com/luke-c-newell/surfs_up/blob/main/Resources/December_temp.png "December_temp.png")

### June Precipitation
![June_rain](https://github.com/luke-c-newell/surfs_up/blob/main/Resources/June_rain.png "June_rain.png")

### December Precipitation
![December_rain](https://github.com/luke-c-newell/surfs_up/blob/main/Resources/December_rain.png "December_rain.png")

## Summary
Overall, the analysis has shown that weather in Hawaii is certainly suitable for setting up a Surf and Ice Cream shop on the island of Oahu. Hawaii's tropical climate gives consistent warm, dry weather year round, as shown by the small differences between the average June and December weather patterns. 

The small standard deviation values also support this conclusion as the average daily temperature does not fluctuate greatly in either month. The additional analysis done on rainfall values also highlights that there is very little rain on a regular basis in Hawaii. The large max values for rainfall do suggest that there are days when a significant volume of rainfall occurs, both in June and December. This should not be limiting factor in the decision to set up a Surf and Ice Cream shop on the island as for the majority of days the weather will be ideal! 

### Code sample for additional queries which created two precipitation DataFrames for June and December
``` 
december_rain = session.query(Measurement.date, Measurement.prcp).\
    filter(Measurement.date.like('%-12-%')).all()
```
``` 
june_rain = session.query(Measurement.date, Measurement.prcp).\
    filter(Measurement.date.like('%-06-%')).all()
```