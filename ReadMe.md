# Getting and Cleaning Data - Project README

This project is part of the Getting and Cleaning Data course. It includes an R script (`run_analysis.R`) that processes and tidies the "Human Activity Recognition Using Smartphones" dataset.

## Contents
1. `run_analysis.R`: R script to clean and transform the data.
2. `CodeBook.md`: Codebook detailing variables, units, and transformations.
3. `tidy_data.txt`: The final tidy data set.

## Data Source
The data used in this project was collected from 30 volunteers who performed six different activities while wearing smartphones with embedded inertial sensors.

### Instructions to Run the Analysis
1. Download and unzip the dataset from the [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).
2. Place the `run_analysis.R` script in the same directory as the unzipped data folder.
3. Run the script in R or RStudio.
   ```R
   source("run_analysis.R")
