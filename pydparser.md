# Resume Parser in Spanish

## Introduction

This project aims to construct an open source resume parser for spanish resumees.

### Features

- Extract name, email, phone number, and other contact information from resume.
- Extract skills, experience, education, and other relevant information from resume.
- Extract job title, company name, and other relevant information from resume.
- Extract keywords from resume.
- Extract date of birth from resume.
- Extract location from resume.

The resume does not extract gender or age, to be etically correct.


## Project

### Dataset

The dataset used for training and testing the model is a collection of xxxx spanish resumees.

1. Search of documents and relocation.
2. Text extraction from pdf.
3. Annotation CV / Not CV from texts using [pigeonXT](https://github.com/dennisbakhuis/pigeonXT)
    - *obs*: many names are written like *J J U U A A N N* or *J U A N*. How would we extract the name? Others are capitalized.
4. Cleaning of the text.
5. NER annotation.
    - For this we came up with the following tags: *Name*, *Email*, *Phone*, *Job Title*, *Company Name*, *Skill*, *Experience*, *Education*, *Keyword*, *Date of Birth*, *Location*.
6. Training of the model.
7. Evaluation of the model.