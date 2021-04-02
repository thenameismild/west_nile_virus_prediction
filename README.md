# West Nile Virus Prediction

West Nile virus is most commonly spread to humans through infected mosquitos. Around 20% of people who become infected with the virus develop symptoms ranging from a persistent fever, to serious neurological illnesses that can result in death.

In 2002, the first human cases of West Nile virus were reported in Chicago. By 2004 the City of Chicago and the Chicago Department of Public Health (CDPH) had established a comprehensive surveillance and control program that is still in effect today.

It is believed that hot and dry conditions are more favorable for West Nile virus than cold and wet. 

### The Problem
The West Nile Virus have infected over 4,200 people and killed 177 people in 2006.

The CDC wants us to explore weather, location, testing, and spraying data, to predict when and where different species of mosquitoes will test positive for West Nile virus.

Thus, allowing them to effectively allocate resources towards preventing transmission

### The Data
- Train Data Set
  - Contains 12 columns with features like location, no of mosquitos, virus negative or positive
- Test Data Set
  - Contains 11 columns with information like the train data set without the virus present data
- The Weather Data
  - Contains 22 columns of weather data from different years, with information on temperature, humidity and spray station location
- The Spray Data
  - Contains 4 columns of spraier location, date and time 

There are two spray location:
- Spray Station 1 is at Chicago O'hare Intl Airport
- Spray Station 2 is at Chicago Midway Intl Airport

### Data Preprocessing
Before we begin modeling there was an imbalance in data so we perform SMOTE to increase the imnority classes. Since there are also lots of features that effect the virus like temperature, humidity and species with performed PCA on the different features to maximized out model prediction features.

We also created a time lag in the data since for mosquitos to be able to spread the West Nile Virus it has to mature first so we provided a 10 days lag in the weather data to give that maturity phase a factor in the data we have.

### The Model
In the project we tested 5 different prediction models: SVM, Logistic Rergession, Decision Tree, Random Forest and XGBoost all provided high AUC score on the AOC curve.

However, the Random Forest model performed the best giving and AUC accuracy of 0.718, Precision of 0.15, Recall of 0.63 and F1 score of 0.25.

The best features found to be useful in this prediction:
- 10 days lagged weather information
- Present weather (temperature, wind)
- Location
- Temporal features (date and time)
- Species
- Mosquito life cycle

### The Result
From the model we were able to gain probability of where in Chicago we may find that the virus will be positive. In the data we were able to cluster the location into 6 different districts in Chicago:
1. West Englewood 
2. East Garfield Park
3. New City
4. South Side
5. Near West Side
6. Central Chicago

From the prediction we were able to see that the highest probability that the virus will be positive is in the Near West Side District follow by the East Garfield Park District.

However, looking more closely we can see that the virus spread is different depending on the month but we can see a high probability of the virus being positive from August to October where New City, SOuth Side and Near West Side district will be effected by the virus the most.

### Recommendations
From the results there have be some allocation of resources when dealing with the killing of the West Nile Virus, since there are different area effected in each month and different positive probability rate as well.

This means that Chicago should focus on the high populated area first in the top districts such as the Near West Side then work towards other high contraction districts. This way the resources are spread out in different areas and not just one district.

From the data provided we were able to provide a good prediction, however for the future we can consider:
- Predicting present number of mosquitos
- Consider spray effectiveness
- Spray radius and spread
