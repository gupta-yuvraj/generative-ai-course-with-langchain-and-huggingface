
# Data Preprocessing with NLTK 

## Index

1. [Corpus, Document, Vocabulary, and Words](#corpus-document-vocabulary-and-words)
2. [Tokenization](#tokenization)
3. [Tokenization using NLTK](#tokenization-using-nltk)
4. [Stemming](#stemming)
5. [Lemmatization](#lemmatization)
6. [Stopwords](#stopwords)
7. [Parts of Speech (POS) Tagging](#parts-of-speech-pos-tagging)
8. [Named Entity Recognition (NER)](#named-entity-recognition-ner)
9. [Summary](#summary)

---

## Corpus, Document, Vocabulary, and Words

- **Corpus**: A large collection of text used for NLP tasks, like a database of articles or books.
- **Document**: A single text item within a corpus, such as an article or paragraph.
- **Vocabulary**: The set of all unique words across the corpus.
- **Words**: All words in the corpus, including duplicates.

---

## Tokenization

Tokenization is the process of breaking down text into smaller components called tokens. Tokens can be words, characters, or subwords. This step is crucial in NLP for converting raw text into a structured form suitable for analysis.

---

## Tokenization using NLTK

[NLTK (Natural Language Toolkit)](https://www.nltk.org/) is a popular Python library for NLP tasks.

### Installation

```bash
pip install nltk
```

### Download Required Data

```python
import nltk
nltk.download('punkt')
```

### Word Tokenization

```python
from nltk.tokenize import word_tokenize

text = "Natural Language Processing with NLTK is fun!"
tokens = word_tokenize(text)
print(tokens)
# Output: ['Natural', 'Language', 'Processing', 'with', 'NLTK', 'is', 'fun', '!']
```

### Sentence Tokenization

```python
from nltk.tokenize import sent_tokenize

text = "Hello there! How are you? NLP is interesting."
sentences = sent_tokenize(text)
print(sentences)
# Output: ['Hello there!', 'How are you?', 'NLP is interesting.']
```

### Custom Tokenization

```python
from nltk.tokenize import RegexpTokenizer

tokenizer = RegexpTokenizer(r'\w+')
tokens = tokenizer.tokenize("NLTK's tokenizers are customizable!")
print(tokens)
# Output: ['NLTK', 's', 'tokenizers', 'are', 'customizable']
```

---

## Stemming

Stemming reduces words to their base or root form.

```python
from nltk.stem import PorterStemmer

stemmer = PorterStemmer()
print(stemmer.stem("running"))  # Output: run
print(stemmer.stem("flies"))    # Output: fli
```

Stemming can sometimes produce non-words but is fast and effective.

---

## Lemmatization

Lemmatization also reduces words to their base form (lemma), but it uses vocabulary and morphological analysis.

```python
from nltk.stem import WordNetLemmatizer
nltk.download('wordnet')
nltk.download('omw-1.4')

lemmatizer = WordNetLemmatizer()
print(lemmatizer.lemmatize("running", pos="v"))  # Output: run
print(lemmatizer.lemmatize("flies", pos="n"))    # Output: fly
```

Lemmatization is more accurate than stemming but slightly slower.

---

## Stopwords

Stopwords are common words that are usually removed before analysis.

```python
from nltk.corpus import stopwords
nltk.download('stopwords')

stop_words = set(stopwords.words('english'))
words = word_tokenize("This is an example of stop word removal.")
filtered = [w for w in words if w.lower() not in stop_words]
print(filtered)
# Output: ['example', 'stop', 'word', 'removal', '.']
```

---

## Parts of Speech (POS) Tagging

POS tagging assigns grammatical categories to words (noun, verb, etc.).

```python
from nltk import pos_tag
nltk.download('averaged_perceptron_tagger')

tokens = word_tokenize("Natural Language Processing is fun")
tags = pos_tag(tokens)
print(tags)
# Output: [('Natural', 'JJ'), ('Language', 'NN'), ('Processing', 'NN'), ('is', 'VBZ'), ('fun', 'JJ')]
```

---

## Named Entity Recognition (NER)

NER identifies entities like names, organizations, and locations.

```python
from nltk import ne_chunk
from nltk.tree import Tree
nltk.download('maxent_ne_chunker')
nltk.download('words')

sentence = "Barack Obama was born in Hawaii."
tokens = word_tokenize(sentence)
tags = pos_tag(tokens)
tree = ne_chunk(tags)

for subtree in tree:
    if isinstance(subtree, Tree):
        print(subtree)
# Output: (PERSON Barack Obama)
```

---

## Summary

- **Tokenization**: Breaks text into tokens.
- **Stemming**: Reduces words to base form, might not be actual words.
- **Lemmatization**: More accurate base form, considers POS.
- **Stopwords**: Removes frequent, non-informative words.
- **POS Tagging**: Tags words with grammatical types.
- **NER**: Extracts named entities for understanding text context.

These preprocessing steps help transform raw text into a form suitable for NLP models.
