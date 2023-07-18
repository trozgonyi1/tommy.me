---
title: How I created an AWS pipeline to generate and attach digital signatures to medial documents
date: 2022-08-06T10:00:25-04:00
summary: "Digitally signing documents with an AWS pipeline"
url: "/posts/projects/digital-signatures.md/"
showtoc: true
tags: ["AWS", "Python"]
draft: false
cover:
    image: /posts/tech/digital-signatures/pictures/aws.png
    alt: "pipeline diagram"
    caption: ""
---

This was a project I worked on from start to finish at [SMARTMD](https://www.smartmd.com/). If you would like to view the code for the Lambda function used, see [here]()

# Pipeline

## S3

The start of this pipeline began with an *S3 bucket*, where a ReactJS web app would upload a file. These files were all medical records of type pdf, jpg, or png.
The bucket is configured to trigger a *Lambda function*, passing the file to perform the processing.

## Lambda

oooo
