# Analysis of YouTube Comments on Kaesang and Erina's Wedding Using Topic Modeling

A topic modeling research project using Latent Dirichlet Allocation (LDA) to analyze public discourse and sentiment around the wedding of Kaesang Pangarep and Erina Gudono through YouTube comments.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![LDA](https://img.shields.io/badge/Topic%20Modeling-LDA-orange)](https://en.wikipedia.org/wiki/Latent_Dirichlet_allocation)

## 📋 Overview

This research analyzes public opinion and discourse regarding the wedding of Kaesang Pangarep (son of Indonesian President Joko Widodo) and Erina Gudono by examining YouTube comments using Latent Dirichlet Allocation (LDA) topic modeling. The study identifies hidden themes and patterns in public commentary to understand societal perspectives on this high-profile event.

### Key Findings

- **Number of Topics**: 2 main topics identified
- **Best Model**: 2-topic LDA with perplexity score of -5.876
- **Main Topics**: 
  - **Topic 0**: "Doa" (Prayers and well-wishes)
  - **Topic 1**: "Keluarga" (Family and presidential connections)
- **Keywords**: "Pernikahan Kaesang" (Kaesang's Wedding)

## 🎯 Research Objectives

1. Analyze public opinion on Kaesang and Erina's wedding through YouTube comments
2. Apply LDA topic modeling to identify hidden thematic structures
3. Use qualitative analysis to interpret and label discovered topics
4. Visualize big data from social media to understand public sentiment

## 🔬 Methodology

### Data Collection
- **Source**: YouTube comments from multiple videos
- **Keyword**: "Pernikahan Kaesang" (Kaesang's Wedding)
- **Videos Analyzed**: 23 videos related to the wedding
- **Method**: Web scraping of public comments

### Data Preprocessing

The preprocessing pipeline consists of four main techniques:

1. **Data Cleaning**
   - Remove newlines (`\n`) and convert to empty strings
   - Remove punctuation: `!,-./:;<=>?@[\]^_`{|}~"#$%&'()*+`
   - Convert all text to lowercase
   - Handle missing values, noisy data, and inconsistent data

2. **Tokenization**
   - Split sentences into individual words
   - Example: "Selamat menempuh hidup baru untuk mas Kaesang" → 
     `[selamat, menempuh, hidup, baru, untuk, mas, kaesang]`

3. **Stopword Removal**
   - Remove common Indonesian words without semantic meaning
   - Examples: "yang", "dan", "di", "dari", etc.
   - Reduces noise in text analysis

4. **Lemmatization**
   - Reduce word variations to their root forms
   - Convert active/passive voice to base words
   - Standardize word representations

#### Preprocessing Example

| Stage | Result |
|-------|--------|
| Original | Selamat Raden kaisang sama mbak Erina.. semuga cepat dapat momongan yang Sholeh dan Sholeh |
| Data Cleaning | selamat raden kaisang sama mbak erina semuga cepat dapat momongan yang sholeh dan sholeh |
| Tokenize | ['selamat', 'raden', 'kaisang', 'sama', 'mbak', 'erina', 'semuga', 'cepat', 'dapat', 'momongan', 'yang', 'sholeh', 'dan', 'sholeh'] |
| Stopwords | ['selamat', 'raden', 'kaisang', 'mbak', 'erina', 'semuga', 'cepat', 'momongan', 'sholeh', 'sholeh'] |
| Lemmatizing | selamat raden kaisang mbak erina semuga cepat momong sholeh sholeh |

### Topic Modeling: Latent Dirichlet Allocation (LDA)

LDA is a probabilistic topic modeling method that:
- Discovers hidden thematic structures in comment collections
- Models comments as probabilistic mixtures of topics
- Each topic has a probability distribution over words
- Uses generative process through imaginary random process
- Automatically determines topic distributions

**Why LDA?**
- Unsupervised learning (no labeled data required)
- Works like clustering but more specific to text
- Finds abstract topic patterns in data collections
- Reduces processing complexity (5 topics × 500 words = 2,500 threads vs. 1,000 docs × 500 words = 500,000 threads)

## 📊 Results

### Model Performance

The study evaluated LDA models with different numbers of topics using **perplexity** as the evaluation metric. Lower perplexity indicates better model performance.

**Perplexity Scores by Number of Topics:**

| Number of Topics | Perplexity Score |
|------------------|------------------|
| 2 | -5.876 |
| 3 | -5.952 |
| 4 | -6.064 |
| 5 | -6.164 |
| 6 | -6.208 |
| 7 | -6.388 |
| 8 | -6.359 |
| 9 | -6.416 |
| 10 | -6.488 |

**Best Model**: 2-topic LDA with the lowest perplexity score of **-5.876**

### Topic Analysis

#### **Topic 0: "Doa" (Prayers)**

| Theme | Marginal Distribution |
|-------|----------------------|
| mas_kaesang | 0.024 |
| ya | 0.020 |
| keluarga | 0.020 |
| yg | 0.020 |
| **moga** | **0.020** |
| banget | 0.017 |
| **anak** | **0.015** |
| **selamat** | **0.014** |
| mas | 0.013 |

**Interpretation**: This topic represents well-wishes and prayers from the public. The presence of words like "moga" (hopefully), "anak" (child), and "selamat" (congratulations) indicates that most commenters are offering prayers and blessings for the couple's marriage.

#### **Topic 1: "Keluarga" (Family)**

| Theme | Marginal Distribution |
|-------|----------------------|
| yg | 0.036 |
| **jokowi** | **0.022** |
| **mas_kaesang** | **0.021** |
| bahagia | 0.020 |
| **kaesang** | **0.016** |
| nikah | 0.015 |
| moga | 0.014 |
| **keluarga** | **0.013** |
| selamat | 0.012 |

**Interpretation**: This topic highlights the family connection, particularly to President Jokowi. The prominence of "Jokowi" (0.022), "mas_kaesang" (0.021), "kaesang" (0.016), and "keluarga" (family, 0.013) shows that the public is highly focused on the presidential family aspect of this wedding.

### Key Insights

1. **Public Sentiment**: The dominant topic is well-wishes and prayers, indicating positive public sentiment
2. **Presidential Connection**: Significant attention to the family's political prominence
3. **Cultural Values**: Comments reflect Indonesian cultural values of offering prayers and blessings for newlyweds
4. **Public Interest**: The wedding received substantial public attention due to its political significance

## 🛠️ Technical Stack

- **Language**: Python 3.8+
- **Topic Modeling**: Latent Dirichlet Allocation (LDA)
- **NLP Library**: NLTK (Natural Language Toolkit)
- **Data Processing**: Pandas, NumPy
- **LDA Implementation**: Gensim
- **Preprocessing**: 
  - Tokenization
  - Stopword removal
  - Lemmatization
  - Data cleaning techniques

## 📈 Data Characteristics

- **Source Platform**: YouTube
- **Number of Videos**: 23 videos
- **Search Keyword**: "Pernikahan Kaesang"
- **Comment Language**: Indonesian (Bahasa Indonesia)
- **Processing Stages**: 4 (Cleaning, Tokenizing, Stopwords, Lemmatizing)
- **Optimal Topic Count**: 2 topics

## 🎓 Authors

- **Ade Cahyaning Palupi** (105220001) - Universitas Pertamina
- **Kristine Angelina Simanjuntak** (105220009) - Universitas Pertamina
- **Angelia Regina Dwi Kartika** (105220039) - Universitas Pertamina
- **Yolla Putri Ervanisari** (105220049) - Universitas Pertamina

## 📄 Publication Information

- **Institution**: Ilmu Komputer, Universitas Pertamina
- **Location**: Jakarta, Indonesia
- **Year**: 2024

## 🔍 Research Context

### Big Data and YouTube Analytics

YouTube is the world's second-largest search engine with over 1 billion active users. This research demonstrates how big data analytics can be applied to social media platforms to:
- Extract meaningful insights from unstructured text data
- Understand public opinion on significant social events
- Support decision-making processes through data visualization
- Reveal hidden patterns in large-scale comment datasets

### Why Topic Modeling?

Topic modeling simplifies analysis by:
- Reducing computational complexity
- Extracting semantic themes automatically
- Providing interpretable results
- Handling large-scale text data efficiently

## 📚 References

- Andry, J.F., Tannady, H., Limawal, I.I., Rembulan, G.D., & Marta, R.F. (2021). "Big Data Analysis on YouTube with Tableau"
- Blei, D.M., Ng, A.Y., and Jordan, M.I. (2003). "Latent Dirichlet Allocation," Journal of Machine Learning Research, vol. 3, pp. 993-1022
- Ekinci, E., & İlhan Omurca, S. (2019). "Concept-LDA: Incorporating Babelfy into LDA for aspect extraction," Journal of Information Science, 46, 406-418
- Manyika, J. (2011). "Big Data: The next frontier for innovation, competition, and productivity"

## 💡 Future Applications

This methodology can be applied to similar research in different contexts:
- Political events and public sentiment
- Product launches and consumer feedback
- Entertainment and celebrity events
- Policy announcements and public reaction
- Brand reputation monitoring

## 📧 Contact

For questions or collaborations, please contact the research team at Universitas Pertamina, Jakarta, Indonesia.

---

**Keywords**: YouTube Comments, Topic Modeling, LDA, Latent Dirichlet Allocation, Big Data, NLP, Indonesian Text Analysis, Social Media Analytics, Public Opinion, Presidential Family, Wedding Analysis
