# deepdiggin

## Introduction

This project aims to construct an open source package to classify vinyl according to the [Goldmine Grading](https://www.goldminemag.com/collector-resources/record-grading-101).

The package is constructed with a finetuned version of [facebook/wav2vec2-base](https://huggingface.co/facebook/wav2vec2-base).

### Features

- Obtain grading condition from an audio clip of the vinyl.

Future features:

- Obtain visual grading condition from a photo of the vinyl.
- Obtain visual grading condition of the cover from a photo of it.


## Project

The main steps of the project included:

1. Scraping watchcount to create a database of selled records and links to ebay items.
2. Scraping ebay items and obtain audio and and the vinyl condition "raw".
3. Labeling the audios from this "raw" conditions.
4. Audio exploration and cutting to separate the different sides of the records.
5. Preparing the dataset.
6. Finetuning the model.
7. Evaluation of its performance.
8. Creating the python application for production.


