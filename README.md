# CourseraGetData-030CourseProj
Course Project For GetData-030

To run the script:

```R
##Ensure that the working directory contains the following before running:
##activity_labels.txt
##features.txt
##test (folder)
##		subject_test.txt
##		X_test.txt
##		y_test.txt
##train (folder)
##		subject_train.txt
##		X_train.txt
##		y_train.txt
source("run_analysis.R")
```

###Note that the zip file unpacks to the correct directory structure


```R
##Output file tidyaggregatedata.txt
```

##Output File info:
###180 observations of 68 variables
Dataset Columns (variables)

 $ Subject_ID                                    : int  "The subject ID as part of the study"
 $ activity                                      : chr  "The activity during which the measurements were collected"
 $ timeBodyAccelerometer-mean()-X                : num  "Data Variables"
 $ timeBodyAccelerometer-mean()-Y                : num  
 $ timeBodyAccelerometer-mean()-Z                : num  
 $ timeBodyAccelerometer-std()-X                 : num  
 $ timeBodyAccelerometer-std()-Y                 : num  
 $ timeBodyAccelerometer-std()-Z                 : num  
 $ timeGravityAccelerometer-mean()-X             : num  
 $ timeGravityAccelerometer-mean()-Y             : num  
 $ timeGravityAccelerometer-mean()-Z             : num  
 $ timeGravityAccelerometer-std()-X              : num  
 $ timeGravityAccelerometer-std()-Y              : num  
 $ timeGravityAccelerometer-std()-Z              : num  
 $ timeBodyAccelerometerJerk-mean()-X            : num  
 $ timeBodyAccelerometerJerk-mean()-Y            : num  
 $ timeBodyAccelerometerJerk-mean()-Z            : num  
 $ timeBodyAccelerometerJerk-std()-X             : num  
 $ timeBodyAccelerometerJerk-std()-Y             : num  
 $ timeBodyAccelerometerJerk-std()-Z             : num  
 $ timeBodyGyroscope-mean()-X                    : num  
 $ timeBodyGyroscope-mean()-Y                    : num  
 $ timeBodyGyroscope-mean()-Z                    : num  
 $ timeBodyGyroscope-std()-X                     : num  
 $ timeBodyGyroscope-std()-Y                     : num  
 $ timeBodyGyroscope-std()-Z                     : num  
 $ timeBodyGyroscopeJerk-mean()-X                : num  
 $ timeBodyGyroscopeJerk-mean()-Y                : num  
 $ timeBodyGyroscopeJerk-mean()-Z                : num  
 $ timeBodyGyroscopeJerk-std()-X                 : num  
 $ timeBodyGyroscopeJerk-std()-Y                 : num  
 $ timeBodyGyroscopeJerk-std()-Z                 : num  
 $ timeBodyAccelerometerMagnitude-mean()         : num  
 $ timeBodyAccelerometerMagnitude-std()          : num  
 $ timeGravityAccelerometerMagnitude-mean()      : num  
 $ timeGravityAccelerometerMagnitude-std()       : num  
 $ timeBodyAccelerometerJerkMagnitude-mean()     : num  
 $ timeBodyAccelerometerJerkMagnitude-std()      : num  
 $ timeBodyGyroscopeMagnitude-mean()             : num  
 $ timeBodyGyroscopeMagnitude-std()              : num  
 $ timeBodyGyroscopeJerkMagnitude-mean()         : num  
 $ timeBodyGyroscopeJerkMagnitude-std()          : num  
 $ frequencyBodyAccelerometer-mean()-X           : num  
 $ frequencyBodyAccelerometer-mean()-Y           : num  
 $ frequencyBodyAccelerometer-mean()-Z           : num  
 $ frequencyBodyAccelerometer-std()-X            : num  
 $ frequencyBodyAccelerometer-std()-Y            : num  
 $ frequencyBodyAccelerometer-std()-Z            : num  
 $ frequencyBodyAccelerometerJerk-mean()-X       : num  
 $ frequencyBodyAccelerometerJerk-mean()-Y       : num  
 $ frequencyBodyAccelerometerJerk-mean()-Z       : num  
 $ frequencyBodyAccelerometerJerk-std()-X        : num  
 $ frequencyBodyAccelerometerJerk-std()-Y        : num  
 $ frequencyBodyAccelerometerJerk-std()-Z        : num  
 $ frequencyBodyGyroscope-mean()-X               : num  
 $ frequencyBodyGyroscope-mean()-Y               : num  
 $ frequencyBodyGyroscope-mean()-Z               : num  
 $ frequencyBodyGyroscope-std()-X                : num  
 $ frequencyBodyGyroscope-std()-Y                : num  
 $ frequencyBodyGyroscope-std()-Z                : num  
 $ frequencyBodyAccelerometerMagnitude-mean()    : num  
 $ frequencyBodyAccelerometerMagnitude-std()     : num  
 $ frequencyBodyAccelerometerJerkMagnitude-mean(): num  
 $ frequencyBodyAccelerometerJerkMagnitude-std() : num  
 $ frequencyBodyGyroscopeMagnitude-mean()        : num  
 $ frequencyBodyGyroscopeMagnitude-std()         : num  
 $ frequencyBodyGyroscopeJerkMagnitude-mean()    : num  
 $ frequencyBodyGyroscopeJerkMagnitude-std()     : num  

##Column Naaming information
###time prefix denotes time domain signals
###frequency prefix denotes frequency domain signals
###Gravity denotes derived gravitational acceleration signals
###Body denotes derived body acceleration signals
###Body Linear acceleration and body angular velocity were derived in time to obtain Jerk signals
###XYZ variables are calculated from the signal vectors
###mean denotes Mean Value
###std denotes Standard deviation


