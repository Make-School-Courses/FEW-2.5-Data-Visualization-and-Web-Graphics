
# FEW 2.5 - Review and Present

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-6.html ':ignore')

<!-- > -->

## Overview

This class will take a look at your work, find the things that need improvement, and create a trategy to wrap up the project and make it a good portfolio piece.

### Why?

Taking a critical look at your work is important. Adding things to your portfolio is important. looking for ways to measure your progress is important. 

<!-- > -->

## Learning Objectives

- Identify areas areas for improvement
- Strategize problem solving
- Use Events
- Identify and use and explain event delegation
- Explain Event bubbling

<!-- > -->

## Events

Events are things that happen in the program. Usually they are things that happen in the browser. These are things like: 

- mouse clicks
- form input 
- resources loaded
- keyboard button pressed!

Events can happen at DOM nodes. For example a mouse click might happen at a button or list item. 

### addEventListener

Use addEventListener to listen for events at an object. 

```JS
const button = document.getElementById('button')
button.addEventListener('click', (e) => { ... })

element.addEventListener(eventName, handler)

p.addEventListener('click', () => { alert('P') })
p.addEventListener('click', () => {})
p.onclick = () => { ... }
```

Event name is the name of the event, it's always a string. Handler is a function that handles the event when it occurs.  

### Bubbling

Since the DOM is a tree structure events move up from their target through their ancestors this is called bubbling. 

```HTML
<body>
		<div class="container">
			<div data-id="1">
			...
			<div data-id="891">
			<ul>
					<li>
							<div>
								<strong>
```

Name: Apple

Imagine you are listening for an event at the `<li>` tag but the click occured at the `<strong>` or `<div>`. Bubbling passes the event up the tree each of the parent elements. This gives each containing element a chance to handle the event. 

https://javascript.info/bubbling-and-capturing

<!-- > -->

## Review your work

Look at your work as a finished presentation on the data it presents. View it with a critical eye and identify three things you can improve.

Pair up and discuss your projects with someone else. Find three areas things that you can improve. 

<!-- > -->

## Publish your Work

To make your work a good portfolio item it should be live and it should be documented. 

- Publish your work to GitHub pages
- Write a Readme

<!-- > -->

### Project Readme

The project Readme should include: 

- A short description of the project
- Some background information
- A link to the project
- Getting Started
- Badges!

<!-- > -->

## 


<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->

## Lab

Use lab time to finish up your project and write your readme. 

<!-- > -->

## After class

- [Data Visualization 5](../Assignments/Data-Visualization-5.md)

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity** |
| ----------- | --------- | ------------ |
| 0:00        | 0:05      | Objectives |
| 0:05        | 0:15      | Overview |
| 0:20        | 0:30      | In Class Activity I |
| 0:50        | 0:10      | BREAK |
| 1:00        | 0:45      | In Class Activity II |
| 1:45        | 0:05      | Wrap up review objectives |
| TOTAL       | 1:50      | - |

