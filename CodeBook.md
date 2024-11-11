# Code Book for the Human Activity Recognition Dataset

This code book describes the dataset, variables, transformations, and units for the tidy dataset created as part of the `run_analysis.R` script.

## Source Data
The data was obtained from the UCI Machine Learning Repository and pertains to measurements collected from accelerometers and gyroscopes on smartphones worn by participants performing various activities.

### Feature Selection and Transformation
The original dataset had numerous measurements, but only those related to the mean and standard deviation of each measurement were selected.

Variables

1. subject: 
   - Description: ID of the participant (numeric).
   - Range: 1 to 30.

2. activity: 
   - Description: Activity performed by the subject.
   - Possible Values: 
     - WALKING
     - WALKING_UPSTAIRS
     - WALKING_DOWNSTAIRS
     - SITTING
     - STANDING
     - LAYING

3. Measurement Variables: 
   - Description: Each of these variables represents either a mean or standard deviation calculation for various sensor signals collected by the accelerometers and gyroscopes.
   - Units: All measurements are in normalized form, ranging between -1 and 1.
   - Naming Conventions:
     - TimeDomain (Time): Time-based signals, indicated by `Time` at the beginning of the variable.
     - FrequencyDomain (Frequency): Frequency-based signals, indicated by `Frequency` at the beginning of the variable.
     - Accelerometer: Accelerometer signals, indicated by `Accelerometer`.
     - Gyroscope: Gyroscope signals, indicated by `Gyroscope`.
     - Magnitude: Combined magnitude signals, indicated by `Magnitude`.

Summary of Calculations
Each variable is an average of the mean and standard deviation values per `subject` and `activity`, calculated using the `run_analysis.R` script.

Example of variable names:
   - `TimeBodyAccelerometerMeanX`: Mean of time-domain body acceleration along the X-axis.
   - `FrequencyBodyGyroscopeMeanY`: Mean of frequency-domain body gyroscope signal along the Y-axis.
   - `TimeBodyAccelerometerStdZ`: Standard deviation of time-domain body acceleration along the Z-axis.

Transformations
1. The dataset was merged from training and test sets.
2. Only mean and standard deviation measurements were retained.
3. Activity codes were replaced with descriptive activity names.
4. Variable names were made more descriptive.
5. A tidy dataset was created with the average of each variable for each `activity` and `subject`.
