# FEW 2.5 Data Visualization Interaction tutorial

Handling user interaction is the stock and trade of front end devlopers. Applying interaction to a visualization can add a lot of engagement and provide new insights into the data. 

## Why should you learn this? 

This tutorial will cover a few the standard interactions that appear in many projects core to all desktop and mobile software UI. 

## Buttons, Toggle Buttons and Button Groups 

A common UI requirement is the button. A button handles clicks or taps. 

### Buttons

Consider a button to run the same code every time it is clicked or tapped. It's like your doorbell. 

A button might be created like this: 

```HTML
<button id="hello-button">Login</button>
```

You might handle interaction with this button like this: 

```JavaScript
const helloButton = document.getElementById('hello-button')

helloButton.addEventListener('click', (e) => {
	// do stuff
}) 
```

### Toggle Buttons 

In some cases you'll want a button that toggles between two states each time it is tapped. Think of this like a light switch. 

You might make a toggle button like this: 

```HTML
<button id="toggle-button">Mode</button>
```

The code behind a toggle button is more complex. First, the state of the button needs to be expressed in the style of the button. Second, the button needs to execute different code depending on it's state. 

You set up a toggle button like this: 

```JavaScript 
const toggleButton = document.getElementById('toggle-button')

let buttonState = false

function selectButton(button, state) {
	button.style.border = '1px solid'
	button.style.borderRadius = '5px'
	button.style.margin = '5px'
	button.style.padding = '5px 10px'

	if (state) {
		button.style.backgroundColor = '#000'
		button.style.color = '#fff'
	} else {
		button.style.backgroundColor = '#fff'
		button.style.color = '#000'
	}
}

selectButton(toggleButton, buttonState)

toggleButton.addEventListener('click', (e) => {
	buttonState = !buttonState 
	selectButton(toggleButton, buttonState)
})
```








