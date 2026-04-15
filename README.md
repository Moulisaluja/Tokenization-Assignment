# NLP Text Preprocessing Pipeline

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-orange.svg)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

## Overview

This project implements a **Natural Language Processing (NLP) preprocessing pipeline** as part of an assignment.

The goal is to transform raw textual data (reviews) into a structured and clean format suitable for further analysis.

---

## Objectives

* Convert text to lowercase
* Remove punctuation
* Tokenize text
* Remove stopwords

---

## Dataset

* Format: CSV (`reviews.csv`)
* Each row represents a **single review**

> ⚠️ Note: Each review may contain multiple sentences.
> The preprocessing pipeline is applied to the **entire review as a single unit**, not sentence-by-sentence.

---

## Approach

The preprocessing pipeline is applied **individually to each review** in the dataset.

---

### Step 1: Lowercasing

All text is converted to lowercase to ensure consistency.

```text
"Live" → "live"
```

---

### Step 2: Tokenization

We use `wordpunct_tokenize` to split text into words and punctuation.

```text
"Hello!!!" → ['Hello', '!', '!', '!']
```

---

### Step 3: Removing Punctuation

Punctuation tokens are removed using `string.punctuation`.

```text
['Hello', '!', '!', '!'] → ['Hello']
```

---

### Step 4: Stopword Removal

Common words (such as *is, the, and*) are removed using NLTK stopwords.

```python
from nltk.corpus import stopwords
stopwords.words('english')
```

These words do not contribute significant meaning and are removed to focus on important words.

---

## Pipeline Flow

```text
Raw Review
   ↓
Lowercase Conversion
   ↓
Tokenization (wordpunct_tokenize)
   ↓
Remove Punctuation
   ↓
Remove Stopwords
   ↓
Final Clean Tokens
```

---

## Example Walkthrough

We demonstrate the preprocessing pipeline using a sample review from the dataset:

### Input Review

```text
I don't like this item. It is bad.
```

---

### Step-by-Step Transformation

#### 1️⃣ Lowercasing

```text
i don't like this item. it is bad.
```

---

#### 2️⃣ Tokenization

```text
['i', 'don', "'", 't', 'like', 'this', 'item', '.', 'it', 'is', 'bad', '.']
```

---

#### 3️⃣ Removing Punctuation

```text
['i', 'don', 't', 'like', 'this', 'item', 'it', 'is', 'bad']
```

---

#### 4️⃣ Removing Stopwords

```text
['like', 'item', 'bad']
```

---

### Final Output

```text
['like', 'item', 'bad']
```

---

## Output Structure

| Column Name  | Description                       |
| ------------ | --------------------------------- |
| review       | Original text                     |
| lowercase    | Lowercased text                   |
| tokens       | Tokenized output                  |
| no_punct     | Tokens after removing punctuation |
| final_tokens | Tokens after removing stopwords   |

---

## Tech Stack

* Python
* Pandas
* NLTK

---

## Future Scope

This preprocessing pipeline serves as the foundation for:

### Sentiment Analysis Mini Project

* Classify reviews as **Positive** or **Negative**
* Use cleaned tokens for analysis
* Apply rule-based or machine learning techniques

---

## Conclusion

This project demonstrates how raw text data can be systematically cleaned and transformed into meaningful tokens. It forms the base for more advanced NLP tasks such as sentiment analysis and text classification.

---

## Author

Developed as part of an NLP assignment to understand preprocessing techniques and pipeline design.


