
Project: Getting and Cleaning Course Project
(Course #3 - Data Science Specialization by Johns Hopkins University)
Purpose: demonstrate ability to collect, work with, & clean a data set
Goal: prepare tidy data that can be used for later analysis

Requirements: 1) tidy data set created by run_analysis.R script such
                             that: A) each variable forms a column
                                      B) each observation forms a row
                                      C) each type of observational unit forms a table
                              (NOTE: steps done throughout run.analysis.R script             
                                          to tidy data in order to get final tidy data set)   
                         2)  link to Github repository with run_analysis.R script 
                              for performing analysis
                         3)  code book (CodeBook.md)) describing variables, 
                              data, & any transformations or work that was
                              performed to clean up the data
                         4) this README.md will only explain how run.analysis.R
                              works as it is the only one written for this project
                              (no explanation of scripts working together needed) 

Background on data in project:

NOTE: data collected from the accelerometers 
           from the Samsung Galaxy S smartphone

1) Data Set Information

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. (more details in ‘features.info.txt’ file)
2) Data Attribute Information
Each record in the dataset provides:
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope.
- A 561-feature vector with time and frequency domain variables.
- Its activity label.
- An identifier of the subject who carried out the experiment.

3) Data Set Files
    
    A) 'README.txt'
    B) 'features_info.txt': Shows information about variables used
        on feature vector
     C) 'features.txt': List of all features
     D) 'activity_labels.txt': Links class labels with their activity name
     E) 'train/X_train.txt': Training set
     F) 'train/y_train.txt': Training labels
     G) 'test/X_test.txt': Test set
     H) 'test/y_test.txt': Test labels

      NOTE: following files for train & test data – descriptions equivalent
       A) 'train/subject_train.txt': row identifies subject who
            performed activity for each sample - range 1 to 30. 
       B) 'train/Inertial Signals/total_acc_x_train.txt': acceleration signal
            from the smartphone accelerometer X axis in standard gravity
            units 'g' with every row showing 128 element vector
            (same description applies for 'total_acc_x_train.txt' & 
             'total_acc_z_train.txt' files for Y and Z axis) 

       C) 'train/Inertial Signals/body_acc_x_train.txt': body acceleration
             signal obtained by subtracting gravity from total acceleration. 
        D) 'train/Inertial Signals/body_gyro_x_train.txt': angular velocity
            vector measured by gyroscope for each sample
            (units are radians/second)


NOTE: no single piece of documentation exists explaining how
           different files relate to each other and how to combine them
            into a single data set for subsequent analysis. 

File content for each of 8 files shown below: 
File                                                           Description
------------------------------      ---------------------------------------------------------------------------------
activity_labels.txt       File: 6 rows X 2 columns

                                    columns – 1) code (values 1-> 6)
                                                     2) activity
                                                          A) walking
                                                          B) walking up stairs
                                                          C) walking downstairs
                                                          D) sitting
                                                          E) standing
                                                          F) laying 

features.txt                  File: 561 rows X 2 columns
       
                                      columns: - 1) count (1 -> 561)
                                                        2) body signals

subject_test.txt           File: 2947 rows X 1 column
                                   
                                      identifies subject (person) corresponding to 
                                      each row of data in X_test.txt file


File                                                           Description
------------------------------      ---------------------------------------------------------------------------------

X_test.txt                    File: 2947 rows X 561 columns

                                    measurements for each observed experiment
                                    on one of the six activities for a specific person

y_test.txt                     File: 2947 rows X 1 column

                                     containing one column of data that 
                                     identifies activity corresponding to each 
                                     row of data in test measurement X_test.txt file.

subject_train.txt          File: 7352 rows X 1 column

                                     identifies subject (person) corresponding 
                                     to each row of data in test measurement 
                                     X_train.txt file.   

X_train.txt                   File: 7352 rows X 1 column

                                     measurements for each observed experiment 
                                     on one of the six activities for specific person.

y_train.txt                    File: 7352 rows X 1 column
                       
                                    containing one column of data that 
                                    identifies activity corresponding to each 
                                    row of data in test measurement X_train.txt file.

File Analysis:
NOTE: column heading named for data sets for clarity

1) x data - combine x_test & x_train by rows
2) y data - combine y_test & y_train by rows
3) subject data - combine subject_test & subject_train by rows
4) merged data – combine x data, y data & subject data by columns



subject_test.txt           File containing one column of data that 
                                     identifies the subject (i.e. person) 
                                     corresponding to each row of data in the test 
                                     measurement X_test.txt file.


run.analysis.R script steps:

1) read data files for project
2) appropriately label data set with descriptive variable names
3) combine & merge training & test sets to create a data set
4) extracts only measurements of mean & standard deviation 
    for each measurement
5) uses descriptive activity names to name activities in data set
6) from data set created prior, create 2nd independent tidy
    data set with average of each variable for each activity & subject

    




README:  Getting and Cleaning Data Course Project

