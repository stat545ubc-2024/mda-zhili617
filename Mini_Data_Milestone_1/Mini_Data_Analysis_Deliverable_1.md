Mini Data-Analysis Deliverable 1
================

# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let’s get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr)
    package by typing the following into your **R terminal**:

<!-- -->

    install.packages("devtools")
    devtools::install_github("UBC-MDS/datateachr")

2.  Load the packages below.

``` r
library(datateachr)
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   3.5.1     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.1
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

3.  Make a repository in the <https://github.com/stat545ubc-2024>
    Organization. You can do this by following the steps found on canvas
    in the entry called [MDA: Create a
    repository](https://canvas.ubc.ca/courses/158528/pages/mda-create-a-repository).
    One completed, your repository should automatically be listed as
    part of the stat545ubc-2024 Organization.

# Instructions

## For Both Milestones

-   Each milestone has explicit tasks. Tasks that are more challenging
    will often be allocated more points.

-   Each milestone will be also graded for reproducibility, cleanliness,
    and coherence of the overall Github submission.

-   While the two milestones will be submitted as independent
    deliverables, the analysis itself is a continuum - think of it as
    two chapters to a story. Each chapter, or in this case, portion of
    your analysis, should be easily followed through by someone
    unfamiliar with the content.
    [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R.html)
    is a good resource for what constitutes “good code”. Learning good
    coding practices early in your career will save you hassle later on!

-   The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd`
file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd)
directly. Fill in the sections that are tagged with
`<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an
`.md` file by changing the YAML output settings from
`output: html_document` to `output: github_document`. Commit and push
all of your work to the mini-analysis GitHub repository you made
earlier, and tag a release on GitHub. Then, submit a link to your tagged
release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and
6 for overall reproducibility, cleanliness, and coherence of the Github
submission.

# Learning Objectives

By the end of this milestone, you should:

-   Become familiar with your dataset of choosing
-   Select 4 questions that you would like to answer with your data
-   Generate a reproducible and clear report using R Markdown
-   Become familiar with manipulating and summarizing your data in
    tibbles using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently
composed of 7 semi-tidy datasets for educational purposes. Here is a
brief description of each dataset:

-   *apt_buildings*: Acquired courtesy of The City of Toronto’s Open
    Data Portal. It currently has 3455 rows and 37 columns.

-   *building_permits*: Acquired courtesy of The City of Vancouver’s
    Open Data Portal. It currently has 20680 rows and 14 columns.

-   *cancer_sample*: Acquired courtesy of UCI Machine Learning
    Repository. It currently has 569 rows and 32 columns.

-   *flow_sample*: Acquired courtesy of The Government of Canada’s
    Historical Hydrometric Database. It currently has 218 rows and 7
    columns.

-   *parking_meters*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 10032 rows and 22 columns.

-   *steam_games*: Acquired courtesy of Kaggle. It currently has 40833
    rows and 21 columns.

-   *vancouver_trees*: Acquired courtesy of The City of Vancouver’s Open
    Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

-   We hope that this project will serve as practice for carrying our
    your own *independent* data analysis. Remember to comment your code,
    be explicit about what you are doing, and write notes in this
    markdown document when you feel that context is required. As you
    advance in the project, prompts and hints to do this will be
    diminished - it’ll be up to you!

-   Before choosing a dataset, you should always keep in mind **your
    goal**, or in other ways, *what you wish to achieve with this data*.
    This mini data-analysis project focuses on *data wrangling*,
    *tidying*, and *visualization*. In short, it’s a way for you to get
    your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr`
package, choose **4** that appeal to you based on their description.
Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package,
but if you have a dataset that you’d really like to use, you can include
it here. But, please check with a member of the teaching team to see
whether the dataset is of appropriate complexity. Also, include a
**brief** description of the dataset here to help the teaching team
understand your data.

<!-------------------------- Start your work below ---------------------------->

