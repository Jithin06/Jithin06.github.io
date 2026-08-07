---
layout: page
title: Academia
description: Node.js | React | MongoDB | AWS Lambda | Textract
img: assets/img/9.jpg
importance: 1
category: software
related_publications: false
---

A full-stack platform that helps students discover professors by research interest, and summarizes the papers behind that research on demand.

#### Search

The core is a Node.js/Express REST API with a React/Vite frontend. I integrated **Typesense** for fuzzy, synonym-aware search over research interests, which cut query latency by roughly 10x compared to the previous approach.

#### Event-driven summarization

Paper summarization runs as an asynchronous pipeline rather than a blocking request:

1. An **API Gateway** trigger invokes a Lambda that checks **DynamoDB** for an existing summary.
2. If none exists, the request is queued on **SQS** — so duplicate requests for the same paper never trigger duplicate processing.
3. A second Lambda extracts text from the uploaded PDF with **Amazon Textract**, summarizes it with the Hugging Face **BART** model, and writes both the result and its status back to DynamoDB.

The status field lets the frontend poll for progress instead of holding a connection open for the length of a model run.
