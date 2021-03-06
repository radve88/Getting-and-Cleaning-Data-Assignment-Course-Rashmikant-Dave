---
title: "Assignment Getting and Cleaning Data"
author: Rashmikant Dave
date: May 16, 2016
output: github_document
html_preview: TRUE
---


This file desribes the usage,features and functionality of the run_analysis.R
file. It also explains how the code works and the flow of the steps it carries
out.

###   Functionality is given in the order processing is carried out by the script


All libraries required by the script are included by the script. The directories where download and unzip are done are unlinked by the script.

###   Download and Unzip of data

The script checks to see if the project folder "./data" is already present in the current working directory in case it is not a new folder gets created. The files are then copied to UCI HAR Dataset folder in the /data folder. The resultant tidyfile.txt is copied to the current working directory and not the ./data folder where only data is copied.                                                         

The script is meant to be automatic, it downloads the dataset files from the url given viz. "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip".


###   Data Frames 

The activity,subject and features files are read into variables

dataActivityTest  

dataActivityTrain 

dataSubjectTrain 

dataSubjectTest

dataFeaturesTest

dataFeaturesTrain 
The activity,subject and features files read using data.table are 

y_test.txt

y_train.txt

subject_train.txt

subject_test.txt

X_test.txt

X_train.txt

                                   

###  Variables created above for activity,subject and features are merged

The merge takes place in such a way that activity train and  test are merged with subject train and test which in turn are merged with features train and to give three variables of merged activity, subject and features


dataSubject 

dataActivity

dataFeatures



###  Set Column names of above created variables to facilitate a merge

For a merge to happen the column names need to be same or there needs to be a common key. The column names of the 3 datasets are changed so that the merge is made possible.

### Once Column names map with each other the variables created above are merged to give a combined dataframe

Dataframes with column names set dataSubject,dataActivity and dataFeatures are now merged to form a combined dataset called Data. Further details are given in CODEBOOK.MD

###  Means and Standard Deviation  extracted 


Subset name of Features by measurements on the mean and standard deviation and use these names to subset the data frame Data by names of Features.

                                                                 

###  Activity names made more readible and understandable

Activity names are made more descriptive and understandable.Also the dataset is now labelled with descriptive names Participant as they are  made more descriptive and understandable.More descriptive activity names replace the names of the activities in the data set.These are read  from ctivity_labels.txt.


Activity names are changed to below

1 WALKING

2 WALKING_UPSTAIRS

3 WALKING_DOWNSTAIRS

4 SITTING

5 STANDING

6 LAYING




^t" changed to "time" 

"^f" changed to "frequency"

"Acc" changed to "Accelerometer"

"Gyro" changed to "Gyroscope"

"Mag"changed to "Magnitude"

"BodyBody" changed to "Body"




###  Aggregating of Data by partiipant and acitivities to get Tidy data


Finally the dataset mean is grouped by participant and activities and saved to a file tidyfile.txt this gets created in the current working directory. This is a tidy form of data.

###  Usage
As described in the functionality the script takes care of most things automatically including copying downloaded and unzipped file is stored in the ./data/UCI HAR Dataset folder. Tidy files are saved in the current working diectory. 