1: **apt_buildings** : This dataset contains the apartment building
information for buildings in Toronto that are registered in the
Apartment Building Standard (ABS) program.

2: **parking_meters** : This dataset contains information on the rates
and time limits for parking meters in Vancouver. Information is shown
for entire block faces rather than for individual meters.

3: **vancouver_trees**: This dataset contains the information public
trees in the City of Vancouver,

4: **steam_games** : This dataset contains games from steam shop.

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to
*explore* the datasets. Use your knowledge of dplyr to find out at least
*3* attributes about each of these datasets (an attribute is something
such as number of rows, variables, class type…). The goal here is to
have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the
cleanliness of your analysis. I added a single code chunk for you below,
but do you want to use more than one? Would you like to write more
comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

``` r
apt_buildings_attributes <- apt_buildings%>% #pass the dataset apt_buildings into reframe() function
                            reframe( #Collapses a group of information into a single row
                              data_name = "Apartment Buildings", # Assigns a new character string "Apartment Buildings" to the column named data_name
                              row_number = nrow(.), # Assigns the number of rows from dataset apt_buildings to the column named row_number
                              variable_number = ncol(.), # Assigns the number of variable from dataset apt_buildings to the column named variable_number
                              variable_name = colnames(.), # Assign variables' name from dataset to the column named variable_name
                              variable_type = sapply(., class), # Assign variables' class from dataset to the column named variable_name
                              miss_value = colSums(is.na(.))) #Assign missing value of each variable from dataset to the column named miss_value


#Because the remaining three sets of code have almost the same content with the above one, only the dataset is modified, so I only explained the above one.

parking_meters_attributes <- parking_meters%>%
                            reframe( data_name = "Parking Meters",
                                       row_number = nrow(.), 
                                       variable_number = ncol(.),
                                       variable_name = colnames(.),
                                       variable_type = sapply(., class),
                                       miss_value = colSums(is.na(.)))


vancouver_trees_attributes <- vancouver_trees%>%
                            reframe( data_name = "Vancouver Trees",
                                       row_number = nrow(.), 
                                       variable_number = ncol(.),
                                       variable_name = colnames(.),
                                       variable_type = sapply(., class),
                                       miss_value = colSums(is.na(.)))


steam_games_attributes <- steam_games%>%
                            reframe( 
                              data_name = "Steam Games",
                              row_number = nrow(.), 
                              variable_number = ncol(.),
                              variable_name = colnames(.),
                              variable_type = sapply(., class),
                              miss_value = colSums(is.na(.)))


bind_rows(apt_buildings_attributes, parking_meters_attributes, vancouver_trees_attributes,steam_games_attributes ) #Combine the four data frames containing attributes of different datasets into one.
```

    ## # A tibble: 100 × 6
    ##    data_name   row_number variable_number variable_name variable_type miss_value
    ##    <chr>            <int>           <int> <chr>         <chr>              <dbl>
    ##  1 Apartment …       3455              37 id            numeric                0
    ##  2 Apartment …       3455              37 air_conditio… character             85
    ##  3 Apartment …       3455              37 amenities     character           2518
    ##  4 Apartment …       3455              37 balconies     character             88
    ##  5 Apartment …       3455              37 barrier_free… character             82
    ##  6 Apartment …       3455              37 bike_parking  character              0
    ##  7 Apartment …       3455              37 exterior_fir… character             95
    ##  8 Apartment …       3455              37 fire_alarm    character             87
    ##  9 Apartment …       3455              37 garbage_chut… character             83
    ## 10 Apartment …       3455              37 heating_type  character             86
    ## # ℹ 90 more rows

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you’ve explored the 4 datasets that you were
initially most interested in, let’s narrow it down to 1. What lead you
to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

