
## Project Description Slides
#### pedicting_retail_sales_slides.pdf 



## Data Source
https://www.kaggle.com/manjeetsingh/retaildataset

---

## Cleaning Data

---

###  data_clean_sales.ipynb



#### clean weekly sales data
#### challenges in raw data:

1. entries are recorded on different days of the week
2. some weeks have multiple entires
3. between start date and end date, about 20% of all weeks are missing

    
#### solutions to get clean data:
1. normalize dates: since we are dealing with weekly sales, convert all dates to the Monday of that week
2. consolidate all records from a week into one dated the Monday of that week by adding their weekly sales together.
3. for each missing week, create a record dated the Monday of that week; impute its weekly sales value as follows:
    * if it's a non-holiday week, use the weekly sales value from the closeset available non-holiday week
    * else (it's a holiday week), use the mean weekly sales from the same holiday if exist,otherwise use the closest avaiable holiday weekly sales. 
    
#### clean data and save in pickles



### data_clean_features.ipynb


#### clean metadata

---

## Generating Models

---

### modeling_generate_best_sarima_params_for_all_depts.ipynb
#### grid search and save best parameters for each SARIMA model for every dept in a store.

### save_sarima_prediction_to_DB.ipynb
#### generate sarima prediction for each (dept, store) and save in database. 

### modeling_generate_correction_models.ipynb
#### grid search and save a Lasso metadata correction model for every dept in a store.

### save_correction_models_to_DB.ipynb
* save metadata correction models in postgres database
* create table model_coeffs that has metadata correction model coefficients
* tables col_means and col_stds store the means and standard deviations of predictors so predicted scaled sales can be transformed back to original scale.

---

## Making Prediction

---

###  make_pediction.ipynb
#### predict weekly sales. 


---

## Data Directory
#### not included due to git hub file size limit 

---

## EDA files
#### not included - lots of exploration before finalizing approach in each component of the pipeline 



