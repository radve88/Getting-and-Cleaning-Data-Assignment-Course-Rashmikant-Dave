### Student Name and Email
Rashmikant Dave
rashmikant.dave@gmail.com 


###  Codebook for Assignment Getting and Cleaning Data 

The data pertains to experiments carried out for Human Activity Recognition Using Smartphones.
This codebook shows the variables, the data, that was taken as a starting point and the transformations that were performed to clean up the data.

###  Data and Information Source

    Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
    Original description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones


###  Data Set Information

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, 3-axial linear acceleration and 3-axial angular velocity were capturedat a constant rate of 50Hz. The experiments had been video-recorded to label the data manually. The obtained dataset had been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force was assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

###  Data Source 

Jorge L. Reyes-Ortiz(1,2), Davide Anguita(1), Alessandro Ghio(1), Luca Oneto(1) and Xavier Parra(2)
1 - Smartlab - Non-Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova, Genoa (I-16145), Italy.
2 - CETpD - Technical Research Centre for Dependency Care and Autonomous Living
Universitat Politècnica de Catalunya (BarcelonaTech). Vilanova i la Geltrú (08800), Spain
activityrecognition '@' smartlab.ws


### Citation Requests as mentioned in the data description to be sent to

Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. A Public Domain Dataset for Human Activity Recognition Using Smartphones. 21th European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning, ESANN 2013. Bruges, Belgium 24-26 April 2013.



### Data Transformations done by run_analysis.R

The activity,subject and features files are read into variables 

dataActivityTest

dataActivityTrain 

dataSubjectTrain 

dataSubjectTest 

dataFeaturesTest 

dataFeaturesTrain

Activity test and train dataframes are merged, subject train and test are merged
and features train and test are merged to give three variables
and the Variables created are dataSubject,dataActivity and dataFeatures

Set Column names of above created variables to facilitate a merge once Column names map with each other the variables created above are merged to give a combined dataframe called Data.First dataSubject and dataActivity are combined to give a dataframe dataCombine then  dataFeature is combined with dataCombine to give Data the merged dataframe.From Data mean and standard deviation terms are extracted 

Activity names are made more descriptive and understandable.Also the dataset is now labelled with descriptive names. Participant is made more descriptive and understandable as descriptive activity names are used to name the activities, in the data set. Descriptive activity names are read from activity_labels.txt.

Aggregate Data dataframe by partiipant and acitivities to get Tidy data saved to a file called tidyfile.txt.


