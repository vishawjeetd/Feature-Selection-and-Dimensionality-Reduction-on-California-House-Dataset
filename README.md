
![Logo](https://github.com/vishawjeetd/Feature-Selection-and-Dimensionality-Reduction-on-California-House-Dataset/blob/main/img/title.png?raw=true)

## Implementation Details

### Dataset Details
- **Dataset:** California Housing Dataset from SKLEARN
- **Data Granularity:** Block level
- **Input:** Location, Age of house, Income, Number of rooms & bedrooms, Occupancy of household members, Population
- **Output:** House Prices
- **Source:** 1990 U.S. census
- **Number of Instances:** 20640

### Technical Details
- **Programming Language:** Python
- **Jupyter Notebook:** Google Colab
- **Packages Used:** sklearn, pandas, numpy, ydata_profiling
- **Code file:** [Feature_Selection_and_Dimensionality_Reduction_Techniques_on_California_House_Price_Dataset.ipynb](https://github.com/vishawjeetd/Feature-Selection-and-Dimensionality-Reduction-on-California-House-Dataset/blob/f9ac00a6c16fea1b893676d430d7bed31a0e9ae3/src/Feature_Selection_and_Dimensionality_Reduction_Techniques_on_California_House_Price_Dataset.ipynb)


# Feature Selection and Dimensionality Reduction Techniques on California House Price Dataset

Explores various methods to enhance predictive modeling on the California Housing dataset. This study delves into feature selection and dimensionality reduction approaches to identify the most relevant features and reduce the dataset's complexity. By systematically evaluating techniques such as variance thresholding, SelectKBest, SelectPercentile, Recursive Feature Elimination (RFE), and Principal Component Analysis (PCA), this analysis aims to optimize model performance and interpretability for predicting house prices in California.
## Hierarchy

![feature_selection_hierarchy](https://github.com/vishawjeetd/Feature-Selection-and-Dimensionality-Reduction-on-California-House-Dataset/blob/f9ac00a6c16fea1b893676d430d7bed31a0e9ae3/img/feature_selection_hierarchy.png?raw=true)


## Results

| Experiment Name                                     | Excluded Features                            | Selected Features                        | R2 Score    | MSE          |
|-----------------------------------------------------|---------------------------------------------|------------------------------------------|-------------|--------------|
| Base Model Run - with all features                  | ['MedInc', 'HouseAge', 'AveRooms', 'AveBedrms', 'Population', 'AveOccup', 'Latitude', 'Longitude'] |                                            | 0.610963372 | 0.540412806  |
| Exp 1 - Variance Threshold of 70%                   | ['AveBedrms']                               | ['MedInc', 'HouseAge', 'AveRooms', 'Population', 'AveOccup', 'Latitude', 'Longitude']              | 0.60159948  | 0.556502204  |
| Exp 2 - SelectKBest with mutual info: top 4 features| ['HouseAge', 'AveBedrms', 'Population', 'AveOccup'] | ['MedInc', 'AveRooms', 'Latitude', 'Longitude']                                                      | 0.590175743 | 0.569146713  |
| Exp 3 - SelectKBest with pearson correlation: top 4 features | ['AveBedrms', 'Population', 'Latitude', 'Longitude'] | ['MedInc', 'HouseAge', 'AveRooms', 'AveOccup']                                                     | 0.52083862  | 0.673465188  |
| Exp 4 - SelectKBest with F statistics: top 4 features | ['AveBedrms', 'Population', 'AveOccup', 'Longitude'] | ['MedInc', 'HouseAge', 'AveRooms', 'Latitude']                                                     | 0.526108352 | 0.665196663  |
| Exp 5 - SelectPercentile with mutual info: top 50 percentile | ['HouseAge', 'AveBedrms', 'Population', 'AveOccup'] | ['MedInc', 'AveRooms', 'Latitude', 'Longitude']                                                     | 0.590175743 | 0.569146713  |
| Exp 6 - SelectPercentile with pearson correlation: top 50 percentile | ['AveBedrms', 'Population', 'Latitude', 'Longitude'] | ['MedInc', 'HouseAge', 'AveRooms', 'AveOccup']                                                     | 0.52083862  | 0.673465188  |
| Exp 7 - SelectPercentile with F statistics: top 50 percentile | ['AveBedrms', 'Population', 'AveOccup', 'Longitude'] | ['MedInc', 'HouseAge', 'AveRooms', 'Latitude']                                                     | 0.526108352 | 0.665196663  |
| Exp 8 - RFE - Lasso - 4 features                    | ['AveRooms', 'AveBedrms', 'AveOccup', 'Latitude'] | ['MedInc', 'HouseAge', 'Population', 'Longitude']                                                    | 0.518237308 | 0.679906795  |
| Exp 9 - Select from Model - Lasso on regression     | ['HouseAge', 'AveRooms', 'AveBedrms', 'Population', 'AveOccup', 'Latitude', 'Longitude'] | ['MedInc']                                                                                            | 0.480619308 | 0.725353457  |
| Exp 10 - Sequential Feature selection - Forward     | ['Population', 'AveOccup', 'Latitude', 'Longitude'] | ['MedInc', 'HouseAge', 'AveRooms', 'AveBedrms']                                                     | 0.544852646 | 0.641648571  |
| Exp 11 - Sequential Feature selection - Backward    | ['AveRooms', 'AveBedrms', 'Population', 'AveOccup'] | ['MedInc', 'HouseAge', 'Latitude', 'Longitude']                                                     | 0.599569183 | 0.559400348  |
| Exp 12 - Lasso                                      |                                               |                                          | 0.2923162   | 0.945250079  |
| Exp 13 - PCA - 4 Components                         |                                               |                                          | 0.011731481 | 1.313124391  |



## Summary

Since The California Housing Dataset, being a prebuilt dataset, offers a relatively cleaner and more structured environment for experimentation. We have failed to improve model significantly.

But in real-world dataset, feature selection and dimensionality reduction play critical roles in improving model performance and interpretability. Through systematic experimentation and evaluation of various techniques, we can identify the most suitable methods for a given dataset and modeling task, ultimately enhancing the effectiveness of predictive modeling on real-world datasets like the California Housing Dataset
