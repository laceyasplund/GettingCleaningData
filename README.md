# Getting and Cleaning Data Project
The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. You will be graded by your peers on a series of yes/no questions related to the project. You will be required to submit: 1) a tidy data set as described below, 2) a link to a Github repository with your script for performing the analysis, and 3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.

One of the most exciting areas in all of data science right now is wearable computing - see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Here are the data for the project:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

You should create one R script called run_analysis.R that does the following.

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names.
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. Good luck!

#run_analysis.R

## Generate Dataset

This will download the appropriate data, merge the training and test sets, extract the measurements on mean and standard deviation, name the activities, rename column labels to be more user friendly, and lastly create a new tidy dataset with the averages of each activity, variable, and subject.

source("run_analysis.R")

This will download the required package (plyr) and the required data from (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) and store it in a zip file called data.zip, After this a new folder will be generated (results/) containing the two datasets.

dataset1.txt - 10299 rows and 81 cols
TidyData.txt - 180 rows and 81 cols

##Included dataset

The data is located in the results folder  dataset1 <- write.table("results/dataset1.txt") TidyData <- write.table("results/TidyData.txt") 