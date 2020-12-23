
# FEW 2.5 - Intro to Data Visualization

<!-- Put a link to the slides so that students can find them -->

<!-- ➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-1.html ':ignore') -->

<!-- > -->

## Welcome to Data Visualization!

The goal of this lesson is to get started with data visualization. You will look at needed to make information visible.

The first step in the process is asking questions of the data you're working with. The code you'll write in this assignment will answer those questions. 

<!-- > -->

## Why you should know this or industry application

To make data visible you need to measure and quantify the data. While many programs have function built in that handle these operations it goof to know how they work and how to implement them yourself. 

The tools you will use for this are some of the most important tools to have in your tool box. 

<!-- > -->

## Learning Objectives

- Identify values in the Titanic dataset
- Extract data and derive relevant values
  - map, filter, reduce
  - min, max, average
  - nomarlize data

<!-- > -->

## Overview

The goal today is to look at the Titanic dataset and use JavaScript to extract relevant data from it. You'll use all of the regular CS tools with a focus on map, filter, and reduce. 

- Titanic Dataset
  - What does it contain?
  - How can this be visualized?
  - min, max, average
- map, filter, and reduce

## JSON

JSON is a common format for storing structured data for use with JavaScript. JSON stands for JavaScript Object Notation. 

JSON is not code. JSON is a plain text format. The JSON format looks like standard JavaScript Objects and can easily be converted to and from JavaScript Objects. This often happens automatically. 

Here are a few rules for JSON. JSON supports the following data types: 

- Number
- String - Must be quoted with double quotes
- Boolean - either of the vlaues `true` or `false`
- Array 
- Object - property names must appear in the double quotes
- null

What doe's JSON not support? While JSON is JS objects and is easily converted to JS object there are a few things that JSON connot represent: 

- functions 
- comments
- All properties must be quoted with double quotes
- Strings must quoted with double quotes

JSON files should always have the .json file extension. 

```JSON
[{
  "id": 1,
  "name": "Hadleigh",
  "says": "Pre-emptive didactic forecast"
}, {
  "id": 2,
  "name": "Hersh",
  "says": "Compatible secondary methodology"
}, {
  "id": 3,
  "name": "Shelly",
  "says": "Robust mission-critical strategy"
}, {
  "id": 4,
  "name": "Erina",
  "says": "Reactive next generation customer loyalty"
}]
```

## CSV

CSV or Comma Separated Values, is a text format for managing organized information. So it's information with each value separated by a comma.

In a CSV file each line is one row of data with each value separated by a comma. The first line is special as it holds a list of keys each separated by a comma. 

Below is the same data we looked at in JSON format above but in CSV format this time. 

```CSV
id,name,says
1,Hadleigh,Pre-emptive didactic forecast
2,Hersh,Compatible secondary methodology
3,Shelly,Robust mission-critical strategy
4,Erina,Reactive next generation customer loyalty 
```

## CSV vs JSON

JSON more human readable and works seemlessly with JavaScript because of built in support. 

CSV is notably smaller in file size. It takes fewer characters to express data in CSV format. The JSON sample above is 314 characters, the same data in CSV is only 183 characters. 

JSON has the ability to express structured data. For example a JSON file can express objects and arrays nested within other objects and arrays. CSV has a flat structure and only represents a single level, imagine an array of values (numbers and strings.) 

Why use JSON? Use JSON when you need structure beyond a simple array or object. Use JSON when you need seemlessly exchange data with JavaScript programs. 

Why use CSV? Use CSV when you have lots of data and that data is organized in a flat file structure. 

<!-- > -->

## The Titanic Dataset

Take a look at the [Titanic Dataset](https://www.kaggle.com/c/titanic/data). This link points to the Titanic dataset on Kaggle. Kaggle is a web site that shares dtaasets for data science and other studies. 

The Titanic dataset is the starting point for studying dtaascience. It's sort of the Hello World of datsets. It's large enough to provide meaningful information, but also small enough to be managable. 

The Titanic data on Kaggle is in CSV format which makes it harder to work with. You can download the Titanic dataset in JSON here: https://public.opendatasoft.com/explore/dataset/titanic-passengers/export/

Take a look at the data, ask yourself what you see?

- There is a record for each passenger
- Each passenger has fields for a range of data points
 - age, fare, pclass, sex, etc.

What types of values can you find here? 

What could this data tell you? 

Pair and discuss. Come up with a list of things you find interesting. **Write the list on the board.**

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- v -->

## Exercise: Finding meaning in Data

The Titanic dataset is an array of objects each of which describes a single passenger. 

What can the array tell you about the Titanic and it's passengers? 

```JS
[{
  "datasetid": "titanic-passengers", 
  "recordid": "398286223e6c4c16377d2b81d5335ac6dcc2cafb", 
  "record_timestamp": "2016-09-20T15:34:51-07:00",
  "fields": {
    "fare": 7.3125, 
    "name": "Olsen, Mr. Ole Martin", 
    "age": 40.0,
    "embarked": "S", 
    "parch": 0, 
    "pclass": 3, 
    "sex": "male", 
    "survived": "No", 
    "ticket": "Fa 265302", 
    "passengerid": 155, 
    "sibsp": 0,
    "cabin": "F4"
  }
},
  {
    ...
  }
]
```

Above is a single passenger what does this tell us about this passenger? 

Name three things you can say about this passenger? 

- ? 
- ? 
- ? 

If we had an array of paessenger what questions could you ask the data? Pair up and make a list of at least 3 questions: 

- ? 
- ? 
- ?

Using the Titanic dataset, we will be practicing the following techniques using JS:

- Counting values, how hany...
- Find the min, max, range, median values
- Filter, look at a subset
- Aggregate values, finding the total and average

<!-- > -->

## Lab Activity

Work through the following activities: [Tutorial](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-Working-with-Data/tree/master)

<!-- > -->

## After Class

Complete the Challenges: [Tutorial](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-Working-with-Data/tree/master)

<!-- > -->

## Additional Resources

- [Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
- [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)

<!-- > -->

<!-- 
## Minute-by-Minute

| **Elapsed** | **Time** | **Activity** |
| ----------- | --------- | ------------------------- |
| 0:00 | 0:05 | [Welcome to Data Visualization!](#welcome-to-data-visualization) |
| 0:05 | 0:10 | [Why you should know this or industry application](#why-you-should-know-this-or-industry-application) |
| 0:10 | 0:15 | [Learning Objectives](#learning-objectives) |
| 0:15 | 0:20 | [Overview](#overview) |
| 0:20 | 0:25 | [JSON](#json) |
| 0:25 | 0:30 | [CSV](#csv) | 
| 0:30 | 0:40 | [CSV vs JSON](#csv-vs-json) |  
| 0:40 | 0:50 | [The Titanic Dataset](#the-titanic-dataset) | 
| 0:50 | 1:00 | Break |
| 1:00 | 1:10 | [Exercise: Finding meaning in Data](#exercise-finding-meaning-in-data) |
| 1:10 | 2:00 | [Lab Activity](#lab-activity) |
| 2:00 | 2:10 | [After Class](#after-class) |
| TOTAL | 2:45 | - | 
-->
