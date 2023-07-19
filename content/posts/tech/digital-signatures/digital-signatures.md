---
title: How I created an AWS pipeline to generate and attach digital signatures to medical documents
date: 2022-08-06T10:00:25-04:00
summary: "Digitally signing documents with an AWS pipeline"
url: "/posts/projects/digital-signatures.md/"
showtoc: true
tags: ["AWS", "Python"]
draft: false
cover:
    image: /tommy.me/posts/tech/digital-signatures/pictures/aws.png
    alt: "pipeline diagram"
    caption: ""
---

This was a project I worked on from start to finish at [SMARTMD](https://www.smartmd.com/). If you would like to view the code for the Lambda function used, see [here]()

# Pipeline

### `S3`

The start of this pipeline began with an *S3 bucket*, where a ReactJS web app uploads a file. These files are all medical records of type pdf, jpg, or png.
The bucket is configured to trigger a *Lambda function*, passing the file to perform the processing.

### `Lambda`

Once the file is passed to the Lambda function, OpenCV is used to extract the signature from the document. From there,
it is cleaned of any stray marks, straightened so it is not slanted, and scaled to fit a certain bounding box. Next, 
the a GUID and the company signature are applied above and below the signature as a watermark. Finally, the new file
is uploaded into another S3 bucket to be used by various web apps.

---


