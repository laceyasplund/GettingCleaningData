# Getting & Cleaning Data

## Course Project Description
The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. You will be graded by your peers on a series of yes/no questions related to the project. You will be required to submit: 1) a tidy data set as described below, 2) a link to a Github repository with your script for performing the analysis, and 3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.  

## The Experiment
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

## The Data Used

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

Notes: 
- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

License:
========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.

## run_analysis.R
This code does the following:
1. Merges the training and the test sets to create one data set.

2. Extracts only the measurements on the mean and standard deviation for each measurement. 

3. Uses descriptive activity names to name the activities in the data set
	* Provided in 'activity_labels.txt'

4. Appropriately labels the data set with descriptive variable names. 
	* leading t or f is based on time or frequency measurements.
	* Body = related to body movement.
	* Gravity = acceleration of gravity
	* Acc = accelerometer measurement
	* Gyro = gyroscopic measurements
	* Jerk = sudden movement acceleration
	* Mag = magnitude of movement
	* mean and SD are calculated for each subject for each activity for each mean and SD measurements. The units given are g’s for the accelerometer and rad/sec for the gyro and g/sec and rad/sec/sec for the corresponding jerks.

5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
	*See TidyData.txt in Resulting Datasets

# Resulting Datasets

## dataset1.txt 
contains 10299 rows and 81 columns in a default txt format.
Variables: "id" "activity" "timeBodyAccelerometer.SD...X" "timeBodyAccelerometer.SD...Y" "timeBodyAccelerometer.SD...Z" "timeGravityAccelerometer.SD...X" "timeGravityAccelerometer.SD...Y" "timeGravityAccelerometer.SD...Z" "timeBodyAccelerometerJerk.SD...X" "timeBodyAccelerometerJerk.SD...Y" "timeBodyAccelerometerJerk.SD...Z" "timeBodyGyroscope.SD...X" "timeBodyGyroscope.SD...Y" "timeBodyGyroscope.SD...Z" "timeBodyGyroscopeJerk.SD...X" "timeBodyGyroscopeJerk.SD...Y" "timeBodyGyroscopeJerk.SD...Z" "timeBodyAccelerometerMagnitude.SD.." "timeGravityAccelerometerMagnitude.SD.." "timeBodyAccelerometerJerkMagnitude.SD.." "timeBodyGyroscopeMagnitude.SD.." "timeBodyGyroscopeJerkMagnitude.SD.." "frequencyBodyAccelerometer.SD...X" "frequencyBodyAccelerometer.SD...Y" "frequencyBodyAccelerometer.SD...Z" "frequencyBodyAccelerometerJerk.SD...X" "frequencyBodyAccelerometerJerk.SD...Y" "frequencyBodyAccelerometerJerk.SD...Z" "frequencyBodyGyroscope.SD...X" "frequencyBodyGyroscope.SD...Y" "frequencyBodyGyroscope.SD...Z" "frequencyBodyAccelerometerMagnitude.SD.." "frequencyBodyAccelerometerJerkMagnitude.SD.." "frequencyBodyGyroscopeMagnitude.SD.." "frequencyBodyGyroscopeJerkMagnitude.SD.." "timeBodyAccelerometer.MEAN...X" "timeBodyAccelerometer.MEAN...Y" "timeBodyAccelerometer.MEAN...Z" "timeGravityAccelerometer.MEAN...X" "timeGravityAccelerometer.MEAN...Y" "timeGravityAccelerometer.MEAN...Z" "timeBodyAccelerometerJerk.MEAN...X" "timeBodyAccelerometerJerk.MEAN...Y" "timeBodyAccelerometerJerk.MEAN...Z" "timeBodyGyroscope.MEAN...X" "timeBodyGyroscope.MEAN...Y" "timeBodyGyroscope.MEAN...Z" "timeBodyGyroscopeJerk.MEAN...X" "timeBodyGyroscopeJerk.MEAN...Y" "timeBodyGyroscopeJerk.MEAN...Z" "timeBodyAccelerometerMagnitude.MEAN.." "timeGravityAccelerometerMagnitude.MEAN.." "timeBodyAccelerometerJerkMagnitude.MEAN.." "timeBodyGyroscopeMagnitude.MEAN.." "timeBodyGyroscopeJerkMagnitude.MEAN.." "frequencyBodyAccelerometer.MEAN...X" "frequencyBodyAccelerometer.MEAN...Y" "frequencyBodyAccelerometer.MEAN...Z" "frequencyBodyAccelerometer.MEANFreq...X" "frequencyBodyAccelerometer.MEANFreq...Y" "frequencyBodyAccelerometer.MEANFreq...Z" "frequencyBodyAccelerometerJerk.MEAN...X" "frequencyBodyAccelerometerJerk.MEAN...Y" "frequencyBodyAccelerometerJerk.MEAN...Z" "frequencyBodyAccelerometerJerk.MEANFreq...X" "frequencyBodyAccelerometerJerk.MEANFreq...Y" "frequencyBodyAccelerometerJerk.MEANFreq...Z" "frequencyBodyGyroscope.MEAN...X" "frequencyBodyGyroscope.MEAN...Y" "frequencyBodyGyroscope.MEAN...Z" "frequencyBodyGyroscope.MEANFreq...X" "frequencyBodyGyroscope.MEANFreq...Y" "frequencyBodyGyroscope.MEANFreq...Z" "frequencyBodyAccelerometerMagnitude.MEAN.." "frequencyBodyAccelerometerMagnitude.MEANFreq.." "frequencyBodyAccelerometerJerkMagnitude.MEAN.." "frequencyBodyAccelerometerJerkMagnitude.MEANFreq.." "frequencyBodyGyroscopeMagnitude.MEAN.." "frequencyBodyGyroscopeMagnitude.MEANFreq.." "frequencyBodyGyroscopeJerkMagnitude.MEAN.." "frequencyBodyGyroscopeJerkMagnitude.MEANFreq.."