I’d like to choose **steam_games**. First of all, this dataset focuses
on games available on Steam. As an active player on the platform, I have
a personal interest in this content. Secondly, from the survey conducted
in the previous question, I discovered that this dataset contains a
relatively high number of missing values. I want to explore the impact
of these missing values on the overall dataset. Finally, the dataset has
a moderate number of variables and rows, which makes it more
representative and manageable for analysis.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the
beginning, it’s important to have an *end goal* in mind. For example, if
I had chosen the `titanic` dataset for my project, I might’ve wanted to
explore the relationship between survival and other variables. Try to
think of 1 research question that you would want to answer with your
dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

What is the impact of missing values (NA) on the analysis of numerical
variables in the Steam game dataset?
<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them.
Probably also a good point to grab a coffee to get ready for the fun
part!

This project is semi-guided, but meant to be *independent*. For this
reason, you will complete tasks 2 and 3 below (under the **START HERE**
mark) as if you were writing your own exploratory data analysis report,
and this guidance never existed! Feel free to add a brief introduction
section to your project, format the document with markdown syntax as you
deem appropriate, and structure the analysis as you deem appropriate. If
you feel lost, you can find a sample data analysis
[here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a
better idea. However, bear in mind that it is **just an example** and
you will not be required to have that level of complexity in your
project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you’ll see that by
the end of this deliverable, you should have formulated *4* research
questions about your data that you may want to answer during your
project. However, it may be handy to do some more exploration on your
dataset of choice before creating these questions - by looking at the
data, you may get more ideas. **Before you start this task, read all
instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to
dive deeper into your data. All datasets are different and therefore,
not all of these tasks may make sense for your data - which is why you
should only answer *4*.

Make sure that you’re using dplyr and ggplot2 rather than base R for
this task. Outside of this project, you may find that you prefer using
base R functions for certain tasks, and that’s just fine! But part of
this project is for you to practice the tools we learned in class, which
is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.

``` r
numeric_variables <- steam_games %>%
  select(where(is.numeric)) #find all numeric variables

print(numeric_variables) #by this step found except id, there are only 3 numeric variables, then choose one of these numeric variable. I choose discount_price here.
```

    ## # A tibble: 40,833 × 4
    ##       id achievements original_price discount_price
    ##    <dbl>        <dbl>          <dbl>          <dbl>
    ##  1     1           54           20.0           15.0
    ##  2     2           37           30.0           NA  
    ##  3     3          128           40.0           NA  
    ##  4     4           NA           45.0           NA  
    ##  5     5           NA            0             NA  
    ##  6     6           NA           NA             35.2
    ##  7     7           51           60.0           70.4
    ##  8     8           55           15.0           17.6
    ##  9     9           34           30.0           NA  
    ## 10    10           43           50.0           NA  
    ## # ℹ 40,823 more rows

``` r
steam_games_discount_price<- ggplot(steam_games, aes(x = discount_price)) + #using the steam_games dataset and let discount_price to be value for x-axis.
  geom_histogram( aes(y = after_stat(density)), binwidth = 1, color = "black", na.rm = TRUE) 
#Crate a histogram and the y-axis be the density of discount_price. Let the wide of each bin to be 1; let the color of bins to be black; remove all NA values
print(steam_games_discount_price) #show up the graph
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
steam_games_achievements<- ggplot(steam_games, aes(x = achievements)) + 
  geom_histogram( aes(y = after_stat(density)), binwidth = 1, color = "black", na.rm = TRUE) 
print(steam_games_achievements) 
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-3-2.png)<!-- -->

``` r
steam_games_original_price<- ggplot(steam_games, aes(x = original_price)) + 
  geom_histogram( aes(y = after_stat(density)), binwidth = 1, color = "black", na.rm = TRUE) +
  xlim(0, 2000) #To ensure the shape of output is clear.
  print(steam_games_original_price) 
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-3-3.png)<!-- -->

2.  Create a new variable based on other variables in your data (only if
    it makes sense)

3.  Investigate how many missing values there are per variable. Can you
    find a way to plot this?

