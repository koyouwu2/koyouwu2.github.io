---
layout: post
title: "UFO Sightings: Shapes and Timing"
date: 2026-11-20
permalink: /ufo-visualizations/
---

# UFO Sightings: Shapes and Timing

This project uses the public UFO sightings dataset from the IS 445 dataset list. Both visualizations were created in Python using Altair and Vega-Lite.

## Visualization 1: Most Common Reported UFO Shapes

<iframe src="{{ '/assets/plots/ufo_shapes.html' | relative_url }}" title="Bar chart of the top ten reported UFO shapes" width="100%" height="440" style="border:0;" loading="lazy"></iframe>

My first visualization is a horizontal bar chart showing the ten most frequently reported UFO shapes. The shape is a **nominal** variable on the y-axis, while the number of reports is a **quantitative** variable on the x-axis. I use a sequential blue color scheme based on the number of reports: darker blue highlights higher counts. In Python, I cleaned the shape names, removed records missing a shape, grouped the data by shape, counted the reports, and selected the ten most common categories. This makes the rankings easier to compare than displaying every category.

## Visualization 2: When Were UFO Sightings Reported?

<iframe src="{{ '/assets/plots/ufo_time_heatmap.html' | relative_url }}" title="Interactive heatmap of UFO reports by month and hour" width="100%" height="480" style="border:0;" loading="lazy"></iframe>

My second visualization is a heatmap showing how the number of UFO reports varies across the months of the year and hours of the day. Month is encoded as a **nominal** category in calendar order, hour as an **ordinal** variable from 0 to 23, and report count as a **quantitative** variable represented by the intensity of a sequential blue color scale. I parsed the sighting dates in Python, normalized times marked `24:00` to `00:00`, removed records without valid dates, extracted month and hour, and counted the reports for each combination. The color scale helps identify periods with more reported sightings.

**Interactivity:** The heatmap has a dropdown menu that lets visitors switch between all countries and selected individual countries. This helps users compare month-and-hour patterns without making the graph crowded. Hovering over a cell shows the selected region, month, hour, and number of reports. This dropdown filter is interactive functionality beyond ordinary panning or zooming.

## Sources and Analysis

[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/ufo-scrubbed-geocoded-time-standardized-00.csv) · [The Analysis](https://github.com/koyouwu2/koyouwu2.github.io/blob/main/python_notebooks/ufo_visualizations.ipynb)

**Note:** These charts describe records in this historical dataset, not verified UFO events. Counts are not adjusted for population or differences in reporting behavior.
