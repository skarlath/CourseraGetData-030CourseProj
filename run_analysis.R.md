
#Script for tidying up the data from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones




##First we read in the shared variable sets

```
##activities will store the activity id (act_id) and the activity name (activity)
activities <- read.table("activity_labels.txt", col.names = c("act_id","activity"), stringsAsFactors = FALSE)

##features will store the feature variable id (var_id) and the feature variable name (Feature_Variable)
features <- read.table("features.txt", col.names = c("var_id","Feature_Variable"), stringsAsFactors = FALSE)
```

###Next we read the Training Data

##We check the number of observations in the data set
TrainingRows <- nrow(read.table("train//subject_train.txt"))

##Load the subjects information
tr_subject <- read.table("train//subject_train.txt", row.names = paste("tr", seq(1, TrainingRows), sep="")
	, col.names = "Subject_ID", stringsAsFactors = FALSE)

##Load the bulk of the data
tr_X <- read.table("train//X_train.txt", row.names = paste("tr", seq(1, TrainingRows), sep=""), stringsAsFactors = FALSE)
##Assign the variable names
names(tr_X) <- features[["Feature_Variable"]]

##Load the activity label
tr_Y <- read.table("train//y_train.txt", row.names = paste("tr", seq(1, TrainingRows), sep=""), col.names = "Activity_ID", stringsAsFactors = FALSE)

##Merging the files into one data set
tr_XY <- merge( tr_X, tr_Y, by=0)
tr_XYSubj <- merge( tr_XY, tr_subject, by.x=1, by.y=0)
tr_FullMerged <- merge(tr_XYSubj, activities, by.x=563, by.y=1)

##Next we read the Test Data

##We check the number of observations in the data set
TestRows <- nrow(read.table("test//subject_test.txt"))

##Load the subjects information
tt_subject <- read.table("test//subject_test.txt", row.names = paste("tt", seq(1, TestRows), sep="")
	, col.names = "Subject_ID", stringsAsFactors = FALSE)

##Load the bulk of the data
tt_X <- read.table("test//X_test.txt", row.names = paste("tt", seq(1, TestRows), sep=""), stringsAsFactors = FALSE)
##Assign the variable names
names(tt_X) <- features[["Feature_Variable"]]

##Load the activity label
tt_Y <- read.table("test//y_test.txt", row.names = paste("tt", seq(1, TestRows), sep=""), col.names = "Activity_ID", stringsAsFactors = FALSE)


##Merging the files into one data set
tt_XY <- merge( tt_X, tt_Y, by=0)
tt_XYSubj <- merge( tt_XY, tt_subject, by.x=1, by.y=0)
tt_FullMerged <- merge(tt_XYSubj, activities, by.x=563, by.y=1)



##Combine the Test and Training data into one
allData <- rbind(tt_FullMerged, tr_FullMerged)

##find the columns that we're interested in (in this case Mean and STD Columns) 
##and append the Subject and Activity informational columns to our selection
colNames <- features$Feature_Variable[grep("mean\\(\\)|std\\(\\)", features$Feature_Variable)]
colNames <- c(colNames, "Subject_ID", "activity")

##apply our selection
relData <- subset(allData,select=colNames)

##Variable name cleanup
names(relData)<-gsub("Acc", "Accelerometer", names(relData))
names(relData)<-gsub("Gyro", "Gyroscope", names(relData))
names(relData)<-gsub("Mag", "Magnitude", names(relData))
names(relData)<-gsub("^t", "time", names(relData))
names(relData)<-gsub("^f", "frequency", names(relData))
names(relData)<-gsub("BodyBody", "Body", names(relData))


##Load plyr and preform the aggregate operations to get the mean for each Subject/Activity Pair
library(plyr)
aggData <- aggregate(. ~Subject_ID + activity, relData, mean)
aggData <- aggData[order(aggData$Subject_ID,aggData$activity),]

##Write it to a file for sharing
write.table(aggData, file = "tidyaggregatedata.txt", row.name=FALSE)

