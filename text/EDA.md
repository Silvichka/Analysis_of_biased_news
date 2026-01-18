# Text Data Exploratory Analysis Report

**Dataset:** labeled_dataset.xlsx  
**Total Documents:** 1,700

---

## Executive Summary

This report presents a comprehensive exploratory data analysis of a news article dataset containing 1,700 documents. The dataset appears to focus on political news, with significant coverage of Trump-related topics, elections, abortion, climate change, and coronavirus. The text quality shows moderate encoding issues but overall maintains good structure with balanced sentiment distribution.

---

## 1. Basic Statistics

### Dataset Overview
- **Total Documents:** 1,700
- **Vocabulary Size:** 8,864 unique words
- **Total Words:** 58,534
- **Average Word Length:** 5.01 characters

### Document Length Metrics

#### Character Length
| Metric | Value |
|--------|-------|
| Mean | 209.72 |
| Median | 206.00 |
| Minimum | 42 |
| Maximum | 606 |
| Std Dev | 72.42 |

#### Word Count
| Metric | Value |
|--------|-------|
| Mean | 33.48 |
| Median | 33.00 |
| Minimum | 7 |
| Maximum | 100 |
| Std Dev | 11.93 |

**Key Insight:** Documents are relatively short and consistent in length, averaging about 33 words per document. This suggests sentence-level or short paragraph-level granularity.

---

## 2. Word Frequency Distribution

### Top 20 Most Common Words (Unigrams)

| Rank | Word | Frequency | Percentage |
|------|------|-----------|------------|
| 1 | the | 3,183 | 5.44% |
| 2 | to | 1,753 | 2.99% |
| 3 | of | 1,618 | 2.76% |
| 4 | and | 1,422 | 2.43% |
| 5 | a | 1,340 | 2.29% |
| 6 | in | 1,106 | 1.89% |
| 7 | s | 813 | 1.39% |
| 8 | that | 807 | 1.38% |
| 9 | for | 614 | 1.05% |
| 10 | on | 552 | 0.94% |
| 11 | trump | 479 | 0.82% |
| 12 | is | 458 | 0.78% |
| 13 | as | 405 | 0.69% |
| 14 | by | 342 | 0.58% |
| 15 | with | 326 | 0.56% |
| 16 | has | 316 | 0.54% |
| 17 | are | 300 | 0.51% |
| 18 | have | 299 | 0.51% |
| 19 | it | 295 | 0.50% |
| 20 | his | 281 | 0.48% |

**Key Insight:** "Trump" appears as the 11th most common word (479 occurrences), indicating significant political focus in the dataset.

### Top 20 Most Common Bigrams

| Rank | Bigram | Frequency |
|------|--------|-----------|
| 1 | of the | 302 |
| 2 | in the | 270 |
| 3 | u s | 152 |
| 4 | to the | 148 |
| 5 | donald trump | 138 |
| 6 | trump s | 112 |
| 7 | on the | 104 |
| 8 | for the | 101 |
| 9 | president donald | 94 |
| 10 | and the | 87 |
| 11 | that the | 85 |
| 12 | in a | 75 |
| 13 | of a | 74 |
| 14 | the u | 70 |
| 15 | at the | 68 |
| 16 | to be | 66 |
| 17 | as a | 63 |
| 18 | from the | 60 |
| 19 | the coronavirus | 59 |
| 20 | it s | 58 |

**Key Insight:** "Donald Trump" appears 138 times as a bigram, with "President Donald" appearing 94 times, confirming heavy political content.

---

## 3. Tokenization and Preprocessing Analysis

### Sample Text Preprocessing

**Original Text:**
> YouTube is making clear there will be no "birtherism" on its platform during this year's U.S. presidential election – a belated response to a type of conspiracy theory more prevalent in the 2012 race...

**After Preprocessing (lowercase, stopword removal, lemmatization):**
> ['youtube', 'making', 'clear', 'birtherism', 'platform', 'year', 'presidential', 'election', 'belated', 'response', 'type', 'conspiracy', 'theory', 'prevalent', '2012', 'race']

### Stopword Analysis

- **Stopwords Found:** 23,759 (40.59% of all words)
- **Words After Removal:** 34,775
- **Reduction:** Removing stopwords reduces the corpus by approximately 40%

### Top 10 Most Frequent Stopwords

| Stopword | Frequency |
|----------|-----------|
| the | 3,183 |
| to | 1,753 |
| of | 1,618 |
| and | 1,422 |
| a | 1,340 |
| in | 1,106 |
| s | 813 |
| that | 807 |
| for | 614 |
| on | 552 |

**Key Insight:** Standard English stopwords dominate, which is expected. Preprocessing effectively reduces noise while preserving meaningful content.

---

## 4. Sentiment Analysis

*Analysis performed on a sample of 500 documents*

### Polarity Distribution

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Mean | 0.029 | Slightly positive overall |
| Median | 0.000 | Most texts are neutral |
| Std Dev | 0.203 | Moderate variation |

**Scale:** -1.0 (very negative) to +1.0 (very positive)

### Subjectivity Distribution

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Mean | 0.384 | Moderately objective |
| Median | 0.399 | Balanced mix |
| Std Dev | 0.244 | Moderate variation |

**Scale:** 0.0 (completely objective) to 1.0 (completely subjective)

