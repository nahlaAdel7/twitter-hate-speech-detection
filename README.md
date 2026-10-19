# Twitter Hate Speech Detection

## Project Overview

This project uses Natural Language Processing (NLP) and Machine Learning to classify tweets into two categories:

* **0:** Tweet does not belong to the targeted hate speech category.
* **1:** Tweet belongs to the targeted category.

The goal is to identify potentially harmful content in tweets using text preprocessing and machine learning techniques.

## Dataset

The project uses the Twitter Hate Speech dataset from Analytics Vidhya.

* **Training data:** 31,962 tweets
* **Test data:** 17,197 tweets
* **Target variable:** `label`
* **Class distribution:** The dataset is imbalanced, with approximately 7% positive samples.

The dataset files are not included in this repository. Obtain the original dataset from its source and place `train.csv` and `test_tweets.csv` in the project directory before running the notebook.

## Technologies Used

* Python
* Pandas
* Scikit-learn
* Regular Expressions (`re`)
* Jupyter Notebook

## Methodology

### 1. Text Preprocessing

* Converted tweets to lowercase.
* Replaced URLs and user mentions with placeholders.
* Removed the `#` symbol while preserving hashtag words.
* Removed the `RT` retweet marker.
* Normalized extra whitespace.

### 2. Feature Extraction

Used **TF-IDF (Term Frequency–Inverse Document Frequency)** to transform tweet text into numerical features.

Both word-level and character-level TF-IDF features were combined to capture useful text patterns.

### 3. Model Training

Trained a **Logistic Regression** classifier using balanced class weights to help address class imbalance.

### 4. Model Evaluation

Compared different regularization settings using a stratified validation split and evaluated performance using the F1-score for class 1.

**Best validation F1-score: 0.7328**

This score is from the validation set and is not a final test-set evaluation score.

## How to Run

1. Clone or download this repository.

2. Install the required packages:

   ```bash
   pip install pandas scikit-learn jupyter
   ```

3. Obtain the dataset files and place them in the same directory as the notebook:

   * `train.csv`
   * `test_tweets.csv`

4. Open `Twitter_Hate_Speech_Detection.ipynb` in Jupyter Notebook.

5. Run the notebook cells in order.

## Project Structure

```text
twitter-hate-speech-detection/
├── Twitter_Hate_Speech_Detection.ipynb
├── README.md
└── .gitignore
```

## Future Improvements

* Experiment with additional NLP techniques and classification models.
* Tune the classification threshold to explore precision and recall trade-offs.
* Evaluate model generalization on additional datasets.

## Author

**Nahla Adel**