``` r
missing_values_steamgame <-steam_games %>% #pass the dataset steam_games into summarise() function
                            summarise(across(everything(), ~sum(is.na(.))))%>% #count the missing value of each variables and create a tipple for with these counts
                            pivot_longer(everything(), names_to = "variable_name", values_to = "missing_values_number") #transform the data from wide format to long format by creating two columns: one for variable names and one for their corresponding missing value counts. 
print(missing_values_steamgame) # show up the new tipple that answer "how many missing values there are per variable"
```

    ## # A tibble: 21 × 2
    ##    variable_name  missing_values_number
    ##    <chr>                          <int>
    ##  1 id                                 0
    ##  2 url                                0
    ##  3 types                              2
    ##  4 name                               2
    ##  5 desc_snippet                      41
    ##  6 recent_reviews                 35317
    ##  7 all_reviews                     9553
    ##  8 release_date                       2
    ##  9 developer                        342
    ## 10 publisher                       5100
    ## # ℹ 11 more rows

``` r
missing_value_graph<- ggplot(missing_values_steamgame, aes(y = variable_name)) + #plot a graph using the missing_values_steamgame tipple with the y-axis to be variable_name
                      geom_bar(aes(weight = missing_values_number))+ #build a bar chart and specify missing_values_number provide the weight for each bar in the bar chart
                      ggtitle("Find the number of missing for each variables") + #give a name for this graph
                      ylab("number of missing values") + #set a label for y-axis
                      xlab("variables") #set a label for x-axis
print(missing_value_graph) #show up the plot that answer "how many missing values there are per variable"
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

4.  Explore the relationship between 2 variables in a plot.

5.  Filter observations in your data according to your own criteria.
    Think of what you’d like to explore - again, if this was the
    `titanic` dataset, I may want to narrow my search down to passengers
    born in a particular year…

6.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish!

``` r
steam_games_numeric <- steam_games %>%
  select(where(is.numeric), -id)%>%  # Select all the numerical variables except the variable id.
  pivot_longer(cols = everything(), names_to = "numerical_variable", values_to = "value") #transform the numerical data from wide format to long format by creating two columns: one for numerical_variable and one for their corresponding values. 
print(steam_games_numeric)
```

    ## # A tibble: 122,499 × 2
    ##    numerical_variable value
    ##    <chr>              <dbl>
    ##  1 achievements        54  
    ##  2 original_price      20.0
    ##  3 discount_price      15.0
    ##  4 achievements        37  
    ##  5 original_price      30.0
    ##  6 discount_price      NA  
    ##  7 achievements       128  
    ##  8 original_price      40.0
    ##  9 discount_price      NA  
    ## 10 achievements        NA  
    ## # ℹ 122,489 more rows

``` r
# Create side-by-side box plot
ggplot(steam_games_numeric, aes(x = numerical_variable , y = value)) +
  geom_boxplot( color = "black", outlier.colour = "red", na.rm = TRUE) + #let the color of outline of box be black, let the color of outlier be red
  ggtitle("Side-by-Side Boxplot of Numerical Variables") + #Give a title to the plot
  ylab("Value") + #Label the y-axis
  xlab("Numerical Variables") #Label the x-axis
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` r
#due to the outlier to big and the mean and median are too small, I decide to draw another side-by-side box plot and set the upper and lower limits of the y-axis so that I can have a clear boxplot.

ggplot(steam_games_numeric, aes(x = numerical_variable , y = value)) +
  geom_boxplot( color = "black", outlier.colour = "red", na.rm = TRUE) + 
  ylim(0, 100) + #Set the upper and lower limits of the y-axis to be 100 and 0.
  ggtitle("Side-by-Side Boxplot of Numerical Variables with limited y-axis") + 
  ylab("Value") + 
  xlab("Numerical Variables") 
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-5-2.png)<!-- -->

7.  Make a new tibble with a subset of your data, with variables and
    observations that you are interested in exploring.

8.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot).

``` r
ggplot(steam_games, aes(x = achievements)) + #select the achievements from steam_games to be the x-axis.
  geom_density(fill = "lightblue", color = "darkblue", alpha = 0.7, na.rm = TRUE) + #draw a density graph with the fill color of the area below the density curve is light blue and the edge color of the density curve is dark blue
  xlim(0, 100)+ #let the range of x-axis to be 0 to 100 (without this code, it is hard to see the graph's detail)
  ggtitle("Density Plot of Achievements") + #give a title to this graph
  xlab("Achievements") + #Label the x-axis
  ylab("Density") #Label the y-axis
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggplot(steam_games, aes(x = original_price)) +
  geom_density(fill = "lightblue", color = "darkblue", alpha = 0.7, na.rm = TRUE) +
  xlim(0, 100)+
  ggtitle("Density Plot of Original Price") +
  xlab("Original Price") +
  ylab("Density") 
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-6-2.png)<!-- -->

