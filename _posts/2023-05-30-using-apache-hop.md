---
layout: post
title: Using Apache Hop!
date: 2023-05-30 23:01 +0000
last_modified_at: 2023-05-30 23:11 +0000
tags: [apache-hop, etl, docker]
toc:  true
---

This use case was created from an idea to have an integration data tool for a small company, for instance.
Therefore, it is possible to use Apache Hop to integrate different kinds of systems and data.

# About Apache Hop
Apache Hop is an open-source data integration platform that provides a flexible and extensible environment for designing, orchestrating, and executing data integration workflows. It offers a wide range of connectors, transformations, and job execution capabilities, making it suitable for diverse integration scenarios.

# Objective
The purpose of this project is to showcase how Apache Hop can be utilized to enable seamless integration across different systems and data types. By leveraging its extensive set of features, users can easily connect, transform, and load data from multiple sources, enabling efficient data processing and analysis.

# Concepts
**Metadata** is by far the most important concept in all of Hop. Every item we’ll cover below is defined as metadata. 
All interactions between Hop and other components in your data architecture are done through metadata. 
### Metadata is at the core of everything in Hop.
- **Pipelines** are collections of transforms, connected by hops. All transforms in a pipeline run in parallel.
- **Workflows** are collections of actions, connected by hops. All actions in a workflow run sequentially by default.
- **Projects** are logical collections of hop code and configuration. Environments contain the environment-specific (e.g. dev, uat, prd) metadata.

# Installation
To get started with this project, follow the steps below:

1. Clone this repository to your local machine and install the libraries:
   git clone https://github.com/lucnietoX/di-apachehop-postgresql.git
   
2. Perform access permissions into all ports
3. Execute docker composer & pipelines

# Docker file
![data](/imgs/hop1.png)

# Source
Kaggle dataset - Amazon Product: https://www.kaggle.com/datasets/promptcloud/amazon-product-dataset-2020?resource=download