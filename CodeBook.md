The run\_analysis.R script performs the data preparation, followed by
the 5 steps described in the course project’s description.

1. Download the dataset
=======================

-   The dataset was downloaded and extracted into a folder called UCI
    HAR Dataset

2. Assign each data to variables
================================

-   features &lt;- features.txt: *The features selected for this
    database come from the accelerometer and gyroscope 3-axial raw
    signals tAcc-XYZ and tGyro-XYZ.*
-   activities &lt;- activity\_labels.txt: *List of activities performed
    when the corresponding measurements were taken and its codes
    (labels)*
-   subject\_test &lt;- test/subject\_test.txt: *Contains test data of
    9/30 volunteer test subjects being observed*
-   x\_test &lt;- test/X\_test.txt: *Contains recorded features test
    data*
-   y\_test &lt;- test/y\_test.txt: *Contains test data of
    activities’code labels*
-   subject\_train &lt;- test/subject\_train.txt: *Contains train data
    of 21/30 volunteer subjects being observed*
-   x\_train &lt;- test/X\_train.txt: *Contains recorded features train
    data*
-   y\_train &lt;- test/y\_train.txt: *Contains train data of
    activities’ code labels*

3. Merges the training and the test sets to create one data set
===============================================================

-   X is created by merging x\_train and x\_test using the rbind()
    function
-   Y is created by merging y\_train and y\_test in the same way
-   Subject is created by merging subject\_train and subject\_test in
    the same way
-   MergedData is created by merging Subject, Y and X using cbind()
    function

4. Extracts only the measurements on the mean and standard deviation for each measurement
=========================================================================================

-   TidyData is created by subsetting MergedData, selecting only columns
    "subject, "code" and the measurements on the mean and standard
    deviation (std) for each measurement

5. Uses descriptive activity names to name the activities in the data set
=========================================================================

-   Integers in the code column of the TidyData are replaced with the
    corresponding activity taken from second column of the activities
    data frame

6. Appropriately labels the data set with descriptive variable names
====================================================================

Changed various aspects of the variable names to make them clearer and
easier to read, including: \* code column in TidyData renamed into
activities \* All Acc in column’s name replaced by Accelerometer \* All
Gyro in column’s name replaced by Gyroscope \* All BodyBody in column’s
name replaced by Body \* All Mag in column’s name replaced by Magnitude
\* All start with character f in column’s name replaced by Frequency \*
All start with character t in column’s name replaced by Time

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
================================================================================================================================================

-   TidyDataAvg is created by sumarising TidyData, taking the means of
    each variable for each activity and each subject after grouping by
    subject and activity.
-   Export TidyDataAvg into TidyDataAvg.txt file.