## TidyData.txt
contains 180 rows and 81 columns in a default csv format.
Variables:"id" "activity" "timeBodyAccelerometer.SD...X_AVG" "timeBodyAccelerometer.SD...Y_AVG" "timeBodyAccelerometer.SD...Z_AVG" "timeGravityAccelerometer.SD...X_AVG" "timeGravityAccelerometer.SD...Y_AVG" "timeGravityAccelerometer.SD...Z_AVG" "timeBodyAccelerometerJerk.SD...X_AVG" "timeBodyAccelerometerJerk.SD...Y_AVG" "timeBodyAccelerometerJerk.SD...Z_AVG" "timeBodyGyroscope.SD...X_AVG" "timeBodyGyroscope.SD...Y_AVG" "timeBodyGyroscope.SD...Z_AVG" "timeBodyGyroscopeJerk.SD...X_AVG" "timeBodyGyroscopeJerk.SD...Y_AVG" "timeBodyGyroscopeJerk.SD...Z_AVG" "timeBodyAccelerometerMagnitude.SD.._AVG" "timeGravityAccelerometerMagnitude.SD.._AVG" "timeBodyAccelerometerJerkMagnitude.SD.._AVG" "timeBodyGyroscopeMagnitude.SD.._AVG" "timeBodyGyroscopeJerkMagnitude.SD.._AVG" "frequencyBodyAccelerometer.SD...X_AVG" "frequencyBodyAccelerometer.SD...Y_AVG" "frequencyBodyAccelerometer.SD...Z_AVG" "frequencyBodyAccelerometerJerk.SD...X_AVG" "frequencyBodyAccelerometerJerk.SD...Y_AVG" "frequencyBodyAccelerometerJerk.SD...Z_AVG" "frequencyBodyGyroscope.SD...X_AVG" "frequencyBodyGyroscope.SD...Y_AVG" "frequencyBodyGyroscope.SD...Z_AVG" "frequencyBodyAccelerometerMagnitude.SD.._AVG" "frequencyBodyAccelerometerJerkMagnitude.SD.._AVG" "frequencyBodyGyroscopeMagnitude.SD.._AVG" "frequencyBodyGyroscopeJerkMagnitude.SD.._AVG" "timeBodyAccelerometer.MEAN...X_AVG" "timeBodyAccelerometer.MEAN...Y_AVG" "timeBodyAccelerometer.MEAN...Z_AVG" "timeGravityAccelerometer.MEAN...X_AVG" "timeGravityAccelerometer.MEAN...Y_AVG" "timeGravityAccelerometer.MEAN...Z_AVG" "timeBodyAccelerometerJerk.MEAN...X_AVG" "timeBodyAccelerometerJerk.MEAN...Y_AVG" "timeBodyAccelerometerJerk.MEAN...Z_AVG" "timeBodyGyroscope.MEAN...X_AVG" "timeBodyGyroscope.MEAN...Y_AVG" "timeBodyGyroscope.MEAN...Z_AVG" "timeBodyGyroscopeJerk.MEAN...X_AVG" "timeBodyGyroscopeJerk.MEAN...Y_AVG" "timeBodyGyroscopeJerk.MEAN...Z_AVG" "timeBodyAccelerometerMagnitude.MEAN.._AVG" "timeGravityAccelerometerMagnitude.MEAN.._AVG" "timeBodyAccelerometerJerkMagnitude.MEAN.._AVG" "timeBodyGyroscopeMagnitude.MEAN.._AVG" "timeBodyGyroscopeJerkMagnitude.MEAN.._AVG" "frequencyBodyAccelerometer.MEAN...X_AVG" "frequencyBodyAccelerometer.MEAN...Y_AVG" "frequencyBodyAccelerometer.MEAN...Z_AVG" "frequencyBodyAccelerometer.MEANFreq...X_AVG" "frequencyBodyAccelerometer.MEANFreq...Y_AVG" "frequencyBodyAccelerometer.MEANFreq...Z_AVG" "frequencyBodyAccelerometerJerk.MEAN...X_AVG" "frequencyBodyAccelerometerJerk.MEAN...Y_AVG" "frequencyBodyAccelerometerJerk.MEAN...Z_AVG" "frequencyBodyAccelerometerJerk.MEANFreq...X_AVG" "frequencyBodyAccelerometerJerk.MEANFreq...Y_AVG" "frequencyBodyAccelerometerJerk.MEANFreq...Z_AVG" "frequencyBodyGyroscope.MEAN...X_AVG" "frequencyBodyGyroscope.MEAN...Y_AVG" "frequencyBodyGyroscope.MEAN...Z_AVG" "frequencyBodyGyroscope.MEANFreq...X_AVG" "frequencyBodyGyroscope.MEANFreq...Y_AVG" "frequencyBodyGyroscope.MEANFreq...Z_AVG" "frequencyBodyAccelerometerMagnitude.MEAN.._AVG" "frequencyBodyAccelerometerMagnitude.MEANFreq.._AVG" "frequencyBodyAccelerometerJerkMagnitude.MEAN.._AVG" "frequencyBodyAccelerometerJerkMagnitude.MEANFreq.._AVG" "frequencyBodyGyroscopeMagnitude.MEAN.._AVG" "frequencyBodyGyroscopeMagnitude.MEANFreq.._AVG" "frequencyBodyGyroscopeJerkMagnitude.MEAN.._AVG" "frequencyBodyGyroscopeJerkMagnitude.MEANFreq.._AVG"