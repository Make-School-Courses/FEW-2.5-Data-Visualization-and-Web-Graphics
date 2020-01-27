
# FEW 2.5 - Displaying Data graphically

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-2.html ':ignore')

<!-- > -->

## Overview

This class you will take the values generated in the previous class and turn them into shapes on the screen. The goal of this lesson is to create DOM elements and apply styles. The values applied to styles will come from the Titanic data.

<!-- > -->

## Why you should know this?

Displaying data is interesting and useful. You can convey a lot more information that is easier to grasp and show relations with images in some cases these would not be apparent with numbers.

Beyond data science being able to draw shapes in HTML is a key skill to creating interesting and copelling user interfaces. Everything covered here can be used in almost all aspects of web application development.

<!-- > -->

## Learning Objectives

- Create elements with JS
- Build basic visualizations with JS
- Use JS to apply CSS styles
- Create elements dynamically
- Normalize data for graphic representation

<!-- > -->

## Normalization

Values are almost always associated with a unit. For example

- $99 dollars
- 120bpm beat per minute
- 42 Miles

To display things on the screen we need to convert units like $, BPM, and Miles into px or em or a color. 

<!-- v -->

To do this, it's best to normalize data into a decimal value from 0 to 1.

In order to do _that_, it's often necessary to know the max value of your dataset and the range.

To normalize values: divide all of the values in a dataset by the max value.

<!-- v -->

### Example:

88 / 100 is 0.88, meaning 88 is 88% of 100

This works for any number.

56 / 121 is 0.4628099174 in other words 56 is ~46% of 121.

The two values above could now be used to create values that display on the screen. See the below example:

<!-- > -->

Looking at the Titanic dataset. 

- max age = 80 
– min age = 0 
- max fare = 512.3292
- min fare = 0

