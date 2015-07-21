# Introduction

What the `run_analysis.R` Script do.

 1. Read Training file from folder train
		 - X_train.txt, y_train.txt
 2. Read Subject Trainning subject_train.txt
 3. Read Test file from folder test
		 - X_test.txt, y_test.txt
 4. Read Subject  Test subject_test.txt
 5. Combine Training & Test file  (x,y file from folder Train and test
 6. Combine Subject for Training and test
    - subject_data <- rbind(subject_train, subject_test)
 7. Read table features.txt
 8. Get only mean and standard deviation
    - mean_and_std_features <- grep("-(mean|std)\\(\\)", features[, 2])
 9. Arrange by specific  column
    - x_data <- x_data[, mean_and_std_features]
    
10. Update column name in features.txt description
    - names(x_data) <- features[mean_and_std_features, 2]
11. Read activity label.
    - activities <- read.table("activity_labels.txt")
12. Match the activity witch correct activity name

13. Change column name for "activity" adn "subject"
    - names(y_data) <- "Activity"
    - names(subject_data) <- "Subject"
14. Combine all process to one variable
    - all_data <- cbind(x_data, y_data, subject_data)
15. Export tidy data to tidy_data.txt
    - write.table(tidy_data, "tidy_data.txt", row.name=FALSE)

