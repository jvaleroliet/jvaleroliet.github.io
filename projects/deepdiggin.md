---
layout: page
title: Deep Diggin
---


<img src="{{ site.baseurl }}/images/deepdiggin-large.png?raw=true" width="1000"/>


# A Machine Learning Approach to Vinyl Record Grading

## Introduction

Imagine buying a 'Near Mint' vinyl record online, only to discover it has distracting crackles upon arrival. Inconsistent vinyl grading is a constant frustration for collectors, sellers, and enthusiasts alike. Traditional methods rely on subjective human judgment, leading to discrepancies and misrepresented quality.

This project introduces **Deep Diggin**, a machine learning solution that automates vinyl record grading based on the [Goldmine Grading System](https://www.goldminemag.com/collector-resources/record-grading-101). By analyzing audio samples, Deep Diggin provides objective and consistent evaluations, offering several benefits:

- **Collectors**: Gain confidence in purchasing decisions, knowing the vinyl's true condition.
- **Sellers**: Attract more buyers by accurately representing the quality of records. Gain efficiency and accuracy in the grading process.
- **Marketplaces**: Reduce the risk of grading errors and enhance customer trust.

Deep Diggin aims to be a fresh solution, with the state-of-the art Machine Learning architectures. We'll delve into the project's details, showcasing a robust model, a user-friendly application, and exploring exciting possibilities for future enhancements.


## Data Acquisition and preparation
### Data Sources
The primary dataset was constructed by scraping product listings from eBay. {::comment}should include To ensure data diversity, records from various genres and release years were included. While these platforms offer a vast collection, there might be biases towards popular artists and recent releases. {:/comment}

### Data Collection Process
A custom web scraping script was developed to extract relevant information including record titles, artists, condition descriptions, and audio links. The process encountered challenges such as handling dynamic website elements and inconsistencies in data format. To address these, a robust data cleaning and standardization process was implemented.

### Data Preprocessing
Extracted audio files underwent format standardization. To enhance model performance, audio clips were divided into segments to capture variations in record condition across different parts of the vinyl. The dataset was then partitioned into training and testing sets for model development and evaluation. {::comment} ensuring a balanced distribution of record conditions{:/comment}.

## Model Development
### Understanding the Problem
Vinyl record grading is a multi-class classification task aiming to predict the condition of a vinyl record based on its audio content. The Goldmine Grading System provides a standardized framework for categorizing record conditions.

### Model Architecture
A pre-trained **Wav2Vec2** model (facebook/wav2vec2-base) was fine-tuned to create a specialized model named wav2vec2-base-vinyl_condition. This approach leverages the model's ability to extract meaningful audio representations, eliminating the need for manual feature engineering.

### Model Training and Evaluation
The fine-tuning process involved training the model on a dataset of vinyl record audio samples labeled with their corresponding Goldmine grades. To assess the model's performance, metrics such as accuracy, precision, recall, and F1-score were calculated on a held-out validation set.

The model achieved an accuracy of 0.5747, F1-score of 0.3691, recall of 0.3745, and precision of 0.4017 on the validation set. These results indicate that the model struggles to accurately classify vinyl records, particularly in terms of precision and recall. Potential factors contributing to this performance include data imbalance, limited dataset size, and the complexity of distinguishing subtle audio differences between record conditions.

To address these challenges, the following strategies are currently being explored: data augmentation, feature engineering, hyperparameter tuning, experimentation with different model architectures, and ensemble methods.

## Gradio App
To provide a user-friendly interface for accessing the model's capabilities, a Gradio app was developed. The app allows users to upload an audio clip of a vinyl record, and the model predicts its condition based on the Goldmine Grading System. The app provides a clear and intuitive interface, making it accessible to users with varying technical backgrounds.

<script
	type="module"
	src="https://gradio.s3-us-west-2.amazonaws.com/4.37.2/gradio.js"
></script>

<gradio-app src="https://jvalero-vinyl-classificator.hf.space"></gradio-app>


Future enhancements include incorporating additional features like visual inspection of the vinyl and cover.