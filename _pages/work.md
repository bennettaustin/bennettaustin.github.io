---
layout: archive
title: "Work"
permalink: /work/
author_profile: true
---

## Data Science Intern at Plastic Omnium
Throughout the Summer of 2021, I worked as a data scientist at [Plastic Omnium](https://www.plasticomnium.com/en/), the world's leading fuel tank manufacturer. I worked within the engineering and digital manufacturing department under Derek Naas's supervision. I was tasked with two main projects: 1) developing an algorithm that predicts the thickness of a given fuel tank and 2) assist in improving and validating an existing algorithm which predicts the weld quality of various components inside of a fuel tank. The motivation for both algorithms comes from a goal of reducing manual labor and destructive testing, which in turn save time and money. 

The first algorithm was really my own project - I was the sole perosn working on this one. As usual with any data science project, I first had to collect data. I used the company's software to pull data holding information for 100,000 fuel tanks. The data consisted of each tank's thickness at different areas and various features inlcuding machine parameters (e.g. cycle time and temperature), machine throughput, and fuel tank weight. Of course, with all this data, I had to do some serious data cleaning; this called for changing data formats, converting values, the merging of various datasets, dealing with missing data, and normalization. The next steps I took were making some preliminary plots and statistical calculations to see if there are any initial patterns I can spot before building a model. Then I decided to write this thickness prediction algorithm in Julia. The first model I attempted was using a basic neural network built from the ground up.
