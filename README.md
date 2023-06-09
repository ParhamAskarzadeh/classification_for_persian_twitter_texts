# Persian Twitter Text Normalization and Classification

This code performs text normalization and classification on Twitter data using various techniques. It includes the following steps:

## Prerequisites

- pandas
- numpy
- openpyxl
- sklearn

Install the required packages using pip:

```bash
!pip install pandas numpy openpyxl sklearn
```

## Data Preparation

1. Read the Twitter data from an Excel file named `twitter.xlsx` using `pd.read_excel`.
2. Read the emoji data from a CSV file named `ijstable.csv` using `pd.read_csv`.
3. Prepare the emoji dictionary based on the emoji data.

## Text Normalization

The `NormalizerOfTwitter` class provides methods to perform different text normalization techniques:

- URL normalization: Replace URLs with `||url||`.
- Username normalization: Replace usernames with `||target||`.
- Repeated characters normalization: Reduce repeated characters to two occurrences.
- HTML tag removal: Remove HTML tags from the text.
- Negation normalization: Replace negation words with `||not||`.
- Acronym normalization: Normalize specific acronyms.
- Emoji normalization: Replace emojis with their corresponding sentiment tags.
- Additional space removal: Remove excessive spaces.

Apply all the above normalization filters to the Twitter data using the `apply_all_filter` method.

## Data Encoding

- Encode the target variable ('رویکرد') using `LabelEncoder` from sklearn.
- Split the normalized text into tokens.

## Feature Extraction

Use the `CountVectorizer` from sklearn to extract the Bag-of-Words (BoW) features from the normalized text.

## Model Training and Evaluation

- Split the dataset into training and testing sets using `train_test_split` from sklearn.
- Train a Multinomial Naive Bayes model on the training data.
- Make predictions on the test data and evaluate the model using accuracy and classification report.

## Results

The accuracy of the trained model on the test data is approximately 0.57. The classification report provides precision, recall, and F1-score for each class.

```
Accuracy: 0.5667396061269147
              precision    recall  f1-score   support

           0       0.57      0.75      0.65       216
           1       0.43      0.41      0.42        85
           2       0.68      0.39      0.50       156

    accuracy                           0.57       457
   macro avg       0.56      0.52      0.52       457
weighted avg       0.58      0.57      0.55       457
```
