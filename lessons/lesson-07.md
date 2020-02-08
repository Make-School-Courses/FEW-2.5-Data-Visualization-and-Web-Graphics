
# FEW 2.5 - Real Time Data

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-7.html ':ignore')

<!-- > -->

## Overview

Sometimes data changes moment by moment you can display that! 

<!-- > -->

## Why you should know this?

Experimenting weith real time data is expands your skills into new areas. 

<!-- > -->

## Learning Objectives

- Use canvas to draw data
- Use the audio object
- draw real time data

<!-- > -->

## Real Time Data

Real time data is data that changes from moment to moment, micro-second to micro-second even! 

This can be stock prices, exchange rates, interstellar noise, tectonic motion, heart rates, and more. For this example you will work with audio data. 

<!-- > -->

## Getting started 

Create a new folder for this project. Add an HTML file with two elements: 

```HTML
<canvas id="canvas" width="300" height="300"></canvas>
<button id="button-play">Play</button>
```

The canvas will display the visualization and the button will be used start playing the audio. 

## Audio

The Audio Object loads audio data. The Audio object does many things. It can play and modify audio, and generate new audio sources and process audio. 

It can also analyse audio and provide information about the audio source. 

### Load Audio 

The code snippet below uses the Audio object to load sound file and play it.

```JS
function startAudio() {
  const audio = new Audio()
  const audioContext = new (window.AudioContext || window.webkitAudioContext)()

  audio.src = 'bird-whistling-a.wav'
  
  audio.play()
}
```

Call the function above with a button: 

```JS
const playButton = document.getElementById('button-play')

playButton.addEventListener('click', (e) => {
  startAudio()
})
```

**You can't play audio with user interaction** Read this rationale https://developers.google.com/web/updates/2017/09/autoplay-policy-changes

<!-- > -->

### Analysing Audio

The Audio object can do many things with an audio source. For a visualization we need to create an analyzer. 

Add two variables to hold a reference to the analyzer and 

```JS
let analyser
let frequencyArray

function startAudio() {
  ...
}
```

Add a couple lines of code to your 

```JS
function startAudio() {
  const audio = new Audio()
  const audioContext = new (window.AudioContext || window.webkitAudioContext)()
  
  audio.src = 'bird-whistling-a.wav'

  // --------------------------------------------------------
  analyser = audioContext.createAnalyser()
  const source = audioContext.createMediaElementSource(audio)
  source.connect(analyser)
  analyser.connect(audioContext.destination)
  frequencyArray = new Uint8Array(analyser.frequencyBinCount)
  // --------------------------------------------------------
  
  audio.play()
}
```

These lines: 

- Create the `analyser`
- get a `source` 
- connect the source to the analyser
- define `freqeuncyArray` as an array of frequencies from the audio analyser

### Rendering Audio

The process of rendering audio will need to follow these steps: 

- clear the canvas 
- get an array of frequency values from the analyser
- for each frequency in the array
  - draw a shape influenced by each frquency

All of the steps above will be repeated each time the browser redraws. 

Add some references to the canvas and some variables we can use for drawing. 

```JS
const canvas = document.getElementById('canvas')
const ctx = canvas.getContext('2d')

const centerX = 300 / 2
const centerY = 300 / 2
const radius = 300 / 5
```

Add a new function: 

```JS
function render() {

  requestAnimationFrame(render)
}
```

Add a few lines to clear the canvas and draw a circle in the center.

```JS
function render() {
  // -----------------------------------------------
  ctx.clearRect(0, 0, 300, 300)
  ctx.beginPath()
  ctx.arc(centerX, centerY, radius, 0, 2 * Math.PI)
  ctx.strokeStyle = 'red'
  ctx.stroke()
  // ----------------------------------------------

  requestAnimationFrame(render)
}
```

Define a couple variables that will be used to drasw the bars. 

Get an array of freqwuncies from the analyser. 

```JS
function render() {
  ctx.clearRect(0, 0, 300, 300)
  ctx.beginPath()
  ctx.arc(centerX, centerY, radius, 0, 2 * Math.PI)
  ctx.strokeStyle = 'red'
  ctx.stroke()

  // -------------------------------------------------
  const bars = 200
  const step = Math.PI * 2 / bars

  analyser.getByteFrequencyData(frequencyArray)
  // --------------------------------------------

  

  requestAnimationFrame(render)
}
```

For each frequency you'll draw a line. To do this we need to the starting point: x1 and y1, and the ending point x2, y2. Each line is drawn as a path the last step is to stroke the paths. 

```JS
function render() {
  ctx.clearRect(0, 0, 300, 300)
  ctx.beginPath()
  ctx.arc(centerX, centerY, radius, 0, 2 * Math.PI)
  ctx.strokeStyle = 'red'
  ctx.stroke()

  const bars = 200
  const step = Math.PI * 2 / bars

  analyser.getByteFrequencyData(frequencyArray)
  
  // --------------------------------------------
  frequencyArray.forEach((f, i) => {
    const barLength = frequencyArray[i] * 0.5
    const x1 = (Math.cos(step * i) * radius) + centerX
    const y1 = (Math.sin(step * i) * radius) + centerY
    const x2 = (Math.cos(step * i) * (radius + barLength)) + centerX
    const y2 = (Math.sin(step * i) * (radius + barLength)) + centerY

    ctx.moveTo(x1, y1)
    ctx.lineTo(x2, y2)
  })

  ctx.stroke()
  // -------------------------------------------------

  requestAnimationFrame(render)
}
```

### Challenges 

1. Follow the tutorial steps above and get this working. 
2. Customize the drawing code from the last step.
  - change the color.
  - change the color of each line. To do this you'll need to: 
    - set the `ctx.strokeStyle` inside the loop and call `ctx.stroke()` inside the loop.
  - Change the lines drawn. Currently they are mapped around the circle. Change the x1, y1, and x2, y2 vaslues to something else. 





<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->



<!-- > -->

## After Class

- Finish [Visualization 2](Assignments/Data-Visualization-6.md), due TONIGHT, 11:59pm

<!-- > -->

## Additional Resources

- https://www.kkhaydarov.com/audio-visualizer/
- https://medium.com/@duraraxbaccano/computer-art-visualize-your-music-in-javascript-with-your-browser-part-2-fa1a3b73fdc6

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:05      | Overview and Learning Outcomes |
| 0:05        | 0:10      | CDNs |
| 0:15        | 1:00      | ChartJS |
| 1:15        | 0:10      | BREAK |
| 1:25        | 1:15      | Lab |
| 2:40        | 0:05      | Wrap up and review homework |
| TOTAL       | 2:45      | - |

