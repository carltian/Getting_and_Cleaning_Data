what columns are measurements on the mean and standard deviation
Based on interpreting column names in the features is an open question as to is the the entries that include mean() and std() at the end, or does it include entries with mean in an earlier part of
the name as well. There are no specific marking criteria on the number of columns. It is up to you to make a decision and explain what you did to the data. Make it easy for people to give you marks
by explaining your reasoning.

Is descriptive activity names things like "Walking" and "Walking Up"
Yes, you need to get the activity numbers in the data and replace them with descriptive terms which are words. Now, a lot of people watch the merge lecture in week three, and decide to use it in a
"I am rushing through without checking each step kind of way" and fail to notice merge reorders the data (this is something you also might see in the week 3 quiz if you are paying attention). If
you have not yet clipped all your data together (because you are doing the steps out of order) this will mean the things you are clipping together will be in a different order. If you are doing
the steps in the set out order, you will never see this problem though. You can also apply the labels with subsetting. Another strategy is adjusting factor levels, or other even more exotic
techniques.

Is step 4 the same as step 3?
I am going to say no

Since it say labels the data set it is talking about the variable names (which at the moment are V1, V2, etc if you have be following the steps in there numbered order. Descriptive variable names
means names based on the action the variable is recording, for example the Jerk of the body on the z axis of the phone. In general, the more descriptive is going to be the better. once again make
it easy for your markers by noting why they are descriptive names (what they mean goes in the code book).

Is an average of a standard deviation even a thing?
Short answer. Doesn't matter, you are being asked to produce a average for each combination of subject, activity, and variable as a sign you can manipulate the data. Long answer, yes it is a thing.

Is it the first data set or the second we upload?
Up load the set created in step 5. This is an independent set of data created by taking the results of step 4 and making a new set of averaged data. Step 4 is internal to the script only.

Are you sure either the wide or narrow form of the data is tidy?
This question only makes sense when you have watched the reshaping lectures in week 3.

Yes. The wide or narrow form is tidy. The wording in the rubric has actually been clarified on this point to help people be clear in marking. Tidy data is one of the more important concepts in the
is course. Go back and read Hadley Wickham's Tidy Data paper (not that you have read this at the start of the course, but it is recommended reading in the lectures in both week one and week three
before the assignment is due). It talks about how the specific form of "tidy" depends on the problem being solved, and this problem permits two forms. I have my own elegant proof of this which the
margins do not have room for. If you want to bulletproof yourself on this point for the assignment, I am also going to start a similarly verbose thread about tidy data. And that gives you something
you can assert in your readMe citing the weblink to the discussion (hardly anyone cites things, but it is actually a brilliant plan). That, people, is how you make sure there is no ambiguity for
your markers. the Tidy data thread is at https://class.coursera.org/getdata-014/forum/thread?thread\_id=31

should the saved text file look that weird?
Tidy data is not made to be looked neatly at in programs like notepad (which is often the default for text files on windows), but if you saved the file with write.table according to the
instructions, the command for reading it in and looking at it in R would be

    data <- read.table(file_path, header = TRUE) #if they used some other way of saving the file than a default write.table, this step will be different
    View(data)
A person wanting to make life easy for their marker would give the code for reading the file back into R in the readMe. A person who varied the write.table settings should definitely help their
marker by giving the variant instructions for reading the file in. A person careful about ethically noting their sources might cite this thread (though that is a pretty minor bit of code). There
are fancier ways of reading the file in, like from a web address on the clipboard, but that is probably a topic for a stand lone thread if people were really curious, rather than extending this
thread.

wasn't there a Code Book?
Yes, and it is really important you include it. Go back to quiz 1 and look at the codebook there for inspiration. Be sure it goes on github with the analysis script and the readme. People have
lost major marks in previous sessions by having a brain-fade and forgetting about critical files so not getting the marks: you want a run_analysis R script, a ReadMe markdown document, a Codebook
markdown document, and a tidy data text file (this last goes on Coursera).

