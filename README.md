# Lab 1: Review of Statistical Computing with R

## Part One: Checking Normality (150 pts)

**Create an R Markdown file for Part One.**

Make sure your final file is carefully formatted, so that each analysis is clear and concise.  Be sure your knitted .html file shows all your source code, including your function definitions.  
(That is, for purposes of this exam, do not write your functions in a separate source file.)

### Background: Q-Q Plots

A Q-Q (Quantile-Quantile) Plot is a way of checking if two collections of observations come from the same distribution.

The steps are as follows:

1. Take two vectors of the same length, `x` and `y`.

2. Put the vectors in order from largest to smallest.

3. Pair the ordered vectors up, so that the smallest value of `x` is paired with the smallest value of `y`, and so on.

4. Make a scatterplot of the ordered pairs.  


If the points in the scatterplot fall on a straight line, with intercept 0 and slope 1, 
this suggests that `x` and `y` are sampled from the same distribution.


In this section, you will use a **Q-Q Plot** to check if a vector of values `x` comes from a Normal distribution.  
The approach is to randomly generate a new vector `y` from a Normal distribution with the same mean and standard deviation as `x`, 
then to create a Q-Q plot of `x` and `y`.
*(Note: A typical Normal Q-Q plot uses theoretical quantiles instead of randomly generated values.  We're taking a bit of a shortcut
in this assignment.)*


### Write a function  (100 points)

Your final function should take as input a **numeric vector**.

It should return (not just print!) a **Q-Q Plot** comparing your input to Normally distributed values.

You may **not** use any existing functions specific to Q-Q plots; including (but not limited to) `qqplot()`, `geom_qq`, or `stat_qq`. 

Demonstrate that your function works by running it on either real data of your choice, or on a non-Normal vector that you create.

### Code design and style (50 points)

A third of your grade on this section is for beautiful, well-formatted, and well-designed code.

Some (non-exhaustive!) tips:

* Name your variables and functions reasonably and informatively.

* Follow style guides (tidyverse or Google), especially with regard to white space, parentheses, and brackets.

* Be deliberate about your objects and object types, and how you choose to store information.

* Write efficient code: do not duplicate analyses unnecessarily, use loops/map/apply when it is not needed, 
or create new objects you don't need.

* Write well-designed code: your main function might rely on helpful smaller functions, 
and all functions should take reasonable inputs and give reasonable outputs.

* Your code should have at least a few comments, explaining what your functions do.


## Part Two: Data Analysis (150 points)

**Create a new R Markdown file for Part Two.**

Make sure your final file is carefully formatted, so that each analysis is clear and concise.  
Be sure your knitted .html file shows all your source code.


### The Data

Use the dataset `Oscars-demographics-DFE.csv` in this repository.

To accomplish the tasks in this exam, you will need to do appropriate cleaning, adjusting, and reorganizing of the data.

In what follows, the phrase "Big 5 Awards" refers to the five individual Academy Awards covered in this dataset:  
Best Director, Best Actor, Best Actress, Best Supporting Actor, and Best Supporting Actress.

### Warm-ups (10 points each)

1. Which movie(s) won the most unique "Big 5" awards?

2. Of all actresses who have won the Best Actress award, what are is the most common first name?  

3. What US State, or non-US country, has produced the most Oscar winners (for the awards in this dataset)?

### Age and Gender (60 points)

The information in this dataset includes two awards given only to women (Best Actress, Best Supporting Actress) 
and two awards given only to men (Best Actor, Best Supporting Actor).  

Create a linear model that explores how the typical age of acting award winners has changed over time, 
and how that effect is different for the two genders of awards.

*(Note:  You will absolutely need to do some careful manipulation of the date information in this dataset, before you create your model.
You may assume all Oscar awards take place on Feb 1 of the year they are awarded.)*

Print out the results of your model, and briefly discuss the interpretations and conclusions.


### Bootstrapping (60 points)

Use a bootstrap approach to answer the following question:  
What is an approximate 95% confidence interval for percent of "Big 5 Award" award winners who are not white?

In addition to the confidence interval, make a plot that illustrates your findings.
