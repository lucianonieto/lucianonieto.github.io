---
layout: post
title: Mapping Pet-Friendly Water Points in Madrid Using the City's Open Data API
date: 2024-09-16 16:47 +0000
last_modified_at: 2024-09-16 16:47 +0000
author : Luciano Nieto
tags: [madrid, python, api, pets, pandas, sqlite]
toc:  true
---

In an effort to enhance urban pet care, I explored the Open Data API provided by the City of Madrid to identify water points available across the city for pets, especially for dogs and cats. By integrating this data, I created an interactive HTML map showcasing the exact locations of these water stations, helping pet owners easily locate the nearest spots where their pets can drink water.

## Methodology:
- I used Python to process and filter the data from the Open Data API. The dataset contains geographic coordinates of water points, which I visualized using HTML and JavaScript to create a dynamic map in HTML.

## Requirements

To use this repo, you will need the following:

- Clone this repository to your local machine.
- Install the libraries: Sqlite, Pandas.

## Code

To update the data from API and save it into the sqlite database:

![](/imgs/mc1.png)

## Report Generation Code

![](/imgs/mc2.png)
![](/imgs/mc3.png)
![](/imgs/mc4.png)
![](/imgs/mc5.png)


## Result

<iframe src="/assets/mp1.html" width="100%" height="800" style="border:none;"></iframe>

## HTML

<a href="/assets/mp1.html" target="_blank">Click here to view the map in a new tab</a>

## More

- GitHub Repo **[here](https://github.com/lucnietoX/mascots)**.