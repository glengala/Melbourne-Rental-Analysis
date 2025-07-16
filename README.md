Melbourne Rental Price Analysis & Forecasting

A comprehensive end-to-end data science project that preprocesses Melbourne-Metro rental data, explores spatial and temporal trends across Local Government Areas (LGAs), ranks the most and least expensive LGAs, and trains a baseline machine learning model to predict median rents.

Table of Contents
Project Structure

Features

Installation

Data Preparation

Usage

Results & Outputs

Next Steps

Contributing

License

Project Structure
Path	Description
data/	Raw Excel files and cleaned CSV exports
notebooks/	Jupyter notebooks for preprocessing, EDA, and modeling
scripts/	Python modules encapsulating pipeline steps:
&nbsp;&nbsp;preprocess_data.py	Flatten and clean multi-sheet Excel rental data
&nbsp;&nbsp;eda_plots.py	Generate exploratory plots of median rent trends
&nbsp;&nbsp;lga_ranking.py	Identify and visualize top N most/least expensive LGAs
&nbsp;&nbsp;baseline_model.py	Build and evaluate a Random Forest regression pipeline
outputs/	Saved plots and model reports
requirements.txt	Library dependencies
README.md	Project overview and usage instructions
Features
Ingest and clean multi-sheet Excel rental data into long-form CSV

Visualize yearly median rent trends by Region and LGA

Rank and plot top N most and least expensive LGAs for any year, region, property type, and bedroom count

Train a baseline Random Forest regressor with one-hot encoding

Evaluate model performance using Mean Absolute Percentage Error (MAPE)

Installation
Clone the repository

bash
git clone https://github.com/yourusername/melbourne-rental-forecast.git
cd melbourne-rental-forecast
Create a virtual environment (optional but recommended)

bash
python3 -m venv venv
source venv/bin/activate
Install dependencies

bash
pip install -r requirements.txt
Data Preparation
Place the raw Excel file (e.g., Data.xlsx) in the data/ folder.

Run the preprocessing script to flatten and clean all sheets:

bash
python scripts/preprocess_data.py \
  --input data/Data.xlsx \
  --output data/Project1_cleaned_all.csv
Usage
Exploratory Data Analysis
Generate median rent trend plots by region or LGA:

bash
python scripts/eda_plots.py --region Metro
python scripts/eda_plots.py --region "Southern Metro"
LGA Ranking
Rank the top 5 most and least expensive LGAs for 2024, Metro region, 2-bedroom flats:

bash
python scripts/lga_ranking.py \
  --year 2024 \
  --region Metro \
  --property_type Flat \
  --bedrooms 2 \
  --top_n 5
Baseline Modeling
Train and evaluate a Random Forest regressor:

bash
python scripts/baseline_model.py \
  --data_path data/Project1_cleaned_all.csv \
  --n_estimators 10
Results & Outputs
All generated plots and model performance metrics are saved in the outputs/ folder:

yearly_median_rent_per_region_<region>.png

yearly_LGA_median_rent_per_region_<region>.png

top_expensive_cheap_LGAs_<year>_<region>_<type>_<beds>.png

baseline_model_report.txt (contains MAPE and other evaluation metrics)

Next Steps
Implement time-aware train/test splits for true forecasting

Perform hyperparameter tuning with GridSearchCV or RandomizedSearchCV

Engineer additional features (lagged rents, macroeconomic indicators)

Integrate experiment tracking (MLflow, Weights & Biases)

Develop an interactive dashboard using Streamlit or Dash

Contributing
Contributions are welcome! Please fork the repo, create a feature branch, and submit a pull request. For major changes, open an issue to discuss your ideas first.
