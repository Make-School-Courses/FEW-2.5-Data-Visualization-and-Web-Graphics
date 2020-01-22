
# FEW 2.5 - Intro to Data Visualization

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-1.html ':ignore')

<!-- > -->

## Welcome to Data Visualization!

The goal of this lesson is to get started with data visualization. You will look at the features of making information visible and represented graphically using HTML, CSS, and JavaScript.

<!-- > -->

## Why you should know this or industry application

Being able to display things on the screen is a core feature of computer software. Having this skill in your back pocket is important for making software that is engaging and compelling to your users.

The skills learned to make data visualizations will translate to making you a better programmer and give you new ideas on how to problems on the computer.

If you are interested in data this your opportunity to show it.

<!-- > -->

## Learning Objectives

- Define data visualization
- Load Data from JS
    - Identify and avoid CORs problems
- Identify values in the Titanic dataset
- Extract data and derive relevant values
    - map, filter, reduce
    - min, max, average
    - nomarlize data
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

<!-- v -->

Some examples

- [Info Graphic](https://venngage.com/blog/what-is-an-infographic/)

- Data visualizations Examples
 - [What is data visualization](https://www.tableau.com/learn/articles/data-visualization)
 - [Tableau Best Data viz examples](https://www.tableau.com/learn/articles/best-beautiful-data-visualization-examples)
 - [Best Data Visualizations 2018](https://visme.co/blog/best-data-visualizations/)
 - [James Round](https://www.jamesrounddesign.com)
 - [Data visualization](https://datavizcatalogue.com)
 - [Examples](https://www.maptive.com/17-impressive-data-visualization-examples-need-see/)

Generative art and Data: 
- https://www.ted.com/playlists/201/art_from_data
- https://joshuadavis.com
- https://www.theatlantic.com/entertainment/archive/2015/05/the-rise-of-the-data-artist/392399/
- https://techcrunch.com/2016/05/08/the-digital-age-of-data-art/

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

**CORS - Cross-Origin Resource Sharing**, is a security feature built into the browser. It's also a headache for developers. In a nutshell, it prevents JavaScript in the browser from reading files on your file system.

The easy solution for you is to run your work from a local server. This is the solution that will work for all of the work in this class and will usually solve common CORS errors.

For more info read these articles.

- https://medium.com/@baphemot/understanding-cors-18ad6b478e2b
- https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

<!-- > -->

## The Titanic Dataset

Take a look at the [Titanic Dataset](https://www.kaggle.com/c/titanic/data). This link points to the Titanic dataset on Kaggle. There is also a copy in the tutorial repo.

(You can download the Titanic dataset in JSON or CSV here: https://public.opendatasoft.com/explore/dataset/titanic-passengers/export/)

Take a look at the data, ask yourself what you see?

- There is a record for each passenger
- Each passenger has fields for a range of data points
 - age, fare, pclass, sex, etc.

What types of values can you find here? 

What could this data tell you? 

Pair and discuss. Come up with a list of things you find interesting. **Write the list on the board.**

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

- Get data from the first passenger in the list
    - name, fare, pclass, survived, age
- How many total passengers? 
    - get the length of the list
- How many survived?
    - Loop over the list and count survived = Yes
- How many died?
    - Loop over the list and count survived = No
- How many passenger classes?
    - Loop over the list and look for each unique value
    - You can use an object or a set for this
- How many passengers in each class?
    - Loop over the list and count the number of times each unique value appears
    - Use an object where the key is passenger class
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

Solve these problems in code. 

- Use JS to read the Titanic Dataset.
- Write code to solve the problems above
 - Use foreach, map, filter, and reduce


```JS 
fetch('titanic-passengers.json')
    .then(res => res.json())
    .then(json => handleData(json))
    .catch(err => console.log(err.message))
```

## Normalizing Data 

Numbers are great but they aren't perfect for every situation. 

For example, imagine you want to graph the ages of Titanic passengers. They range from 0 to 80. Translated to the screen in pixels. 80px might be too small to display in the space available. 

Here's another example. Imagine graphing the US budget which is measured in millions, billions and trillions of dollars. Millions, billions, and trillions would be far too large in pixels. 

We need a system to convert values in one range into values in another range. For example ages 0 to 80 years into 0 to 400 px. Or 600 billion dollars into 12 rems. 

The solution is normalization. This is the process of converting values from their original ranges into a range of 0 to 1. Think of this as an intermediate step that is easily converted to any other range by multiplication. 

The formula for normalizing is: value / maxValue

<!-- > -->

## Normalizing challenges 

Normalizing applies to numeric data. With the Titanic dataset it would be good to normalize: 

- fare
- age

Try this on your own

## Scales 

Some values would fall on a scale. A scale is a measure with fixed zones. In the Titanic, dataset scales apply to:

- gender - [male, female]
- survived - [Yes, No]
- siblings - [true, false]
- embarked - [C, Q, S]

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

```JS 
for (let item of data) {
 const { fields } = item
 const { fare, name, age, embarked, parch, pclass, sex, sibsp, survived } = fields
 
 const bgColor = survived === 'Yes' ? 'rgba(51, 208, 45, 0.125)' : 'rgba(195, 52, 52, 0.125)'
 
 const el = document.createElement('div')
 const br = sex === 'male' ? '50% 50% 50% 0' : '50% 0 50% 50%'

 el.style.width = `${size}px`
 el.style.backgroundColor = bgColor
 
 container.prepend(el)
} 
```

<!-- > -->

## Challenges

- Make a div for each passenger
 - Give it a width, height, and background color
- Give each div different background color for survivors
- Set the width of each div based on the fare paid
- Show the gender of the passenger
 - This could be done with color or?
- Show the fare paid 
- Show passenger class
- Show the embarkation 

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
 1. How many movies had the release year of 2005? 2019?
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

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time** | **Activity** |
| ----------- | --------- | ------------------------- |
| 0:00 | 0:10 | Overview + Learning Outcomes |
| 0:10 | 0:10 | Infographic vs Data Visualization |
| 0:20 | 0:10 | Activity |
| 0:30 | 0:10 | JSON and CORS |
| 0:40 | 0:50 | Titanic Dataset |
| 1:30 | 0:10 | Break |
| 1:40 | 1:00 | Lab |
| 2:40 | 0:05 | Wrap-up + homework overview |
| TOTAL | 2:45 | |