With these numbers we could graph the age of **Watt, Mrs. James (Elizabeth \"Bessie\" Inglis Milne)**. Bessie is age 40. To normalize her age divide by the max age: 

- Bessie's Age 40 Nromalized age 0.5 (40 / 80 = 0.5)

<!-- > -->

This same system applies to any value. Notmalize Bessi'es fare? 

<!-- > -->

15.75 / 512.3292 = 0.03074195264

It appears that some people paid a lot more than everyone else!

<!-- > -->

Try that again with **Bengtsson, Mr. John Viktor**. 

- Age 26
- Fare 7.775

<!-- > -->

- Age 26 / 80 = 0.325
- Fare 7.775 / 512.3292 = 0.01517578932

<!-- > -->

What if we wanted to convert these into pixels? 

Any time we talke about pixels we are usually measuring things aon the screen. 

Imagine you want to graph the ages of all of the passengers. You would know how big the box was where the graph would appear. Imagine it's 400px tall. 

<!-- > -->

You could multiply the normalized values by your target range. 

- Bessie age (normalized) = 0.5 * 400px = 200px
- John age (normalized) = 0.325 * 400px = 130px

<!-- > -->

If you were using CSS you could also use the % unit and multiply the normalized value by 100

- Bessie age (normalized) = 0.5 * 100% = 50%
- John age (normalized) = 0.325 * 100% = 32.5%

<!-- > -->

In code this might translate to roughly: 

```JS
const bessieAgeNormalized = 0.5
const johnAgeNormalized = 0.325
bessieDiv.style.height = `${bessieAgeNormalized * 400}px`
johnDiv.style.height = `${johnAgeNormalized * 400}px`
``` 

<!-- v -->

Here are a couple more examples:

```JavaScript
const maxValue = 100
const value = 88
const normalizedValue = value / maxValue

el.style.width = `${normalizedValue}%` // Convert to a percent
el.style.height = `${normalizedValue * 500}px` // convert to px
el.style.color = `hsl(${normalizedValue * 360}, 50%, 50%)` // Convert to a color

```

<!-- > -->

## Drawing shapes with HTML and CSS

There is a limit to what can be drawn with HTML and CSS, a wide range of shapes is possible. With a single div you can create a rectangle. With the rectangle you have the following options

- round the corners
- set a stroke
- rotate
- skew
- size
- color
- stroke

<!-- v -->

## Rectangles

The default shape is the rectangle. Anything you create on the computer is going to be a rectangle.

Draw a rectangle:

```html
<div style="width: 100px;
height: 100px;
background-color: red;">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
```

<!-- v -->

### Bar Graphs
The most common way data is displayed after showing it numerically is by drawing bar graphs. A bar graph is easily created with HTML and CSS.

```html
<div style="width: 200px; height: 200px; border:1px solid; display: flex; flex-direction: row; align-items: flex-end">
	<div style="width: 20px; height: 37%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 48%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 66%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 55%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 77%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 90%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 85%; background-color: red; margin: 5px"></div>
</div>
```

This block draws a group of rectangles and sizes the height with `%`. They are arranged horizontally using `flex`.

<!-- v -->

### Making elements

You can generate elements with JS. In the same way you created elements were defined in HTML in the previous example. You might follow these steps: 

- get a reference to a root element
- loop through your data 
		- make a new element
		- set styles on your new element
		- append the new element to the root element

<!-- > -->

Here are the steps in code:

```JS
const container = document.getElementById('id')

for (let i = 0; i < data.length; i += 1) {
	const el = document.createElement('div')
	el.style.height = `${100 * data[age].age}%`
	container.appendChild(el)
}
```
<!-- > -->

#### Setting Styles with JS

All CSS styles are accessed through an element's style property. All styles are camelcase version of the CSS property name. For example: 

- CSS: `width` -> JS `width`
- CSS: `display` -> JS `display`
- CSS: `background-color` -> JS `backgroundColor`
- CSS: `margin-top` -> JS `marginTop`
- CSS: `flex-wrap` -> JS `flex-wrap`

<!-- > -->

Values in CSS almost always have a unit. In JS you'll need to use a string that includes the unit. 

- CSS: `width: 100px` -> JS `width = '100px'`
- CSS: `display: flex` -> JS `display = 'flex'`
- CSS: `background-color: red` -> JS `backgroundColor = 'red'`
- CSS: `margin-top: 1px` -> JS `marginTop = '1px'`
- CSS: `flex-wrap: no-wrap` -> JS `flex-wrap = 'no-wrap'`

<!-- > -->

**Exercise:**

Try the code sample above with your data from the previous class. The goal will be to display all of the passengers as small boxes. 

- Create a root element in your HTML document give it id
- Define a reference to your root element
- Set the 
- loop through each passenger
		- Create an element 
		- Set the height and width to 30px for each element
		- Set margin to 1px
		- Set background color to red

<!-- > -->

Arrange all of the element inside the root element using flex box. Set the following properties on the root element:

- display: flex - `container.style.display = 'flex'`
- flex-direction: row - `container.style.flexDirection = 'row'`
- flex-wrap: wrap - `container.style.flexWrap = 'wrap'`

<!-- > -->

Try these challenges:

- Set the color of each passenger to red if they survived and black if they did not
- Set the border radius for each passenger based on gender (sex). Use 0 for males and 50% for females.
- Make a new container for the next set of challenges. The goal with these is to display fares paid as a bar graph. 
		- create a new root element for this graph by adding a new div with a unique id to the DOM
		- Get a reference to your new root element
		- Loop through all of the passengers
				- Create a new element
				- append this new element to your new root element
				- Set the width of the new element to `passenger.fare  maxFare`
				- set the height to 2px (any value other than 0)
				- set the bnackground color of the element to red if the passenger survived and black if they didn't

<!-- > -->

Besides setting the height and width what else do you think we can do?

<!-- > -->

## Transform

CSS transform is a powerful tool that provides methods to translate (move, left right, up or down), rotate, skew, and scale elements. When using transform you combine all transforms on the same line for example:

`transform: translate(10px, 30px) rotate(45deg) skew(10deg) scale(1.5);`

<!-- v -->

### Transform Rotate

Use transform: rotate to create other shapes from a rectangle like a diamond.

```html
<div style="width: 100px;
height: 100px;
background-color: red;
transform: rotate(45deg)">
</div>
```

Here the div is rotated with `transform: rotate(45deg);` Rotation works with units of radians (`rad`) or degrees (`deg`). There is also [Gradians](https://en.wikipedia.org/wiki/Gradian) (grad).  

```CSS
width: 100px;
height: 100px;
background-color: red;
transform: rotate(45deg);
```

<!-- > -->

## Rounding Corners

How do we make circles from rectangles?

Any of the four corners can have a radius. Round them all and you get a circle. Round a combination of the corners to get other shapes.

<!-- v -->

### Circles

Round all four corners to get a circle.

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50%">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50%;
```

<!-- v -->
### Eyes, Droplets and Leaves

Rounding two or three corners to get shapes that look like eyes, lemmons, leaves, droplets, or map pointers.

In this case you may also want to rotate the element to orient the shape correctly.

<!-- v -->

**Take the code below and see what it draws!**

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0">
</div>\
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0;
```

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 0 0">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 0 0;
```

<!-- v -->

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0;
```

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(135deg)">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(135deg);
```

<!-- v -->

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(-45deg)">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(-45deg);
```

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg)">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
```

<!-- > -->

## Strokes

Add a stroke to add some dimension to your shapes:

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50%;
transform: rotate(45deg);
border: 12px solid">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50%;
transform: rotate(45deg);
border: 12px solid;
```

<!-- v -->

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
border: 12px solid">
</div>
```

```css
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
border: 12px solid;
```

<!-- > -->

## Compound Shapes

Nest one shape inside another for more complex images. A nested element will always render on top of its parent. Note that if the parent rotates its position, the position of the inner element _will_ be effected.

```html
<div style="width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
border: 12px solid;
display: flex;
justify-content: center;
align-items: center">
	<div style="width: 50px;
	height: 50px;
	background-color:#000;
	border-radius:50%;
	border: 10px solid #fff;">
		<div style="width:20px;
		height: 20px;
		background: #fff;
		border-radius:50%;
		position: relative;
		left: 15px;
		top:-5px"></div>
	</div>
</div>
```

<!-- v -->

```css
/* Outer "eye" shape */
width: 100px;
height: 100px;
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
border: 12px solid;
display: flex;
justify-content: center;
align-items: center;

	/* Inner "pupil" shape */
	width: 50px;
	height: 50px;
	background-color:#000;
	border-radius:50%;
	border: 10px solid #fff;

		/* Inner inner "highlight" */
		width:20px;
		height: 20px;
		background: #fff;
		border-radius:50%;
		position: relative;
		left: 15px;
		top:-5px
```

<!-- > -->

## Generating dynamic elements

**Your goal is to generate all of this HTML with JavaScript** and abstract the process into functions that do the work for you. This way you can just supply a dataset, usually an array of values and have your function do the work of creating DOM elements and assigning CSS styles.

<!-- v -->

### Creating DOM elements

Use `document.createElement('div')` to create a new DOM element.

// <div></div>

`const el = document.createElement('div')`

Remember **to be visible an element must be the child of an element that is a descendant of the body tag**. Add an element as a child of another element with `parent.appendChild(el)`. For example:

`parent.appendChild(el)`

<!-- v -->

### Activity - Interview Questions

Think in terms of interview questions. How would what we are doing in class translate to an interview problem?

**Attempt 2 of the questions below**

<!-- v -->

- Easy
	- Generate one element for each record in the Titanic Dataset
	- Create one element for each male passenger
	- Create one element for each female passenger
- Moderate
	- Create two elements that show the ratio of passengers who survived vs those that didn't. (easy solution make a bar graph)
	- Create elements showing the ratio of passengers by `pclass` (easy solution make a bar graph)
- Hard
	- Show the ratio of men and women who survived vs men and women who did not survive.
	- Show the ratio of passengers who survived vs those that did not by embarkation.

<!-- v -->

### Styling elements

All CSS styles of an element are accessible through that element's `style` property. The styles are named with a camelCase version of the CSS style name. For example:

```JavaScript
el.style.width = '20px'
el.style.height = '160px'
el.style.backgroundColor = 'red'
...
```

NOTE! Almost every CSS property requires a unit. You must include these when setting a value with JS. This means usually the value will be a string with a value and a unit.

Notice CSS `background-color` becomes `backgroundColor` in JS.

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->

## Absolute Position

To position elements anywhere on the screen with numeric values, you'll want to use CSS `position: absolute`. Absolute position lets you set the a position using `left`, `top`, `right`, and `bottom`. The easiest way to work with these is to use `left` and `top` and imagine you are setting the position of an element by measuring its position from the top left of the screen.

Sometimes you'll want to position an element using coordinates of a parent. In other words you want to measure `top` and `left` from the top left of the parent. To do this set the parent's position to `position: relative`.

<!-- v -->

Here is an example:

```html
<div style="width: 200px; height: 200px; border:1px solid; position: relative">
	<div style="position: absolute; left: 10px; top: 6px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 35px; top: 40px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 62px; top: 60px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 90px; top: 50px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 116px; top: 85px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 152px; top: 80px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 170px; top: 120px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
</div>
```

<!-- v -->

Notice each of the circles is a div with a style of `border-radius: 50%`. This makes them circles.

The container div has been assigned the style `position: relative`. This makes the descendants use this div to determine where left, top, right, and bottom is.

<!-- v -->

Each of the child divs has `position: absolute` with this the left and top can set to position the element.

I wrote this code by hand and it was a lot of work and not very accurate. You want to automate this as much as you can. You will need to write code that sets the style of an element one property at a time.

<!-- > -->

## Lab

For this lab, you will work on writing functions to automate your visualizations. Keep these functions in a `utils.js` file that you can copy and reuse for your various assignments.

<!-- v -->

These functions should take in color and size parameters, and return a configured object. You can make one of these functions for each shape for ease of creation for your assignments:
- Rectangle
- Rounded Rectangles
- Circle
- Eyes
- Droplets
- Leaves

<!-- v -->

**Stretch Challenges**
- Create functions for compound shapes, or any other shapes you may use
- Have your functions take in a position parameter
- Have your functions take in a stroke parameter

<!-- > -->

## After Class

- Finish [Visualization 1](Assignments/Data-Visualization-1.md) by EOD next Wednesday

<!-- > -->

## Resources

- [Visualization with HTML, CSS, and JS](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-with-HTML-CSS-JS-Tutorial)
- [document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
- [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
- [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
- [CSS border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [CSS position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:10      | Overview + Learning Outcomes                |
| 0:10        | 0:05      | Normalization                  |
| 0:15        | 0:05      | Rectangles       |
| 0:20        | 0:05      | Transform                     |
| 0:25        | 0:10      | Rounding Corners / Circles      |
| 0:35        | 0:05      | Strokes |
| 0:40        | 0:10      | Compound Shapes |
| 0:50        | 0:40      | Generating dynamic elements |
| 1:30        | 0:10      | BREAK |

... More below!

<!-- v -->

...

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 1:40        | 0:10      | Absolute Position |
| 1:50        | 0:50      | Lab |
| 2:40        | 0:05      | Wrapup + homework overview |
| TOTAL       | 2:45      | -                         |

