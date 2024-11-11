# Code Book for the Human Activity Recognition Dataset

This code book describes the variables, units, and transformations applied to create the final tidy dataset from the Human Activity Recognition (HAR) dataset.

## Source Data
The data was collected from 30 volunteers performing six activities (walking, walking upstairs, walking downstairs, sitting, standing, and laying) while wearing smartphones equipped with inertial sensors. 

## Variables in the Tidy Dataset

### Identifier Variables

1. **subject**:
   - **Description**: Unique identifier assigned to each participant in the study.
   - **Type**: Integer.
   - **Range**: 1 to 30.

2. **activity**:
   - **Description**: The type of activity being performed by the participant when the measurement was taken.
   - **Type**: Categorical.
   - **Possible Values**: 
     - `WALKING`
     - `WALKING_UPSTAIRS`
     - `WALKING_DOWNSTAIRS`
     - `SITTING`
     - `STANDING`
     - `LAYING`

### Measurement Variables

Each measurement variable represents either a mean or standard deviation value calculated from smartphone accelerometer and gyroscope data. These values are averaged per `subject` and `activity` in the final tidy dataset.

All measurement variables follow this structure:

- **Domain Prefix**:
  - `Time`: Indicates time-domain signals (derived directly from the sensors).
  - `Frequency`: Indicates frequency-domain signals (obtained via Fast Fourier Transform).

- **Sensor Type**:
  - `Accelerometer`: Data captured by the accelerometer, measuring acceleration.
  - `Gyroscope`: Data captured by the gyroscope, measuring angular velocity.

- **Measurement Type**:
  - `Mean`: Mean value of the measurement.
  - `Std`: Standard deviation of the measurement.

- **Axis**:
  - `X`, `Y`, `Z`: Indicates the axis along which the measurement was taken, if applicable.

### Examples of Measurement Variables

1. **TimeBodyAccelerometerMeanX**:
   - **Description**: Mean of time-domain body acceleration along the X-axis.
   - **Units**: Standardized and normalized (unitless), with values typically ranging from -1 to 1.

2. **TimeBodyAccelerometerStdY**:
   - **Description**: Standard deviation of time-domain body acceleration along the Y-axis.
   - **Units**: Standardized and normalized (unitless), with values typically ranging from -1 to 1.

3. **FrequencyBodyGyroscopeMeanZ**:
   - **Description**: Mean of frequency-domain body gyroscope data along the Z-axis.
   - **Units**: Standardized and normalized (unitless), with values typically ranging from -1 to 1.

4. **TimeBodyAccelerometerMagnitudeMean**:
   - **Description**: Mean of time-domain body acceleration magnitude (combined signal across all axes).
   - **Units**: Standardized and normalized (unitless), with values typically ranging from -1 to 1.

5. **FrequencyBodyAccelerometerMagnitudeStd**:
   - **Description**: Standard deviation of the frequency-domain magnitude of body acceleration.
   - **Units**: Standardized and normalized (unitless), with values typically ranging from -1 to 1.

### Transformations Applied

1. **Merged Training and Test Sets**: Combined data from `X_train.txt`, `X_test.txt`, `y_train.txt`, `y_test.txt`, `subject_train.txt`, and `subject_test.txt` into a single dataset.
2. **Extracted Mean and Standard Deviation Measurements**: Filtered to retain only measurements of the mean and standard deviation.
3. **Applied Descriptive Activity Names**: Replaced activity codes with descriptive names (e.g., `WALKING`, `SITTING`).
4. **Renamed Columns with Descriptive Names**: Replaced abbreviations with full descriptive names, expanded prefixes, and clarified measurement types.
5. **Created Tidy Dataset**: Averaged each measurement per `subject` and `activity` to create a tidy dataset with one row per unique `subject`-`activity` combination.

### Summary of Variables

The tidy dataset includes:
- **2 Identifier Variables**: `subject` and `activity`.
- **66 Measurement Variables**: Each representing an averaged mean or standard deviation measurement across activities and subjects.

