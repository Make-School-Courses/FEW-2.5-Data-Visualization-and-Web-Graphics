# Intro to Data Visualization

The goal of this lesson is to get started with data visualization. You will look at the features of making information visible and represented graphically using HTM, CSS, and JavaScript. 

## Why do you need to know this? 

Being able to display things on the screen is a core feature of computer software. It's what connects people to the computer. Having this skill in your backpocket is important to making software that is engaging and compelling to your users. 

The skill learned making data visualizations will translate to making you a better programmer and give you new ideas on how to approach visual problems on the computer. 

If you are interested in data, what is means, and how it communicates to people this class will give you an opportunity to explore and create. 

## Learning Objectives

- Define data visualization
- Load Data from JS
	- Identify and avoid CORs problems
- Idenitfy values in the Titanic dataset
- Extract data relevant values 
	- map, filter, reduce
	- min, max, average
- Display data in the DOM

## Overview 

- What is data visualization?
	- Some examples of Data viz
- Titanic Dataset
	- What does it contain?
	- How can this be visualized? 
		- min, max, average
	- Styles 
		- width
		- height
		- backgroundColor
		- Using Flex 
		
## Info graphic vs Data Visualization

Let's clarify what you are expected to make. 

- An info graphic provides information in the form of an image. These are often more comic strip and less abstract. The goal is to inform. 
- A data visualization is more abstract showing data in visual form. 

## Getting started 

- JSON 
	- All of the sample data is JSON
	- What is JSON?
	- Validating and formatting JSON
	- Loading JSON with Fetch
		- CORS !? 
			- What is CORS
			- How to to deal with it
			
## The Titanic Dataset 

Take a look at the [Titanic Dataset](https://www.kaggle.com/c/titanic/data). This link points to the Titanic dataset on Kaggle. There is also a copy in tutorial repo. 

Take a look at the data, ask yourself what you see? 

- There is a record for each passenger
- Each passenger has fields for a range of data points
	- age, fare, pclass, sex, etc. 

What values can you find here? What would you want to know from this? 

Pair and dicuss. Come up with a list of things you find interesting. List as many things as you can. 

Write the list on the board. 

## Exercise

Using the Titanic dataset

- Find the min, max, and range
- Filter
- Counting values
- Make elements on screen that visualize information 
- Agregate data

## Display things on the screen

- document.createElement()
- element.appendChild()
- element.style
	- height, width
	- backgroundColor
	- border
	- borderRadius

## After Class

- Start on Visualization 1

## Additional Resources

- [Array.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Array.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
- [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
- [document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
- [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
- [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
