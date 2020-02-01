
# FEW 2.5 - Making an interactive view

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-5.html ':ignore')

<!-- > -->

## Overview

The goal of this session is to focus on making interactive views. 

<!-- > -->

## Why you should know this

Handling interaction is an important skill for front end developers. It's your job to handle user interaction and interface user input with software logic. 

<!-- > -->

## Learning Objectives

- Handle user interactions with events
- Create dynmaic views
- Style views dynamically
- Displaying your work with GitHub Pages

<!-- > -->

## Defining State

Using the Titanic Data you have displayed gender, embarkation, and survival. The goal now will be to show these dynamically. 

To turn the display of a property on or off you can use a variable. 

```JS
let showGender = false
let showEmbarked = false 
let showSurvived = false
```

If one of these variables is true we can show the data and if false the data is not shown. 

<!-- > -->

Next we need some buttons to toggle the state of each of these features. 

```HTML
<button id="button-gender">Gender</button>
<button id="button-embarked">Embarked</button>
<button id="button-survived">Survived</button>
```

Define a few buttons in the DOM with id names to connect them with JS. 

<!-- > -->

Add event listeners to each of the buttons that toggle the property. 

```JS
buttonGender.addEventListener('click', (e) => {
  showGender = !showGender
})
```
Here `showGender` will change from true to false to true again with each click. 

<!-- > -->

Show the state of the button: 

```JS 
buttonGender.addEventListener('click', (e) => {
  showGender = !showGender
  if (showGender) {
    e.target.style.backgroundColor = 'black'
    e.target.style.color = 'white'
  } else {
    e.target.style.backgroundColor = 'white'
    e.target.style.color = 'black'
  }
})
```

Now when showGender is true the button has a black background and white text. 

<!-- > -->

**Challenge:** Abstract the code from the previous section. Here are two ideas you can try: 

**Option 1:** use a class name to change the appearance of the button. Replace the iff statement in the previous code with:

```js
if (showGender) {
  e.target.classList.add('button-selected')
} else {
  e.target.classList.remove('button-selected')
}
```
Define the styles for the button-selected class in your stylesheet. 

```CSS
.button-selected {
  background-color: black;
  color: white;
}
```

**Option 2:** Create a function to abstract the code in the if else. 

```JS 
buttonGender.addEventListener('click', (e) => {
  showGender = !showGender
  selectButton(e.target, showGender) // 
})

function selectButton(el, state) {
  // change the appearance of el 
  // based on state
}
```

<!-- > -->

### Elements and data

The next step is connecting the data with the DOM. A good approach might be to create a DOM for each passenger in the Titanic dataset. 

```JS
const elements = []
const passengerData = []
```

Make two arrays. One to hold the DOM elements that will dipslay passengers. And the other to hold the passenger data loaded from the Titanic data set. 

<!-- > -->

```JS
const elements = []
const passengerData = []

function handleData(data) {
  const fields = data.map(({ fields }) => fields)

  fields.forEach(passenger => {
    const el = document.createElement('div')
    passengers.appendChild(el)
    elements.push(el) // store the element
    passengerData.push(passenger) // Store the passenger
  });
}
```
Loop over the Titanic data and create an element for each passeneger, and push each passenger object into the data array. 

<!-- > -->

Now that you made a DOM elements for each object in your dataset give each element a few default properties

```JS
fields.forEach(passenger => {
  ...
  el.style.width = '14px'
  el.style.height = '14px'
  el.style.backgroundColor = 'black'
  el.style.margin = '1px'
  el.style.transition = '200ms' // use trasnsition to asnimate changes
  el.style.boxSizing = 'border-box'
});
```

<!-- > -->

### Display data in the DOM

You should have an array of elements for each passeneger and an array of passenger data. Time to connect the two. 

The index of each data item will map to the index of the DOM element.

Keeping two arrays allows the DOM to be unaffected by changhes to data. This is important since sorting the data will not rearrange the DOM. 

<!-- > -->

Make a function that loops through your data and sets the appearance of an element at the same index in the elements array. 

```JS
function displayByGender() {
  passengerData.forEach((obj, i) => {
    const el = elements[i]
    const color = obj.sex === 'male' ? 'blue' : 'pink'
    el.style.backgroundColor = showGender ? color : 'black'
  })
}
```

If `showGender` is true the color is displayed otherwise the color is black. 

Call this function from the button event handler. 

<!-- > -->

**Challenges** 

Create functions to display embarked and survival. You can decide how these will be displayed. You can use background color, border, border radius or other. 

The function should use the variable `showSurvival` or `showEmbarked` to either display the feature or use a neutral value to not display that feature. 

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->

### Sorting 

We can sort the data on any of the fields. Sort will rearrange the data array 

Use the sorting ideas from the previouse lesson. 

IF you sort the data you'll need to display it again in the DOM. Call your display functions. 

<!-- > -->

## Your work on GitHub Pages

Use GitHub Pages to host your work. Each of your visualizations should exist on GitHub Pages.

Take some time to do the following:

1. Follow the guide [here](https://pages.github.com) to setup your GitHub Pages.
1. Add a link to your GitHub Pages repo in the project tracker.

For inspiration, here are some [example visualizations](https://github.com/soggybag/data-visualizations) on GitHub Pages.

<!-- > -->

## Lab

<!-- > -->

## After Class



<!-- > -->

## Resources



<!-- v -->



<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:05      | Admin |
| 0:05        | 0:25      | Overview |
| 0:30        | 0:40      | Learning objectives |
| 1:10        | 0:10      |  |
| 1:20        | 0:10      | Sets      |
| 1:30        | 0:10      | BREAK      |
| 1:40        | 1:00      | Lab      |
| 2:40        | 0:05      | Wrap up + Homework Overview |
| TOTAL       | 2:45      | -                         |


