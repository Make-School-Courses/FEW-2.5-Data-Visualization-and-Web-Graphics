# Intro to Data Visualization

The goal of this lesson is to get started with data visualization. You will look at the features of making information visible and represented graphically using HTM, CSS, and JavaScript. 

## Why do you need to know this? 

Being able to display things on the screen is a core feature of computer software. It's what connects people to the computer. Having this skill in your backpocket is important to making software that is engaging and compelling to your users. 

The skill learned making data visualizations will translate to making you a better programmer and give you new ideas on how to approach visual problems on the computer. 

If you are interested in data, what is means, and how it communicates to people this class will give you an opportunity to explore and create. 

## Learning Objectives

- Define data visualization
- Identify the min, max, and range for a set of values
- Use map, filter, and reduce
- Create DOM elements with JavaScript
- Define RGBA and HSLA colors

## Overview 

- What is data visualization?
	- Some examples of Data viz
- Titanic Dataset
	- What does it contain?
	- How can this be visualized? 
		- min, max, range, and normalization
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

## Exercise

Using the Titanic dataset

- Find the min, max, and range
- Normalize 
- Filter
- Make elements on screen that visualize information 
	- Make an element for each passenger
		- Normalize values and set style properties
	- Make an element for each embarkation
		- Agregate and normalize data

## Display things on the screen

- document.createElement()
- element.appendChild()
- element.style
	- height, width
	- backgroundColor
	- ...

## Wrap Up

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