Feel free to start a thread about what a good codebook is.

Is anyone else seeing the y or subject data file as gibberish
You must be on Windows using notepad. Notepad is not a very clever text editor, and can only cope with basic Windows text encodings. Use Notepad++ as a high quality free Windows text editor (if
you want a good free Macintosh one I would suggest TextWrangler)

Should I decompose the variable names
No. For two reasons. One is that no-one ever does so correctly. The other is that you need to write a really excellent ReadMe and Codebook that makes it clear to your markers how what you've done
is tidy, and for reasons of the first part this is a problem. This is one of those ideas that is better in theory than in practice. People (possibly inspired by the tidyr swirl tutorial) go "I can
split the x,y, and z, and all the others into different columns". The trouble in practice is that you don't actually get clear one variable per column because the the entries in each column are not
independent, mutually exclusive, members of the same set. It is like seeing red, dark green, light green, pink, and blue as categories and thinking it is a good idea to make it tidier by putting
the light and dark in a separate column. You introduce a bunch of NA values for all the other entries, and introducing a bunch of NA values where there were not previous ones (or a functional
equivalent term like "other") is a pretty clear sign the data is a best no tidier (and is probably worse).

And Submit
This isn't a question, but there are two buttons at the bottom of the assignment "Save draft" and "Submit for grading". You have not submitted your assignment until you tick the honor code tickbox
and "Submit for grading". If you do not actually do this step you will miss out on all the marks for the assignment.

Have I ruined my data?
There are ways you can put the data together where it all goes wrong. All subjects should have done all activities. That is a pretty good rule of thumb. If you want to share an aggregate mean value
for a paritcular subject/activity/measurement combination, go right ahead. But the all subjects did all activities normally covers potential problems.

Why do I keep saying "make it easy for your markers"?
Because it is one of the basic principles of doing peer assignments for any course (not just this one). Most people want to give you marks, and if you actually explain about why your project meets
the requirements they will know you have thought about it and be happy to give you marks (even if you did the project differently to them).

Can I vigorously defend what I believe to be the one truly tidy arrangement of the data
Go right ahead. But please keep it to the discussion forums rather than carrying it into how you are marking (and please start another thread for that). This can be one of those times where people
overestimate their understanding of the structure of the data if you are certain of your opinion. I've been helping out in this course for a year and I think it is arguable. What we are marking for
is the data tidy- nicely categorised data so we can do an analysis easily- has it got headings that make it clear which column is which, is it one column per variable (though what the variables are
will be different in the long and wide form), is it one row per observation (though what the observations are will be different in the long and wide form). Tidy data is not a certain number of rows
and columns, if the question was looking for that, the rubric would specific it (that said, for example if their data left out entries because they didn't include the test data, the data set might
be tidy but the script itself would have a serious flaw).

My Link, it does nothing
For those who have not done assignments on Coursera before, when you load a file in it is stored as a link that is inactive during the submission phase. This becomes an active link in the marking
(evaluation) phase. If you want to test it during the submission phase you can Preview the assignment, or right-click on the inactive link and "Open in new window".

If you do every change an existing submission on Coursera, be a bit careful that you cleared out the old submission properly. If you select a link and paste over it, most web browsers will take
this as replacing the text of the link rather than the hyperlink of the link. Either completely clear out the old link before adding a new one, or use the link tool to control the hyperlink bit.

10votes received.==================================================================
Human Activity Recognition Using Smartphones Dataset
Version 1.0
==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
==================================================================

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

For each record it is provided:
======================================

- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

The dataset includes the following files:
=========================================

- 'README.txt'

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

Notes: 
======
- Features are normalized and bounded within [-1,1].
- Each feature vector is a row on the text file.

For more information about this dataset contact: activityrecognition@smartlab.ws

License:
========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.
