# FEW 2.5 Visualization 4

## Interactive Data

**Due Date:** Wed, February 5

Create an interactive visualization. 

## Challenges 

**Challenge display data**

Use a button to display data. Clicking the button should show or hide one featur. For example gender, or embarked. 

The button should display itself in an active state when it's in effect.

You should at least **three buttons**. Each button should display a different aspect of the data.

**Challenge sort data** Clicking a button should sort or filter the data shown. Only one of these buttons should be active at a time. Clicking any one of these should deactivate the others. 

You can sort on any feature in the dataset gender, embarked, survived etc. 

**Challenge** Publish your work to GitHub Pages. Be sure to name your root file index.html. 

**Stretch challenge** create some buttons that filter the data displayed. 

If you filter the data your data array will be shorter than the number of elements in the DOM array. You should loop through the DOM array and get each item in the data array until you are out of range. For the remaining DOM elements either hide or give them neutral display style so we can tell they are not part of the data displayed. 

**Stretch Challenge** Display details about each passenger. You can make this work if you can get the index of the passenger from the element in the DOM. 

You can assign each DOM element you create `data-index` attribute when you create it. 

Handle clicking on the DOM elements adding an eventlistener to the parent element. 

```JS
passengers.addEventListener('click', (e) => {
  const index = e.target.dataset.index
  if (index !== undefined) {
    // Show data here
  }
})
```

Use the index to get the data to show from the data array. You can show the data in the DOM by creating an element and using `innerHTML` to set it's content. 

### Evaluate your work



| Aspect | Does not meet | Meets | Exceeds |
|:------------|:-------------|:------|:--------|
| **Completion** | Did not complete | Completed interactive visualization challenges | Completed stretch challenges |
| **Code Quality** | Your code is sloppy and inconsistent | Your code is well formatted and consistently styled | You have linted your code | 
| **Code Craft** | Your code is not DRY | Your code is DRY you are using functions to do your work | Your code has a plan, you know what it is, and you could use it to take over the world |

### Learing Objectives 

| Aspect | Does not meet | Meets | Exceeds |
|:-------|:--------------|:------|:--------|
| **Sort** | You could not use array.sort() without the docs | You can use array sort without the docs to sort strings and numeric values| You could sort just about anything any time or any place, array.sort() is a tool in your utility belt |
| **filter** | You could not use array.filter() without the docs | You can use Array.filter() without the docs | You can filter anything anytime or any place and frequently sort the wheat from the chaff (figuratively speaking) |