
# FEW 2.5 - D3 Scales

<!-- Put a link to the slides so that students can find them -->

➡️ [**Slides**](https://make-school-courses.github.io/FEW-2.5-Data-Visualization-and-Web-Graphics/Slides/Lesson-10.html ':ignore')


## Lab

Choose an example or tutorial from the D3 site and recreate that example with your own dataset.

**Stretch Challenge:** Recreate a second example. The goal here is to get familiar with D3 to use later in your projects

<!-- > -->

## Overview

D3 Scales provide a system for normalizing and scaling values for display on the screen.

<!-- > -->

## Why you should know this

Scaling and normalizing data is an important task you'll do it all the time. D3's scale tools provide great functionality.

<!-- > -->

## Learning Objectives

1. Identify scales and uses for normalizing
1. Define a scale for each axis
1. Use the d3.scaleLinear() and
1. Differentiate between scaleLinear and scaleOrdinal

<!-- > -->

## Scale and normalization

Scaling and normalizing allows us to convert values of any range into values that can be displayed on the screen.

Scaling and normalizing works best when working with numbers. Sometimes you'll have values that don't normalize easily. For example names of countries and key words don't translate easily to numbers. Also there are situations where you want to categorize values into buckets. [D3 scaleOrdinal](https://observablehq.com/@d3/d3-scaleordinal) does this for you.

<!-- > -->

Use scaleOrdinal for:

- Converting values to colors
- Converting values into key words
- Converting keywords into a values, colors, or other things

<!-- > -->

## Get Started with scaleOrdinal

Go through and review the following links on your own:

- [Documentation](https://d3-wiki.readthedocs.io/zh_CN/master/Ordinal-Scales/)
- [Scales functions in D3](https://d3indepth.com/scales/)

<!-- > -->

<!-- .slide: data-background="#087CB8" -->
## [**10m**] BREAK

<!-- > -->

## Lab

Create one data visualization using scaleOrdinal and D3 Scales with a data source of your choosing. Use the previous examples to help you get started. You should build with either HTML/CSS or SVG.

<!-- > -->

## After class

- Continue working on your [Final Visualization 3](Assignments/Data-Visualization-3.md), due 3/4 9:30am

<!-- > -->

## Additional Resources

- https://d3-wiki.readthedocs.io/zh_CN/master/Ordinal-Scales/
- https://bl.ocks.org/d3indepth/fabe4d1adbf658c0b73c74d3ea36d465
- https://d3indepth.com/scales/
- https://github.com/soggybag/FEW-2-5-Data-Visualization-D3

<!-- > -->

## Minute-by-Minute

| **Elapsed** | **Time**  | **Activity**              |
| ----------- | --------- | ------------------------- |
| 0:00        | 0:05      | Overview + Learning Outcomes                |
| 0:05        | 0:10      | Scale and normalization                  |
| 0:15        | 0:20      | Get started with scaleOrdinal       |
| 0:35        | 0:55      | Example code                     |
| 1:30        | 0:10      | Break      |
| 1:40        | 1:00      | Lab      |
| 2:40        | 0:05      | Wrap up  |
| TOTAL       | 2:45      | -                         |

