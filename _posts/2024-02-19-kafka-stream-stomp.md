---
layout: post
title: Using STOMP protocol to stream data with Kafka and MongoDB
date: 2024-02-19 16:44 +0000
last_modified_at: 2024-02-19 16:44 +0000
author : Luciano Nieto
tags: [streaming, kafka, stomp, mongodb]
toc:  true
---

In this research, I aimed at a streamlined architecture that can support a huge amount of data using NoSQL and Kafka inside a strange world which I don’t have much experience in the real world. The streaming pipeline is a little bit different from batch, however, at the same time is almost the same idea (at least for me).

## Technical solution

Design of the architecture:

![](/imgs/ks1.png)

## Requirements

To use this repo, you will need the following:

- Clone this repository to your local machine.
- Install the libraries: pykafka, pymongo, stomp-py, requests, xmltodict.
- Register on the dataset provider: https://opendata.nationalrail.co.uk.
- Docker compose.

## Docker Compose

![](/imgs/ks2.png)

## Kafka

First step after the docker mount is to create the Kafka Topics.

![](/imgs/ks3.png)

## Configuration file

Configure the file with the user & token provided by the National Rail open data:

![](/imgs/ks4.png)

## Streaming it!

This is a simple code that reads from the Queue and send it to MongoDB and Kafka Topic.

![](/imgs/ks5.png)
![](/imgs/ks6.png)

## Testing - Result

![](/imgs/ks7.gif)





## More

- GitHub Repo **[here](https://github.com/lucnietoX/Kafka-stream/)**.