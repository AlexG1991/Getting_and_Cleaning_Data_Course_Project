## Code Book for Getting and Cleaning Data Course Project

### Overview

[Source](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) of the original data:

	https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

[Full Description](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) at the site where the data was obtained:

	http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
	
### Process

The script `run_analysis.R` performs the following process to clean up the data
and create tiny data sets:

1. Merge the training and test sets to create one data set.

2. Reads `features.txt` and uses only the measurements on the mean and standard
   deviation for each measurement. 

3. Reads `activity_labels.txt` and applies readable activity names to
   name the activities in the data set.

4. Labels the data set with descriptive names

5. Merges the features with activity labels and subject IDs

6. The average of each measurement for each activity and each subject is merged
   to a second data set. The result is saved as `tidyData.txt`.

### Variables

- dataActivityTest - table contains of Y_test.txt
- dataActivityTrain - table contains of Y_train.txt
- dataSubjectTrain - table contains of subject_train.txt
- dataSubjectTrain - table contains of subject_test.txt
- dataFeaturesTest - table contains of X_test.txt
- dataFeaturesTrain - table contains of X_train.txt
- dataSubject - table contains the combination of tables dataSubjectTrain and dataSubjectTrain
- dataActivity - table contains the combination of tables dataActivityTest and dataActivityTrain
- dataFeatures - table contains the combination of tables dataFeaturesTrain and dataFeaturesTest
- dataFeaturesNames - table contains the Features names of dataFeatures
- dataCombine - table contains the combination of tables dataSubject and dataActivity
- Data - table contains the merge of tables dataCombine and dataFeatures with the respective Features names and column names
- Data2 - table contains the aggregate and the mean of subject and activity of Data


### Output

#### tidyData.txt

`tidyData.txt` is a 10299x68 data frame.

- The first column contains subject IDs.
- The second column contains activity names.
- The last 66 columns are measurements.
- Subject IDs are integers between 1 and 30.

#### tidyData2.txt

`tidyData2.txt` is a 180x68 data frame.

- The first column contains subject IDs.
- The second column contains activity names.
- The averages for each of the 66 attributes are in columns 3-68.
