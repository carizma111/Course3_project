
# How the code works
The code is broken down to 8 steps to prepare a final tidy data set.
1. Load and unzip the dataset
•	Loads libraries required to use specific functions
•	Downloads the zip file from the URL
•	Unzips files on your machine
2. Reading activity and features data
•	Reads activity labels data to a variable “activityLabels”
•	Changes the datatype of column 2 for “activityLabels” to a character
•	Adds column names to “activityLabels”
•	Reads features data to a variable “features”
•	Changes the datatype of column 2 for “features” to a character
3. Extract only mean and standard deviation from features data
•	Matches the feature names with mean/std dev and stores the first column as an integer vector in the variable “featuresreq”
•	Stores only the features names where the pattern matched in a separate variable called “featuresreq.names” 
•	Format feature names using gsub
4. Load the training datasets
•	Load X_train data set
•	Select only columns where the indices matched with indices in “featuresreq” as these are the columns containing mean and std dev measurements
•	Load Y_train data set
•	Load subject_train data set
•	Column bind all above datasets in “train”
5. Load the test data sets
•	Load X_test data set
•	Select only columns where the indices matched with indices in “featuresreq” as these are the columns containing mean and std dev measurements
•	Load Y_test data set
•	Load subject_test data set
•	Column bind all above datasets in “test”
6. Merge and add labels data 
•	Row bind test and train data set into one variable “consol_data”
•	Add labels to all columns
 7. Fetching activity description from activity labels and ordering columns
•	Left join with “activityLabels” to fetch activity_description
•	Order columns using “select”
•	Convert activity_description as a factor
8. Create independent tidy data set
•	Group data by subject and activity_description
•	Summarize all columns to calculate mean () for the grouped data set above
•	Export grouped and summarized data set to “tidy” text file.
