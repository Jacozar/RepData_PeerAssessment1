---
title: "Reproducible Research: Peer Assessment 1"
author: "JOSE ANTONIO COZAR RIOS"
output: 
  html_document:
    keep_md: true
---

## Introduction
This assignment makes use of data from a personal activity monitoring device. This device collects data at 5 minute intervals through out the day. The data consists of two months of data from an anonymous individual collected during the months of October and November, 2012 and include the number of steps taken in 5 minute intervals each day. The data for this assignment are in the working directory.

## Loading and preprocessing the data
Firts we Unzip the file **activity.zip** in the working directory and read the **activity.csv** like a dataframe.

```r
# Asume that the activity.zip file is in the working directory and load the activity.csv in the data frame DFactivity
unzip('activity.zip', overwrite = TRUE)
DFactivity<-read.csv('activity.csv',header=TRUE,na.strings = 'NA')
```
The variables included in this dataframe are:

- **steps**: Number of steps taking in a 5-minute interval (missing values are coded as NA).
- **date**: The date on which the measurement was taken in YYYY-MM-DD format.
- **interval**: Identifier for the 5-minute interval in which measurement was taken.

We can see a sample of datas with the *head()* R function:

```r
head(DFactivity)
```

```
##   steps       date interval
## 1    NA 2012-10-01        0
## 2    NA 2012-10-01        5
## 3    NA 2012-10-01       10
## 4    NA 2012-10-01       15
## 5    NA 2012-10-01       20
## 6    NA 2012-10-01       25
```
Now we will transform the variable **date** from data frame in a date class.

```r
DFactivity$date<-as.Date(DFactivity$date)
```

## What is mean total number of steps taken per day?
In this part first we will remove the missing values (NA) with the help *complete.cases()* R function. We will save the result in a new data frame named **DFactivity_complete**.

```r
DFactivity_complete <- DFactivity[complete.cases(DFactivity), ]
```
Now we can see in the new data frame **DFactivity_complete** only the complete datas.

```r
head(DFactivity_complete)
```

```
##     steps       date interval
## 289     0 2012-10-02        0
## 290     0 2012-10-02        5
## 291     0 2012-10-02       10
## 292     0 2012-10-02       15
## 293     0 2012-10-02       20
## 294     0 2012-10-02       25
```




## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
