---
layout: default
title: "30DayMapChallenge"
date: 2025-11-01
categories: [projects]
permalink: /projects/30DayMapChallenge_2025
---

The 30DayMapChallenge consists of 30 different mapping themes and takes place every November. I participated to some extent this year, creating maps for certain themes as time permitted. 

## Topic 01: Points 🗺️ Elevation of Iceland

Just came back from 4 months of traveling, and I totally missed that the new #30DayMapChallenge starts today! To kick things off for Day 1, #Points, I quickly threw together a map visualizing the elevation of Iceland - experimenting with an approach that maps the average elevation across 100 km² areas using SRTM data.

processing in ArcGIS Pro, layout in Affinity Designer
generate tessellation points - extract SRTM values - symbology - design

<div class="blog-image">
  <img src="{{ '/assets/images/projects/30Maps_2025_01_Points_Iceland_GernotNikolaus.jpg' | relative_url }}" alt="Elevation of Iceland">
  <figcaption>Elevation of Iceland (own figure).</figcaption>
</div>

## Topic 02: Lines 🗺️ Global Tropical Cyclone Tracks and Landfalls (1980-2019)

Today’s map for Day 2, #Lines, of the #30DayMapChallenge visualizes Global Tropical Cyclone Tracks and Landfalls (1980-2019). Using the NOAA IBTrACS dataset, each line traces the path of a tropical cyclone, colored by wind intensity according to the Saffir–Simpson Scale, while points mark the first landfall of each storm.

processing in ArcGIS Pro, layout in Affinity Designer
filtered data - converted 10-min winds to 1-min winds - categorized + symbolized - intersected paths with land - summary statistics + join to extract first landfall points - symbolized - design

<div class="blog-image">
  <img src="{{ '/assets/images/projects/30Maps_2025_02_Lines_Cyclone_GernotNikolaus.jpg' | relative_url }}" alt="Global Tropical Cyclone Tracks and Landfalls (1980-2019)">
  <figcaption>Global Tropical Cyclone Tracks and Landfalls, 1980-2019 (own figure).</figcaption>
</div>