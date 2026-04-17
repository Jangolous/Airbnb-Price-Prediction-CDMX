# Airbnb Price Prediction (Mexico City)

This project predicts Airbnb listing prices in Mexico City using machine learning.

I worked with real listing data, cleaned and prepared it, and built a model to understand which factors have the biggest impact on price. The final model (Random Forest) achieved an R² of ~0.65.


## Open in Google Colab

You can run the notebook directly in your browser:

[Open Notebook in Colab](https://colab.research.google.com/drive/1dQFzxHo9ihVtKNMMnO34eo_QUHIZjMAt?usp=sharing)


## Dataset

The data comes from Inside Airbnb and includes information such as:

- Property details (bathrooms, bedrooms, amenities)
- Location (latitude and longitude)
- Host activity and listing characteristics
- Reviews and ratings



## Workflow

### Data Cleaning
- Removed missing values in the target (`price`)
- Cleaned currency format and converted to numeric values
- Filled missing values using medians and simple indicators

### Feature Engineering
- Created `amenities_count` to capture listing quality
- Rounded latitude and longitude to approximate location zones
- Encoded categorical variables using one-hot encoding



## Modeling

Two models were tested:

- Linear Regression (baseline)
- Random Forest (final model)

### Results

| Model              | MAE | RMSE | R² |
|-------------------|-----|------|----|
| Linear Regression | 433 | 589  | 0.43 |
| Random Forest     | 312 | 459  | 0.65 |

The Random Forest model clearly performed better, capturing patterns that the linear model could not.



## Key Findings

The most important factors affecting price were:

- Room type (especially private rooms)
- Number of bathrooms
- Amenities count

This suggests that property characteristics and listing quality are the main drivers of price in this dataset.



## Visualizations

The project includes:

- Price distribution before and after outlier removal
- Price differences by room type
- Feature importance (Top 10)
- Predicted vs actual prices



## Conclusions

- Prices are mainly driven by room type and property features  
- Feature engineering (especially amenities and location grouping) improved performance  
- Random Forest significantly outperformed Linear Regression  
- The model explains about 65% of price variability and generalizes well  



## Next Steps

- Add time-based features (seasonality, demand)
- Use text data from descriptions (NLP)
- Improve location modeling with clustering or distance-based features



## Tools

- Python
- Pandas / NumPy
- Scikit-learn
- Matplotlib / Seaborn
