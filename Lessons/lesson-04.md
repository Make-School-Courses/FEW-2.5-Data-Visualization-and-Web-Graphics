
# FEW 2.5 - Filter and Sorting

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-3.html ':ignore')

<!-- > -->

## Overview

Sorting and Filtering is an important step in organizing data. Organized data can reveal insights into th story of the data. 

<!-- > -->

## Why do you need to know this?

Sort and filter are two important operations that can be applied in a wide variety of uses in CS. 

<!-- > -->

## Learning Objectives

1. Use Array.sort()
1. Use Array.filter()
1. Adding interaction

## Array.sort()

Take a quick look at the documentastion: 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort

<!-- > -->

- Sorts values in place (doesn't make a copy)
- Sorts values based on String value
- Optional Compare function
    - Takes two params a, b
    - Return value determines how a and b are indexed
    - less than 0 a is indexed lower than b
    - greater than 0 b is indexed lower than a
    - 0 and the index of a and b is unchanged

<!-- > -->

Sort values less than 10 

```JS 
const a = [4,3,1,7,6,2]
a.sort() // [1,2,3,4,6,7]
```

<!-- > -->

Sorting larger numbers

```JS 
const a = [4,13,1,7,6,12]
a.sort() // [1, 12, 13, 4, 6, 7]
```

<!-- > -->

Use a compare function

```JS 
const a = [4,13,1,7,6,12]
a.sort((a, b) => {
  return a - b
}) // [1, 4, 6, 7, 12, 13]
```

<!-- > -->

What about non numeric data?

```JS
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort(); // ["Dec", "Feb", "Jan", "March"]
```

<!-- > -->

What about Titanic data?

```js
fields.sort((a, b) => {
    return a.survived === 'No'
})
```

Sorts survivors first

<!-- > -->

### Challenges - Array.sort()

- Sort fields on sex
- Sort fields on survived
- Sort fields on embarked
- Sort on both sex and survived

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## BREAK

Take a ten minute break

<!-- > -->

## Array.filter()

Take a look at the doce for array.filter(). 

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter

<!-- > -->

Array.filter() is similar to map() and reduce() it returns a new array. 

Array.filter() takes a filter function. This function receives the element as a parameter and returns true if the element is included or false if not. 

<!-- > -->

```JS 
const a = [4,13,1,7,6,12]
const b = a.filter((val) => val < 5)
// [4,1]
```

<!-- > -->

Using the Titanic data

```JS
const fieldsMen = fields.filter((p) => p.sex === 'male')
const fieldsWomen = fields.filter((p) =>  p.sex === 'female')
```

<!-- > -->

### Array.filter() challenges 

- display only women
- display only men
- display only pclass 1, 2, or 3

<!-- > -->

## Color

Color can be represented in a few ways in JS:

- hex colors: `#0f0` or `#00ff00`
- keyword colors: `red` or `blue`
- rgb: `rgb(0, 255, 0)`
- rgba: `rgba(0, 255, 0, 0.5)`
- hsl: `hsl(120, 50%, 77%)`
- hsla: `hsla(120, 50%, 77%, 0.6)`

In all cases, it comes down to string manipulation. For any color you want to generate, you'll need to generate a string similar to one of the strings above and assign that to a style property.

If you're generating colors in sequence, HSL has the advantage that the hue is separate from the other color components. Hue has a range of 360 degrees.

```JavaScript
// This generates 12 colors equally spaced around the color wheel:
const numberOfColors = 12
const step = 360 / numberOfColors
for (let i = 0; i < numberOfColors; i += 1) {
    const hue = step * i
    const colorString = `hsl(${hue}, 70%, 50%)`
    ...
}
```

Use RGBA or HSLA when you need to transparent colors. The last value is the alpha (transparency) of the color.

<!-- > -->

## Color Activity

For the same Titanic dataset, create a bar graph that shows the number of passengers from each of the 3 `embarked` cities (C = Cherbourg, Q = Queenstown, S = Southampton). Make sure each bar is a different color

<!-- > -->

## After Class

- Finish the [buttons and interaction tutorial](https://github.com/MakeSchool-Tutorials/FEW-2-5-Data-Visualization-Buttons-and-Interaction)
- Finish [Visualization 1](Assignments/Data-Visualization-1.md) by 11:59pm tonight

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:05      | Overview + Learning Outcomes                |
| 0:05        | 0:30      | Buttons                  |
| 0:35        | 0:20      | Colors       |
| 0:55        | 0:20      | Motion       |
| 1:15        | 0:10      | BREAK                     |
| 1:25        | 1:15      | Lab                       |
| 2:40        | 0:05      | Wrap up + Homework Overview |
| TOTAL       | 2:45      | -                         |
