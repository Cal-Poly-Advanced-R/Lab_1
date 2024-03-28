# Lab 1: Review of Statistical Computing with R

Each portion of the lab (part 1, part 2) should be written in a *separate* Quarto file. 

## Part One: Checking Normality

**Create a Quarto file for Part One.**

- Make sure your final file is carefully formatted, so that each analysis is clear and concise.
- Be sure your knitted .html file shows **all** your source code, including your function definitions.  

### Background: Q-Q Plots

A Q-Q (Quantile-Quantile) plot is a way of checking if two collections of observations come from the same distribution. 

To create a Q-Q plot, you need to carry out the following steps:

1. Take two vectors of the same length, `x` and `y`.

2. Put the vectors in order from largest to smallest.

3. Pair the ordered vectors up, so that the smallest value of `x` is paired with the smallest value of `y`, and so on.

4. Make a scatterplot of the ordered pairs.  

If the points in the scatterplot fall on a straight line, with intercept 0 and slope 1, 
this suggests that `x` and `y` are sampled from the same distribution.

### Write a function

Write a function that takes a **numeric vector** as an input and returns (not just prints!) a **Q-Q Plot** comparing your input to Normally distributed values. 

Your approach should be to:

- randomly generate a new vector `y` from a Normal distribution with the same mean and standard deviation as the input vector
- create a Q-Q plot of `x` and `y`

Your function may **not** use any existing functions specific to Q-Q plots; including, but not limited to, `qqplot()`, `geom_qq`, or `stat_qq`. 

Once you have written your function, you should demonstrate that your function works by running it on the `speed` column of the `cars` dataset (from base-R). 

### Code design and style

A major portion of programming is learning to write beautiful, well-formatted, and well-designed code.

Some (non-exhaustive!) tips:

* Name your variables and functions reasonably and informatively.

* Follow style guides (tidyverse or Google), especially with regard to white space, parentheses, and brackets.

* Be deliberate about your objects and object types, and how you choose to store information.

* Write efficient code: do not duplicate analyses unnecessarily, use loops / map / apply when it is not needed, or create new objects you don't need.

* Write well-designed code: your main function might rely on helpful smaller functions, 
and all functions should take reasonable inputs and give reasonable outputs.

* Your code should have at least a few comments, explaining what your functions do.


## Part Two: Data Analysis

**Create a new Quarto file for Part Two.**

- Make sure your final file is carefully formatted, so that each analysis is clear and concise.  
- Be sure your knitted .html file shows all your source code.

### The Data

Use the dataset `oscars-demographics-DFE.csv` in this repository.

To accomplish the tasks in this section you will need to do appropriate cleaning, adjusting, and reorganizing of the data.

In what follows, the phrase "Big 5 Awards" refers to the five individual Academy Awards covered in this dataset: Best Director, Best Actor, Best Actress, Best Supporting Actor, and Best Supporting Actress.

### Warm-ups

1. Which movie(s) won the most unique "Big 5" awards?

2. Of all actresses who have won the Best Actress award, what is(are) the most common first name(s)?  

3. What US State, or non-US country, has produced the most Oscar winners (for the awards in this dataset)?

### Age and Gender

The information in this dataset includes two awards given only to women (Best Actress, Best Supporting Actress) and two awards given only to men (Best Actor, Best Supporting Actor).  

Create a linear model that explores how the typical age of acting award winners has changed over time, and how this relationship differs for the two genders of awards.

*Note: You will absolutely need to do some careful manipulation of the date information in this dataset, before you create your model. You may assume all Oscar awards take place on February 1st of the year they are awarded.*

Print out the results of your model in a tidy and clean format -- you may find the **broom** package helpful. 

Briefly discuss the interpretations of your regression and what it leads you to conclude about this relationship.
