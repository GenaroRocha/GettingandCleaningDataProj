With this CodeBook we describe the transformations made to follow the instructions from the project:
Step 1: Download the dataset
Dataset downloaded and extracted under a folder called UCI HAR Dataset
Step 2: Assign all data to variables
features <- features.txt | 561 rows, 2 columns
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
activities <- activity_labels.txt | 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken
subject_test <- test/subject_test.txt | 2947 rows, 1 column
Test data of 9/30 volunteer test subjects observed
x_test <- test/X_test.txt | 2947 rows, 561 columns
Recorded features test data
y_test <- test/y_test.txt | 2947 rows, 1 columns
Test data of activities code labels
subject_train <- test/subject_train.txt | 7352 rows, 1 column
Train data of 21/30 volunteer subjects observed
x_train <- test/X_train.txt | 7352 rows, 561 columns
Recorded features train data
y_train <- test/y_train.txt | 7352 rows, 1 columns
Train data of activities’code labels
Step 3: Merges the training and the test sets to create one data set
X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind()
Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind()
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind()
Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind()
Step 4: Extract the measurements on the mean and standard deviation
TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data
with only the columns subject, code and the measurement on the mean and standard deviation for each measurement
Step 5: Rename activities inthe data set using descriptive activities
Numbers in code column of the TidyData replaced with corresponding activity taken from second column of the activities variable
Step 6: Label the data set with descriptive variable names
code column in TidyData renamed into activities
Acc in column’s name replaced by Accelerometer
Gyro in column’s name replaced by Gyroscope
BodyBody in column’s name replaced by Body
Mag in column’s name replaced by Magnitude
Beggining with character f in column’s name replaced by Frequency
Beggining with character t in column’s name replaced by Time
Step 7: create a tidy data set with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns), created by sumarizing TidyData taking the mean of each variable for each activity and each subject, then 
export FinalData into FinalData.txt file.
