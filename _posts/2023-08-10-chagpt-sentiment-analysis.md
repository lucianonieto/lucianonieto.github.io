---
layout: post
title: Proven Practice, Using ChatGPT-3 API for Sentiment Analysis
date: 2023-08-10 21:11 +0000
last_modified_at: 2023-08-10 21:11 +0000
author : Luciano Nieto
tags: [chatgpt, sentiment-analysis, python]
toc:  true
---

Can ChatGPT Serve as an Integrated API for Multilingual Sentiment Analysis?
In my pursuit of understanding sentiment analysis (since when I was in my graduation and the term “Data Mining” was hot), I encountered the challenge of effectively integrating the analysis of multiple languages simultaneously. 

The complexity escalated when attempting to process varied languages concurrently.
To address this challenge, I conducted a personal study using the ChatGPT API (accessible via a subscription). 
The primary objective entailed parsing a Google Review dataset focused on a specific location: the Lisbon Airport in Portugal - spanning a single day. 

## Dataset
The proposed Google Reviews dataset provides a sample of approximately 50 reviews about Lisbon Airport, directly in the original language in which they were written. To aid understanding, ChatGPT is able to automatically translate the provided text.

Sample of the dataset:

- You can download **[here](https://drive.google.com/file/d/1v_tmym1-2FHFLfkYw5lMkggbsWO1EVXs/view?usp=share_link)**.

![Google Review Dataset](/imgs/ds_1.png)

## Requirements

To use these scripts, you will need the following:

- Google account
- Google Colab
- API Key - OpenAI (free usage for 24h) or upgrade for paid plan.

## Coding and Exploratory Review
![data](/imgs/c1.png)
![data](/imgs/c2.png)
![data](/imgs/c3.png)
![data](/imgs/c4.png)
![data](/imgs/c5.png)
![data](/imgs/c6.png)
![data](/imgs/c7.png)

## Results

- Astonishingly, the results demonstrated a remarkable level of accuracy irrespective of the language involved, encompassing English, Portuguese, Spanish, Italian, and even German (languages present within the dataset). 

- Noteworthy is the fact that this process obviated the need for preliminary translation prior to engaging with the ChatGPT model.
To outline the specifics, the dataset encompassed 50 (x3 execution) individual records. 
- The associated cost incurred for this analysis amounted to a mere $0.03, making this a cost-effective solution.

## More

- GitHub Repo **[here](https://github.com/lucnietoX/chatgpt_api_sentiment_analysis.git)**.
- Notebook **[here](https://github.com/lucnietoX/chatgpt_api_sentiment_analysis/blob/main/OpenAIChatGPTAPI_SentimentAnalysis.ipynb)**