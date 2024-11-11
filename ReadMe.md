# Getting and Cleaning Data - Project README

This project is part of the **Getting and Cleaning Data** course. It includes an R script (`run_analysis.R`) that processes and tidies the "Human Activity Recognition Using Smartphones" dataset.

## Contents
1. `run_analysis.R`: R script to clean and transform the data.
2. `CodeBook.md`: Codebook detailing variables, units, and transformations.
3. `tidy_data.txt`: The final tidy data set.

## Data Source
The data used in this project was collected from 30 volunteers who performed six different activities while wearing smartphones with embedded inertial sensors. Download the data from the [UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).

### How the `run_analysis.R` Script Works

This script performs the following steps to clean and tidy the dataset:

### Step 1: Merging the Training and Test Sets
   - The script reads the `X_train.txt`, `y_train.txt`, `subject_train.txt`, and corresponding test files (`X_test.txt`, `y_test.txt`, `subject_test.txt`).
   - It loads the feature names from `features.txt` and the activity labels from `activity_labels.txt`.
   - It binds the rows of training and test data together to create a single dataset (`merged_data`) with columns for subject, activity, and all measurements.

### Step 2: Extracting Mean and Standard Deviation Measurements
   - The script filters the columns to retain only measurements related to the mean and standard deviation, as identified in `features.txt`.
   - This selection is done using `grep` to match columns containing "mean()" or "std()".

### Step 3: Applying Descriptive Activity Names
   - The `activity_labels.txt` file is used to replace activity codes with descriptive activity names, making the data more readable.
   - The script maps these activity names to the corresponding activities in `merged_data`.

### Step 4: Labeling Data with Descriptive Variable Names
   - The script updates the variable names to be more descriptive:
     - `t` is replaced with "Time" (for time-domain signals).
     - `f` is replaced with "Frequency" (for frequency-domain signals).
     - Abbreviations like "Acc" and "Gyro" are expanded to "Accelerometer" and "Gyroscope".
     - Other abbreviations are similarly expanded for clarity.

### Step 5: Creating a Tidy Dataset
   - The script generates a second independent tidy dataset (`tidy_data`) by calculating the average of each variable for each activity and each subject.
   - It groups the data by `subject` and `activity` and then summarizes each variable by its mean.

### Output
   - The final output is saved as `tidy_data.txt`, a tidy dataset where each row corresponds to a unique combination of subject and activity with the average of each measurement.

### Instructions to Run the Analysis
1. Download and unzip the dataset from the UCI HAR Dataset.
2. Place the `run_analysis.R` script in the same directory as the unzipped data folder.
3. Run the script in R or RStudio by executing:
   ```R
   source("run_analysis.R")
