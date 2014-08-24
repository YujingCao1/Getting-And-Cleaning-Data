#Code Book
##Data Source and Information
This dataset is derived from the “Human Activity Recognition Using Smartphones Data Set”.
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

##Signals
The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. 
The set of variables that were estimated from these signals are:
mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.
All the features are normalized and bounded within [-1,1].

##Data Transformation
The whole data sets are processed in run_analysis.R script to create a tidy dataset.

##Merging Train and Test data sets
After setting the working directory, import all the following  tables which data is located in:
features.txt
activity_labels.txt
subject_train.txt
x_train.txt
y_train.txt
subject_test.txt
x_test.txt
y_test.txt
Merge all the tables but feature.txt to get a single dataset, then assign variable names with feature.txt

##Extract Mean and Standard Deviation Variables
create a logical vector which contains true values for ID,mean and std columns and false values for others. Then get a subset that just contains the columns we want based on the logical vector we got.

##Using Descriptive Names
merge sub_data with activitylabels to obtain descriptive activity names

##Labels Variables Appropriately
Change the labels which are given in the features.txt: remove parentheses, dash to make some descriptive names.

##Create a Tidy dataset
Due to the project requirements, finally we get a tidydata.txt with the average of each variable for each activity and subject.