``` r
ggplot(steam_games, aes(x = discount_price)) +
  geom_density(fill = "lightblue", color = "darkblue", alpha = 0.7, na.rm = TRUE) +
  ggtitle("Density Plot of Discount Price") +
  xlab("Discount Price") +
  ylab("Density") 
```

![](Mini_Data_Analysis_Deliverable_1_files/figure-gfm/unnamed-chunk-6-3.png)<!-- -->

2.2 **(4 points)** For each of the 4 exercises that you complete,
provide a *brief explanation* of why you chose that exercise in relation
to your data (in other words, why does it make sense to do that?), and
sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

1.  Plot the distribution of a numeric variable. (plot the distribution
    for achievements, discount_price, and original_price): Since there
    are only 3 useful numeric variables (the id variable does not count
    in it), I decided to plot three distribution graphs for these three
    variables. Also, understanding the distribution of a numerical
    variable is a fundamental step in data exploration. It can show the
    shape of distribution, outliers, and modality of data. Most
    importantly, while the distribution graph does not directly show
    missing values, it can indirectly reflect their impact. This might
    help me to answer the question I gave in 1.4. The results show that
    all three variables are right-skewed distributions, suggesting that
    most of the values for price and achievements are concentrated at
    lower values. Each distribution has several outliers. Moreover, the
    number of non-missing values for achievements and original_price
    appears to be smaller compared to discount_price, which might imply
    that original_price contains fewer NA values than the other two
    variables. I set a specific range for the x-axis on achievements
    because without this code the graph would look like an “L” without
    showing information (like peaks or outliers).

2.  Investigate how many missing values there are per variable. Can you
    find a way to plot this? (show up the missing values for each
    variable and plot this in a bar chat): This exercise directly shows
    how many NA values for all variables that are directly related to my
    question in 1.4. Understanding which variables have the most missing
    values helps in determining the reliability of the analysis.
    According to the graph, the number of missing values for
    discount_price is much smaller compared to the number of missing
    values for achievements and original_price. This observation aligns
    with the conjecture made in the analysis of the previous question,
    where we speculated that original_price and achievements have more
    NA values. Since both achievements and original_price have a big
    amount of missing data, the summary statistics derived from these
    variables might be distorted, reducing the reliability of any
    conclusions based on them.

3.  Use a boxplot to look at the frequency of different observations
    within a single variable. You can do this for more than one variable
    if you wish! (plot a side-by-side box plot for distribution for
    achievements, discount_price, and original_price): The box plot can
    help me to see the five-number summary (minimum, first quartile,
    median, third quartile, and maximum), outliers, and extreme values.
    I plot the side-by-side box plot here so that I can compare these
    three variables. According to the output from previous exercises, I
    already know that these three variables have different amounts of
    missing values. Thus, by using the side-by-side box plot I might be
    able to research How the data is distributed and whether missing
    values affect the dataset. One challenge with this visualization is
    the presence of numerous outliers and extreme values, which
    significantly stretches the y-axis and makes it difficult to observe
    the central part of the data. To address this, I imposed a limit on
    the y-axis. The new boxplot clearly shows up the five-number
    summaries. It also shows the fact that most of the data is
    concentrated at 75 and the data above 75 is considered outlier. The
    adjusting of the y-axis not only highlights the main portion of data
    but also acknowledges the presence of outliers.

