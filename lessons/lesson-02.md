
# FEW 2.5 - Lesson 2

<!-- Put a link to the slides so that students can find them -->

<!-- ➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-2.html ':ignore') -->



## Infographic vs Data Visualization

Let's clarify what you are expected to make.

An infographic provides information in the form of an image. These are often more comic strip and less abstract. The goal is to inform.

A data visualization is more abstract showing data in visual form.

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








<!-- > -->

## Overview

In the last class we examined data to find some relevant values. Today we will continue with this idea but go further. This time around we'll look at abstracting our methods of data collection, collecting data that has more than one association, and build data structures that express the data.

<!-- > -->

## Why you should know this?

The problems in the challenges for today will help you develop your coding skills by offering more involved problems. 

<!-- > -->

## Learning Objectives

- Abstract methods to expand their functionality
- Build histograms
- Use map, filter, and reduce

## Looping over Arrays

Looping over each element in an array is a common operation. The code you write will need to do this often. 

Imagine you have an array and need to log each number ot the console. 

Loop over an array with a for loop:

```JS
const arr = [1,2,3,4]
for (let i = 0; i < arr.length; i += 1) {
	console.log(arr[i])
}
```

Running code for each element in an array is so common Array provides a method for this: `forEach`. Foreach takes a callback function as a parameter and calls that function once for each element in the array and passes the element and the index to the callback.

```JS
const arr = [1,2,3,4]
arr.forEach((item, index) => {
	console.log(item)
})
```

Challenge: Write a function that works like forEach. 

```JS
function forEvery(arr, callBack) {
	...
}

const numbers = [1,2,3,4,5]
forEvery(numbers, (item, i) => {
	console.log(item, i) 
})
```

## Map, Filter, and Reduce

Running code on each element in an array is common. Often you'll want to perform one of three other common tasks. 

- Map - Transform each element in the source array and add it to a new Array
- Filter - Create a new array that contains a subset of the source array 
- Reduce - Create a single value aggregated from the source array

> Map/filter/reduce in a tweet:
>
> `[🌽, 🐮, 🐔].map(cook)` -> `[🍿, 🍔, 🍳]`
> `[🍿, 🍔, 🍳].filter(isVegetarian)` -> `[🍿, 🍳]`
> `[🍿, 🍳].reduce(eat)` -> `💩`

When working with map, filter, and reduce arrow functions are your friend! They make their syntax makes the code you write compact and easy to read. 

Consider the example below: 

```JS 
// This is about as verbose as you cna get
arr.filter(function(item) {
	if (item > 5) {
		return true
	}
	return false
})

// This is very compact
arr.filter(item => item > 5)
```

If you have a strong understanding of arrow function syntax the second example has a lot of advantages. It's easier to read and shorter to type. It's probably less error prone for these reasons. 

### Map 

Use map to transform an array. Here you are making a new array of new things made from the things in the original array. 


```JS 

```

## Lab



## After Class



## Resources



<!-- 

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:10      | Overview + Learning Outcomes |
| 0:10        | 0:05      | Normalization |
| 0:15        | 0:05      | Rectangles |
| 0:20        | 0:05      | Transform |
| 0:25        | 0:10      | Rounding Corners / Circles |
| 0:35        | 0:05      | Strokes |
| 0:40        | 0:10      | Compound Shapes |
| 0:50        | 0:40      | Generating dynamic elements |
| 1:30        | 0:10      | BREAK |

 -->