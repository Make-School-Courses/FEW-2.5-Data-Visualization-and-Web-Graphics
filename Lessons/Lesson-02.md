# Displaying Data graphically 

This class you will take the values generated in the previous class and turn them into shapes on the screen. 

## Why do you need to know this? 

Displaying data is interesting and useful. You can convey a lot more information that is easier to grasp and show relations with images in some cases these would not be apparent with numbers. 

Beyond data science being able to draw shapes in HTML is a key skill to creating interesting and copelling user interfaces. Everything covered here can be used in almost all aspects of web application development. 

## Learning Objectives

- Create elements with JS
- Build basic visualizations with JS
- Use JS to apply CSS styles
- Create elements dynamically
- Normalize data for graphic representation

## Overview 

The goal of this lesson is to create DOM element and apply styles. The values applied to styles will come from the Titanic data. 

### Normalization 

Values are almost always associated with a unit. For example 

- $ dollars
- bpm beat per minute 
- Miles

To display things on the screen we need to convert units link $ into px or another unit used in CSS. 

To do this it's best to normalize data into a decimal value from 0 to 1. 

To do this it's often necessary to know the max value of your dataset and the range.

To normalize values divide all of the values in a dataset by the max value.  

For example: 

88 / 100 is 0.88 that is 88 is 88% of 100

This works for any numbers. 

56 / 121 is 0.4628099174 in other words 56 is ~46% of 121. 

The two values above could now be used to create values that display on the screen. For example: 

```JavaScript
const maxValue = 100
const value = 88
const normalizedValue = value / maxValue

el.style.width = `${normalizedValue}%` // Convert to a percent
el.style.height = `${normalizedValue * 500}px` // convert to px
el.style.color = `hsl(${normalizedValue * 360}`, 50%, 50%)` // Convert to a color
```

## Drawing shapes with HTML and CSS

There is a limit to what can be drawn with HTML and CSS, a wide range of shapes is possible. With a single div you can create a rectangle. With the rectangle you have the following options

- round the corners
- set a stroke
- rotate
- skew

## Rectangles 

The default shape is the rectangle. Anything you create on the computer is going to be a rectangle. 

Draw a rectangle: 

<div style="width: 100px; 
height: 100px; 
background-color: red;">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
```

The most common way data is displayed after showing it numerically is by drawing bar graphs. A bar graph is easioly created with HTML and CSS. 

<div style="width: 200px; height: 200px; border:1px solid; display: flex; flex-direction: row; align-items: flex-end">
	<div style="width: 20px; height: 37%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 48%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 66%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 55%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 77%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 90%; background-color: red; margin: 5px"></div>
	<div style="width: 20px; height: 85%; background-color: red; margin: 5px"></div>
</div>

```HTML
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

Besides setting the height and width what else can you do?

### Transform Rotate

Use transform: rotate to create other shapes from a rectangle like a diamond. 

<div style="width: 100px; 
height: 100px; 
background-color: red; 
transform: rotate(45deg)">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
transform: rotate(45deg);
```

### Make more complex shapes by rounding the corners

Any of the four corners can have a radius. Round them all and you get a circle. Round a combination of the corners to get other shapes. 

#### Circles 

Round all four corners to get a circle. 

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50%">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50%;
```

#### Eyes, Droplets and Leaves

Rounding two or three corners to get shapes that look like eyes, lemmons, leaves, droplets, or map pointers. 

In this case you may also want to rotate the element to orient the shape corrently. 

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 0">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 0;
```

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 0 0 0">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 0 0 0;
```

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 50% 50% 0">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 50% 50% 0;
```

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 50% 50% 0;
transform: rotate(135deg)">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(135deg);
```

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 50% 50% 0;
transform: rotate(-45deg)">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 50% 50% 0;
transform: rotate(-45deg);
```

<div style="width: 100px; 
height: 100px; 
background-color: red; 
border-radius: 50% 0 50% 0;
transform: rotate(45deg)">
</div>

```CSS
width: 100px; 
height: 100px; 
background-color: red;
border-radius: 50% 0 50% 0;
transform: rotate(45deg);
```

## Generating dynamic elements

Your goal is to generate all of this HTML with JavaScript and abstract the process into functions that do the work for you. This way you can just supply a dataset, usually an array of values and have the your function do the work of creating DOM elements and assigning CSS styles. 

### Creating DOM elements

use `document.createElement()` to create a new DOM element. 

`const el = document.createElement('div')`

Remember to be visible an element must the child of an element that is a descendant of the body tag. Add an element as a child of another element with `parent.appendChild(el)`. For example: 

`parent.appendChild(el)`

### Interview Questions 

- Generate one element for each record in the Titanic Dataset
- Create one element for each male passenger
- Create one element for each female passenger 

### Styling elements 

All CSS styles of an element are accessible through that element's `style` property. The styles are named with a camelCase version of the CSS style name. For example:

```JavaScript
el.style.width = '20px'
el.style.height = '160px'
el.style.backgroundColor = 'red'
...
```

NOTE! Almost every CSS property requires a unit. You must inlcude these when setting a value with JS. This means usually the value will be a string with a value and a unit. 

Notice CSS `background-color` becomes `backgroundColor` is JS. 

## Absolute Position

To position elements anywhere on the screen with numeric values you'll want to use CSS `position: absolute`. Absolute position lets you set the a position using `left`, `top`, `right`, and `bottom`. The easiest way to work with these is to work `left` and `top` and imagine you are setting the position of an element measuring it's position from the top left of the screen. 

Sometimes you'll want to position an element using coordinates of a parent. In other words you want to measure top and left from the top left of the parent. To do this set the parent's position to `position: relative`. 

Here is an example: 

<div style="width: 200px; height: 200px; border:1px solid; position: relative">
	<div style="position: absolute; left: 10px; top: 6px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 35px; top: 40px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 62px; top: 60px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 90px; top: 50px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 116px; top: 85px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 152px; top: 80px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 170px; top: 120px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
</div>

```HTML
<div style="width: 200px; height: 200px; border:1px solid; position: relative">
	<div style="position: absolute; left: 10px; top: 6px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 35px; top: 40px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 60px; top: 60px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 85px; top: 50px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 110px; top: 78px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 135px; top: 99px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
	<div style="position: absolute; left: 160px; top: 120px; border-radius: 50%; width: 20px; height: 20px; background-color: red;"></div>
</div>
```

Notice each of the circles is a div with a style of `border-radius: 50%`. This makes them circles. 

The container div has been assigned the style `position: relative`. This makes the descendants use this div to determine where left, top, right, and bottom is. 

Each of the child divs has `position: absolute` with this the left and top can set to position the element. 

I wrote this code by hand and it was a lot of work and not very accurate. You want to automate this as much as you can. You will need to write code sets the style of an element on property at a time but if you can try to do this once when possible. 

## After Class 

- Finish Data [Visualization 1](Assignments/Visualization-1.md)

## Resources 

- [document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
- [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
- [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
- [CSS border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [CSS position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)

