<!-- .slide: data-background="./Images/header.svg" data-background-repeat="none" data-background-size="40% 40%" data-background-position="center 10%" class="header" -->
# FEW 2.5 - Intro to Data Visualization

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](/Syllabus-Template/Slides/Lesson1.html ':ignore')

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:10      | Overview + Learning Outcomes                |
| 0:10        | 0:10      | Infographic vs Data Visualization                  |
| 0:20        | 0:10      | Activity       |
| 0:30        | 0:10      | JSON and CORS                     |
| 0:40        | 0:50      | Titanic Dataset      |
| 1:30        | 0:10      | Break |
| 1:40       | 1:00      | Lab                         |
| 2:40       | 0:05      | Wrap-up + homework overview            |
| TOTAL       | 2:45      |             |


<!-- > -->

## Welcome to Data Visualization!

The goal of this lesson is to get started with data visualization. You will look at the features of making information visible and represented graphically using HTML, CSS, and JavaScript.

<!-- > -->

## Why you should know this or industry application

Being able to display things on the screen is a core feature of computer software. It's what connects people to the computer. Having this skill in your back pocket is important for making software that is engaging and compelling to your users.

The skills learned to make data visualizations will translate to making you a better programmer and give you new ideas on how to approach visual problems on the computer.

If you are interested in data, what it means, and how it communicates to people this class will give you an opportunity to explore and create.

<!-- > -->

## Learning Objectives

- Define data visualization
- Load Data from JS
    - Identify and avoid CORs problems
- Identify values in the Titanic dataset
- Extract data relevant values
    - map, filter, reduce
    - min, max, average
- Display data in the DOM

<!-- > -->

## Overview

- What is data visualization?
    - Some examples of Data visualization
- Titanic Dataset
    - What does it contain?
    - How can this be visualized?
        - min, max, average
    - Styles
        - width
        - height
        - backgroundColor
        - Using Flex

<!-- > -->

## Infographic vs Data Visualization

Let's clarify what you are expected to make.

- An infographic provides information in the form of an image. These are often more comic strip and less abstract. The goal is to inform.
- A data visualization is more abstract showing data in visual form.

Some examples

- [Info Graphic](https://venngage.com/blog/what-is-an-infographic/)
- Data visualizations Examples
	- [What is data visualization](https://www.tableau.com/learn/articles/data-visualization)
	- [Tableau Best Data viz examples](https://www.tableau.com/learn/articles/best-beautiful-data-visualization-examples)
	- [Best Data Visualizations 2018](https://visme.co/blog/best-data-visualizations/)
		- [James Round](https://www.jamesrounddesign.com)
	- [Data visualization](https://datavizcatalogue.com)
	- [Examples](https://www.maptive.com/17-impressive-data-visualization-examples-need-see/)

<!-- v -->

## Activity

Use the previous links to answer the following questions

- What is data visualization?
- What is data?

<!-- > -->

## Getting started

- JSON
	- All of the sample data is JSON
	- What is JSON?
	- Validating and formatting JSON
	- Loading JSON with Fetch
	 - CORS
		- What is CORS
		- How to deal with it

<!-- > -->

## CORS

CORS - Cross Origin Resource Sharing, is a a security feature built into the browser. It's also a headache for developers. In a nutshell it prevents JavaScript in the browser from reading files on your file system.

The easy solution for you is to run your work from a local server. This is the solution that will work for all of the work in this class and will usually solve common CORS errors.

For more info read these articles.

- https://medium.com/@baphemot/understanding-cors-18ad6b478e2b
- https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

<!-- > -->

## The Titanic Dataset

Take a look at the [Titanic Dataset](https://www.kaggle.com/c/titanic/data). This link points to the Titanic dataset on Kaggle. There is also a copy in the tutorial repo.

Take a look at the data, ask yourself what you see?

- There is a record for each passenger
- Each passenger has fields for a range of data points
    - age, fare, pclass, sex, etc.

What values can you find here? What would you want to know from this?

Pair and discuss. Come up with a list of things you find interesting. List as many things as you can.

Write the list on the board.

<!-- v -->

## Exercise

Using the Titanic dataset, we will be practicing the following techniques using JS:

- Find the min, max, and range
- Filter
- Counting values
- Make elements on screen that visualize information
- Aggregate data

<!-- v -->

### Interview Questions

- Get the fare from the first record
- How many passenger classes?
- How many survived?
- How many died?
- How many passengers in each class?
- How many died in each class?
- Get all of the ages from the Titanic Dataset
- Filter datapoints where the age is missing
- How many passengers from Queenstown
- How many people travelled with nanny?
- How many siblings were there?
- What is the survival rate of siblings vs only children?
- How many ages were estimated?

<!-- > -->

## Display things on the screen

It's one thing to find the answer to questions, but this class is about visualizing the answer, so we need a way to put our information on the screen! Below are some useful methods to do this:

- document.createElement()
- element.appendChild()
- element.style
    - height, width
    - backgroundColor
    - border
    - borderRadius

<!-- > -->

## Challenges

- Make make a div for each passenger
    - Give it a height, width, and background-color

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->

## Lab Activity

Work through the following activities in this order to practice your JS visualization skills:

1. Finish up the activities and challenges presented earlier in class today if you haven't already
1. Follow this [Tutorial](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-Working-with-Data/tree/master) and solve all of the challenges.
1. **Stretch Challenge** [Download this Netflix data set](https://www.kaggle.com/shivamb/netflix-shows) and answer the following questions through visualizations:
    1. What is the ratio of TV Shows to Movies?
    1. How many movies had a release year of 2005? 2019?
    1. How many TV shows had more than 3 seasons?
    1. How many Comedies does India have?

<!-- > -->

## After Class

Start on [Visualization 1](Assignments/Data-Visualization-1.md). This first assignment will use the Titanic Dataset.

Before you can visualize data you need to have data. Follow this [Tutorial](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-Working-with-Data/tree/master) and solve all of the challenges.

<!-- > -->

## Additional Resources

- [Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
- [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
- [document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
- [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
- [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
