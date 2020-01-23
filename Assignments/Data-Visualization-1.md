# FEW 2.5 Visualization 1

## Collecting and Normalizing data

**Due Date:** Wednesday, 1/29, 11:59pm

Your goal with this assignment is prepare data for creating your visualization. 

## Getting started

The data set for this visualization will be the Titanic dataset. 

Your goal is to write code that sorts through the data and finds the relevant values. 

### Titanic Dataset

https://github.com/soggybag/data-visualizations/blob/master/titanic/titanic-passengers.json

This is Titanic Dataset in JSON format. Download this.

### Challenges 

Solve the following challenges: 

1. Get data from the first passenger in the list
    - name, fare, pclass, survived, age
1. How many total passengers? 
    - get the length of the list
1. How many survived?
    - Loop over the list and count survived = Yes
1. How many died? (diers?)
    - Loop over the list and count survived = No
1. How many passenger classes?
    - Loop over the list and look for each unique value
    - You can use an object or a set for this
1. How many passengers in each class?
    - Loop over the list and count the number of times each unique value appears
    - Use an object where the key is passenger class
1. **Stetch Challenges**
    - How many died in each class?
    - Get all of the ages from the Titanic Dataset
    - Filter data points where the age is missing
    - How many passengers embarked from Queenstown
    - How many people traveled with a nanny?
    - Find the min and max-age
    - Find min and max fare
    - How many siblings were there?
    - What is the survival rate of siblings vs only children?
    - How many ages were estimated?

### What will you turn in?

Create a repo for your visualization.  You will set up code in this assignment and later add the visualization to it in a following assignment. 

| Aspect | Does not meet | Meets | Exceeds |
|:-------|:--------------|:------|:--------|
| **Completion** | Did not complete the challenges | Solved all [challenges](#challenges) | Solved stretch challenges |
| **Code quality** | Does not follow coding best practice, the style inconsistent | Code is consistently styled and follows coding best practice, you used a linter | Code reviewed by peer |

### Learing Objectives 

| Aspect | Does not meet | Meets | Exceeds |
|:-------|:--------------|:------|:--------|
| **Define Data Visualization** | Could not define data visualization | Can describe data visualization | Can identify data visualizations in the "wild" |
| **Loading JSON** | Can't load JSON without reference code | Can load JSON without a reference | Can handle errors and customize the loading process to fit application needs |
| **Identify Values in Titanic Dataset** | Can't identify values in the Titanic dataset | Can identify values in the Titanic dataset | Feel confident you could identify values in any dataset |
| **Extracting Data** | Can't extract data and derive values from the Titanic dataset | Can extract relevant values from the Titanic Dataset | Could extract values from any dataset |
| **Deriving Values** | Can't derive a count, min, and max values from a dataset| Can get the min, max, and count from a dataset | Could derive range, average, and other values from data provided in the Titanic dataset |