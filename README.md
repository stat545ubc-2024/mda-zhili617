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


### File Directory Description

* **README.md**: Provide distinctions for this project and instructions.

* **Mini_Data_Analysis_Deliverable_1.Rmd**: The file contains the code and analysis for the first milestone.

* **Mini_Data_Analysis_Deliverable_1.md**: The knitted output of *Mini_Data_Analysis_Deliverable_1.Rmd*.

* **Mini_Data_Analysis_Deliverable_1_files**: All images for *Mini_Data_Analysis_Deliverable_1.md*.



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
```
> If unable to load these two libraries, try to install it first by using 

```R
 install.packages("your-package-name")
 ```

3. Download the .rmd file and run it in R/Rstudio. 

[View details](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository)

> If you don't want to look at codes, you can also look at the .md file to view all the details.

### Research Question

* Milestone 1 : 

      What is the impact of missing values (NA) on the analysis of numerical variables in the Steam game dataset?

* Prepared for Milestone 2 :  
                              
      1. How are games from different types or publishers discounted?

      2. How are games with different original_price ranges distributed across types? 
                              
      3. How do missing values impact the analysis of discount_price in Steam games?
                              
      4. How do original_price and discount_price relate to each other?