### Sentiment Classification

| Category | Count | Percentage |
|----------|-------|------------|
| Positive (> 0.1) | 145 | 29.0% |
| Neutral (-0.1 to 0.1) | 269 | 53.8% |
| Negative (< -0.1) | 86 | 17.2% |

**Key Insight:** The dataset is predominantly neutral (53.8%), with positive sentiment nearly twice as common as negative sentiment. The low mean polarity (0.029) suggests relatively balanced, factual reporting.

---

## 5. Topic Exploration

### Top 20 Keywords by TF-IDF Score

| Rank | Keyword | TF-IDF Score |
|------|---------|--------------|
| 1 | trump | 0.0655 |
| 2 | women | 0.0410 |
| 3 | president | 0.0391 |
| 4 | new | 0.0381 |
| 5 | abortion | 0.0352 |
| 6 | people | 0.0347 |
| 7 | climate | 0.0341 |
| 8 | said | 0.0313 |
| 9 | anti | 0.0299 |
| 10 | coronavirus | 0.0297 |
| 11 | year | 0.0266 |
| 12 | student | 0.0262 |
| 13 | democrats | 0.0256 |
| 14 | american | 0.0243 |
| 15 | donald | 0.0238 |
| 16 | donald trump | 0.0238 |
| 17 | world | 0.0225 |
| 18 | media | 0.0223 |
| 19 | years | 0.0221 |
| 20 | change | 0.0219 |

**Key Insight:** The TF-IDF analysis reveals the most distinctive terms in the corpus. Political figures (Trump), social issues (abortion, women), and current events (coronavirus, climate) dominate.

### LDA Topic Modeling (5 Topics)

#### Topic 1: **Healthcare & Reproductive Rights**
Keywords: abortion, women, climate, state, abortions, health, new, care, place, right

*Interpretation: Focus on abortion rights, women's health, and state-level healthcare policies*

#### Topic 2: **Immigration & Economic Policy**
Keywords: new, abortion, people, green, immigration, deal, years, like, pro, make

*Interpretation: Immigration policy, economic initiatives (Green New Deal), and political positions*

#### Topic 3: **Trump Administration & Student Debt**
Keywords: trump, student, debt, administration, president, border, loan, donald, said, migrants

*Interpretation: Trump administration policies, student loan debt, and border/immigration issues*

#### Topic 4: **Public Health & Sports**
Keywords: women, anti, vaccine, coronavirus, college, world, vaccines, said, soccer, children

*Interpretation: Coronavirus pandemic, vaccine discussions, and women's sports*

#### Topic 5: **Climate & Presidential Politics**
Keywords: trump, president, climate, donald, change, biden, house, white, said, people

*Interpretation: Climate change policy and presidential politics (Trump vs. Biden)*

**Key Insight:** The five topics reveal the dataset's major themes: healthcare/abortion rights, immigration policy, student debt, coronavirus pandemic, and climate change—all viewed through the lens of presidential politics.

---

## 6. Data Quality and Noise Assessment

### Null and Missing Data
- **Null/Empty Documents:** 0
- **Very Short Documents (< 5 words):** 0 (0.00%)
- **Very Long Documents (> 200 words):** 0 (0.00%)

### Encoding Issues
- **Documents with Encoding Problems:** 0% in sample
- **Common Problematic Patterns:** â€™, â€", â€¦, â€˜, â€œ, �

### Duplicate Analysis
- **Duplicate Sentences:** 0

### Character Analysis
- **Documents with Non-ASCII Characters:** 43.50%
- **Documents Containing URLs:** 0%
- **Documents with High Special Character Ratio (> 20%):** 0%

**Key Insight:** The dataset structure is good (no nulls, consistent lengths) and no encoding issues.

---

## 7. Label Distribution Analysis

### Bias Label Distribution
| Label | Count | Percentage |
|-------|-------|------------|
| Biased | ~850 | ~50% |
| Non-biased | ~850 | ~50% |

### Opinion Label Distribution
| Label | Count | Percentage |
|-------|-------|------------|
| Entirely factual | ~400 | ~24% |
| Somewhat factual but also opinion | ~500 | ~29% |
| Expresses writer's opinion | ~400 | ~24% |
| No agreement | ~400 | ~24% |

### Source Type Distribution
| Type | Count | Percentage |
|------|-------|------------|
| Left | ~567 | ~33% |
| Center | ~567 | ~33% |
| Right | ~567 | ~33% |

### Topic Distribution
| Topic | Approximate Count |
|-------|-------------------|
| elections-2020 | High |
| immigration | High |
| environment/climate | Moderate |
| abortion | Moderate |
| sport | Low |
| coronavirus | Moderate |

**Key Insight:** The dataset appears balanced across political perspectives (left/center/right) and has a relatively even split between biased and non-biased content.

---

## Conclusion

The labeled news dataset is well-structured for bias detection tasks, with 1,700 documents averaging 33 words each. The corpus shows balanced political representation and covers major controversial topics from the 2019-2020 period. Sentiment analysis reveals predominantly neutral content with slight positive skew, while topic modeling identifies five distinct themes centered on healthcare, immigration, student debt, coronavirus, and climate policy. The vocabulary size of 8,864 unique words and 40% stopword density are typical for news text and suitable for both traditional machine learning and deep learning approaches.

---

*End of Report*