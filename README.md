
## Data Source
https://www.kaggle.com/manjeetsingh/retaildataset

---

## Cleaning Data

---

###  data_clean_sales.ipynb



__ clean weekly sales data__
 __ challenges in raw data:__

1. entries are recorded on different days of the week
2. some weeks have multiple entires
3. between start date and end date, about 20% of all weeks are missing

    
__ solutions to get clean data:__
1. normalize dates: since we are dealing with weekly sales, convert all dates to the Monday of that week
2. consolidate all records from a week into one dated the Monday of that week by adding their weekly sales together.
3. for each missing week, create a record dated the Monday of that week; impute its weekly sales value as follows:
    * if it's a non-holiday week, use the weekly sales value from the closeset available non-holiday week
    * else (it's a holiday week), use the mean weekly sales from the same holiday if exist,otherwise use the closest avaiable holiday weekly sales. 
    
__ clean data and save in pickles__



### data_clean_features.ipynb


__clean metadata__

---

## Generating Models

---

### modeling_generate_best_sarima_params_for_all_depts.ipynb
__ grid search and save best parameters for each SARIMA model for every dept in a store.__

### save_sarima_prediction_to_DB.ipynb
__ generate sarima prediction for each (dept, store) and save in database. __

### modeling_generate_correction_models.ipynb
__ grid search and save a Lasso metadata correction model for every dept in a store.__

### save_correction_models_to_DB.ipynb
* save metadata correction models in postgres database
* create table model_coeffs that has metadata correction model coefficients
* tables col_means and col_stds store the means and standard deviations of predictors so predicted scaled sales can be transformed back to original scale.

---

## Making Prediction

---

###  make_pediction.ipynb
__ predict weekly sales. __


---

## Data Directory
__ not included due to git hub file size limit __

---

## EDA files
__ not included - lots of exploration before finalizing approach in each component of the pipeline __


## Slides
__ pedicting_retail_sales_slides.pdf __
