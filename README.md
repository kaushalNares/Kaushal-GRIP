#importing the libraries
install.packages("tidyverse")
install.packages("here")
install.packages("janitor")
install.packages("dplyr")
install.packages("ggplot")

# calling the librarires
library(tidyverse)
library(here)
library(janitor)
library(ggplot2)
library(dplyr)

#importing the data from url
studentRecord <- read.csv("https://raw.githubusercontent.com/AdiPersonalWorks/Random/master/student_scores%20-%20student_scores.csv")

#Display the columns and first several rows
head(studentRecord)

#Structure of the table
str(studentRecord)

#
glimpse(studentRecord)

#Starting with the linear regession 
slr <- lm(Scores~Hours, data = studentRecord) 
summary(slr)

#visualizing the linear regression
plot(studentRecord)
abline(slr,col="red")

#display summary of linear regression
summary(slr)

#prediction of score
percentage <- data.frame(Hours=9.25)
prediction <- predict(slr,percentage)
prediction

#Code finish
