getting-and-cleaning-data-project
=================================
This repo contains project code for Getting and Cleaning Data course given by John Hopkins university on Coursera.

Script

The script contains a function run.analysis() that performs the actual job:

reads train and test data sets and merges them
processes the merged data set (extract the relevant variables, adds descriptive activity names, etc.)
writes the merged data set to rawdata.csv
generates the tidy data set
writes the tidy data set to tidydata.csv
returns the tidy data set

Included in this repo are:

run_analysis.R - the main script from producing the tidy data set
codebook.md - descibes the original dataset, the variables in the tidy data set and transformations used to obtain them
tidy_data.txt (not required but here in case of online submission problems)
run_analysis.R

I briefly go over the various steps in the run_analysis.R code in this section. See 'Mean and Std Feature Selection' and 'Style' for more justification on those topics.

Here are the various steps used by run_anlaysis.R to transform the original data into the tidy data set:

Read in the necessary text files from the original dataset and combine the train and test data into one data frame.
Extract the columns containing mean and standard deviation measurements, creating a smaller dataset. See the next section, Mean and Std Feature Selection for more information about which variables where extracted. Also, include the 'subject id' and 'activity label' variables in this new, smaller dataset.
Next, the activity measurements are converted from integers 1-6 to the actual activity they each represent. For example '1' is changed to 'WALKING'.
Next the remaining variables are renamed to have more readable and slightly more informative names. See the 'Style' section below for why I use the specific naming convention I do. The CodeBook document in this repo contains more specific information about this as well.
Finally, we about the average for each subject and activity over each of the extracted variables in the smaller data set, giving the final, tidy dataset, written as 'tidy_data.txt'. See the CodeBook document for more information about the final tidy dataset.