4.  Use a density plot to explore any of your variables (that are
    suitable for this type of plot). (plot the density plot for
    achievements, discount_price, and original_price): The density plot
    provides a smooth estimate of the data distribution, and I can
    visualize how the missing values might alter the perceived
    distribution of variables. This helps to illustrate whether missing
    values are causing certain areas to be underrepresented. I limited
    the x-axis range to 0-100 for both achievements and original_price,
    as observed from the boxplot, because as shown in the boxplot, most
    of the data of these two variables are concentrated at 75 and
    without these limits, the detail of information wouldn’t show up due
    to the high y-axis (same issue with the first boxplot). This
    adjustment enables me to focus on the relevant range and observe the
    distribution more clearly. The distribution of the three images is
    biased to the right, and the peak is concentrated on the far left,
    indicating that most of the data is concentrated at low values,
    which is consistent with the analysis in the previous questions.
    Based on the missing values bar chart and these density plots, I
    speculate that the missing values are more likely concentrated at
    higher values. The sharp decline in density at higher values
    suggests that the higher-priced games or achievements might be
    underrepresented due to missing data.

<!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar
with it through exploring the data. You have also brainstormed one
research question that interested you (Task 1.4). Now it’s time to pick
4 research questions that you would like to explore in Milestone 2!
Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

1.  How are games from different types or publishers discounted?
    **comment**: Maybe categorize the discount price into low, median,
    and high, then calculate the proportion of different game types or
    publishers. This allows me to explore how different game types or
    publishers use discount strategies.

2.  How are games with different original_price ranges distributed
    across types? **comment**: Again categorize the original price and
    calculate the proportion of different game types.

3.  How do missing values impact the analysis of discount_price in Steam
    games? **comment**: This is a subdivision of the 1.4 problem. I
    would like to try to study where the missing values are mainly
    concentrated if the discount price is divided into several levels.

4.  How do original_price and discount_price relate to each other?
    **comment**: Since I divided to research original_price related to
    types and discount_price related to types individually, it still can
    not tell the relationship between these two variables. Studying
    their relationship might be a good aspect to see if the original
    price affects the discount price.

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major
continuity errors. An example of a major continuity error is having a
data set listed for Task 3 that is not part of one of the data sets
listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1
point deduction if most code runs without error, and 2 points deduction
if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your
repository. Its contents should automatically appear when you visit the
repository on GitHub.

Minimum contents of the README file:

-   In a sentence or two, explains what this repository is, so that
    future-you or someone else stumbling on your repository can be
    oriented to the repository.
-   In a sentence or two (or more??), briefly explains how to engage
    with the repository. You can assume the person reading knows the
    material from STAT 545A. Basically, if a visitor to your repository
    wants to explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README
files in other projects, you’ll wonder how you ever got by without them!
They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

-   All Rmd files have been `knit`ted to their output md files.
-   All knitted md files are viewable without errors on Github. Examples
    of errors: Missing plots, “Sorry about that, but we can’t show files
    that are this big right now” messages, error messages from broken R
    code
-   All of these output files are up-to-date – that is, they haven’t
    fallen behind after the source (Rmd) files have been updated.
-   There should be no relic output files. For example, if you were
    knitting an Rmd to html, but then changed the output to be only a
    markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point
deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files,
and re-knit each milestone’s Rmd file, so that everything is up to date
and relevant. Then, after your final commit and push to Github, CHECK on
Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You’ve tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and
Vincenzo Coia for launching.
