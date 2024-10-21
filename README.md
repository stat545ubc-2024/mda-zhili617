[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/SCrOVOnU)

# Mini Data Analysis Project

## STAT 545 UBC (2024 Winter 1) -- Zhili Jiang

### Content 

1. [Overview](#overview)
  
2. [File Directory Description](#file-directory-description)
  
3. [How to Engage with the Repository](#how-to-engage-with-the-repository)
  
4. [Research Question](#research-question)
  

### Overview 
Welcome to my mini data analysis project of course STAT 545. 

This project will be completed by 2 milestones. In the first milestone, I analyzed the Steam Games dataset to explore the impact of NA values on numerical variables by using the dplyr and ggplots2 packages. The usage of techniques includes visualization, data summary, and analysis. Now I've finished the first milestone, and I have achieved the following goals:

- [x] Become familiar with a data set of choosing (**steam_games**).
- [x] Select 4 questions out of 8 and use the chosen dataset to answer.
- [x] Generate a reproducible and clear report using R Markdown.
- [x] Become familiar with manipulating and summarizing your data in tibbles using dplyr.


In the second milestone, I continued to study the research questions raised in the last milestone in the Steam games dataset. Through tidy and untidy exercises, I found a dataset that is more suitable for the research question. In addition, I also briefly practiced fitting models and reading and writing data. Now I've finished the second milestone, and I have achieved the following goals:

- [x] Understand what tidy data is, and be able to create it using tidyr.
- [x] Generate a reproducible and clear report using R Markdown.
- [x] Fitting a model object to my data, and extract a result.
- [x] Reading and writing data as separate files.



### File Directory Description

#### **README.md**: Provide distinctions for this project and instructions.


#### **Mini_Data_Milestone_1**


* **Mini_Data_Analysis_Deliverable_1.Rmd**: The file contains the code and analysis for the first milestone.

* **Mini_Data_Analysis_Deliverable_1.md**: The knitted output of *Mini_Data_Analysis_Deliverable_1.Rmd*.

* **Mini_Data_Analysis_Deliverable_1_files/figure-gfm**: All images for *Mini_Data_Analysis_Deliverable_1.md*.

* **README.md**: Explaining what is in the **Mini_Data_Milestone_1**.

#### **Mini_Data_Milestone_2**

* **Mini Data Analysis Milestone 2.Rmd**: The file contains the code and analysis for the second milestone.

* **Mini-Data-Analysis-Milestone-2.md**: The knitted output of **Mini Data Analysis Milestone 2.Rmd**.

* **Mini-Data-Analysis-Milestone-2_files** : All images for **Mini-Data-Analysis-Milestone-2.md**.

* **README.md**: Explaining what is in the **Mini_Data_Milestone_2**.


#### **output**
The folder contains CSV files with summary tables in Task 1 of milestone 2 and RDS files for saved model objects.

* **discount_original.csv**: Group Steam games by types, categorize both original_price and discount_price into five levels each (very low, low, moderate, high, very high), providing a joint distribution analysis of original and discount prices across game types.

* **discount_types.csv**: Summarizes the mean, minimum, maximum, and standard deviation of discount prices across different Steam game types.

* **missing_discounts.csv**: Group Steam games by type and count the number of missing values and non-missing values for different types.

* **original_type.csv**: Select three variables (types, discount_price, and original_price), Group Steam games by types, and categorize the original_price into five levels (very low, low, moderate, high, very high). 

* **model.rds**: A linear regression model that indicates a relationship between the original price and discount price.

* **README.md**: Explaining what is in the **output**.


### How to Engage with the Repository

To engage with the repository:

1. installing the following package for view the data set:
```R     
install.packages("devtools")
devtools::install_github("UBC-MDS/datateachr")
 ```
      
2. Loading the relevant libraries:

```R     
library(datateachr)
library(tidyverse)
library(broom)
library(here)
```
> If unable to load these Four libraries, try to install it first by using 

```R
 install.packages("your-package-name")
 ```

3. Download the .rmd file and run it in R/Rstudio. 

[View details](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

> If you don't want to look at codes, you can also look at the .md file to view all the details.

### Research Question

* Milestone 1 : 

      What is the impact of missing values (NA) on the analysis of numerical variables in the Steam game dataset?

* Milestone 2 :  
                              
      1. How are games from different types or publishers discounted?

      2. How are games with different original_price ranges distributed across types? 
                              
      3. How do missing values impact the analysis of discount_price in Steam games?
                              
      4. How do original_price and discount_price relate to each other?
