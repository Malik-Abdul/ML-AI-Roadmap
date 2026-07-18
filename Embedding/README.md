# What is Embedding

## Easy-to-Remember Definition ⭐ (Recommended)

An embedding is the process of converting data (such as text, images, audio, or code) into a list of numbers (a vector) so that a computer can understand, compare, and search for similar data based on meaning rather than exact words.

## Interview Definition (Best)

An embedding is a dense numerical vector representation of data that captures its semantic meaning. Data with similar meanings have vectors that are closer together in the embedding space.

## One-Line Definition

Embedding converts data into vectors so computers can understand semantic meaning and measure similarity.

## Interview Explanation (30 seconds)

Computers cannot understand text or images directly. An embedding model converts the data into a numerical vector. Similar items produce similar vectors, allowing a vector database to find related information even when the wording or appearance is different.

### Example:

```bash
Text:
"I need a vacation."

↓

Embedding

↓

[0.12, -0.45, 0.89, ...]


Another sentence:
"I want a holiday."

↓

Embedding

↓

[0.11, -0.47, 0.91, ...]
```

Although the words are different, their vectors are close because their meanings are similar.

## To memorise

Embedding is the process of converting data (text, images, audio, code, etc.) into a dense numerical vector that captures its semantic meaning. Similar data produces similar vectors, making it possible for computers to perform semantic search, similarity comparison, and retrieval.

### Dense Numerical Vector

A dense numerical vector is a list of decimal numbers where every number contains useful information about the meaning of the data.

```bash
Example:

"The employee gets 20 vacation days."

↓

Embedding

↓

[0.23, -0.81, 1.45, 0.67, -0.12, ...]

# This list of numbers is called a dense numerical vector.
# Why is it called "Dense"? Because almost every value in the vector contains meaningful information.
# Dense Vector:
[0.42, -0.35, 0.91, 0.18, -0.74]
# Almost every position has a non-zero value.

# If most values were zero:
[0, 0, 0, 0, 15, 0, 0, 0]
# This is called a sparse vector, not a dense vector.

# So Dense numerical vector = A list of meaningful decimal numbers that represents data for AI models.
```

### Semantic Search

- Suppose your document contains:
- Employees receive 20 paid vacation days.
- User asks: How many holidays do employees get?
- Notice:
  - Document says vacation
  - User says holidays
- The words are different, but the meaning is the same.
- A keyword search might fail because it looks for the exact word "holidays".
- A semantic search succeeds because it understands that vacation and holidays are closely related in meaning.

### Keyword Search vs Semantic Search

| Keyword Search         | Semantic Search              |
| ---------------------- | ---------------------------- |
| Matches exact words    | Matches meaning              |
| "Vacation" ≠ "Holiday" | Understands they are similar |
| Traditional search     | AI-powered search            |

### Why embeddings are needed

```bash
Question
      ↓
Embedding

Document
      ↓
Embedding

Compare vectors

↓

Closest vector = Most similar meaning
# The vector database compares vectors, not the original text.
```

Dense Numerical Vector

A dense numerical vector is a list of decimal numbers that represents the meaning of data, where almost every value carries useful information.

Semantic Search

Semantic search finds information based on meaning rather than exact keyword matching.

## Techniques

One-Hot Encoding, Bag of Words, and TF-IDF are text representation techniques, but they are generally not considered modern embedding techniques.

| Technique             | Text Representation | Embedding? | Captures Meaning? |
| --------------------- | ------------------- | ---------- | ----------------- |
| One-Hot Encoding      | ✅ Yes              | ❌ No      | ❌ No             |
| Bag of Words (BoW)    | ✅ Yes              | ❌ No      | ❌ No             |
| TF-IDF                | ✅ Yes              | ❌ No      | ❌ Very little    |
| Word2Vec              | ✅ Yes              | ✅ Yes     | ✅ Yes            |
| GloVe                 | ✅ Yes              | ✅ Yes     | ✅ Yes            |
| FastText              | ✅ Yes              | ✅ Yes     | ✅ Yes            |
| BERT Embeddings       | ✅ Yes              | ✅ Yes     | ✅ Yes            |
| Sentence Transformers | ✅ Yes              | ✅ Yes     | ✅ Yes            |

### 1. One-Hot Encoding

- Represents each word as a binary vector.

- Vocabulary: ["cat", "dog", "bird"]

- Vectors:

```bash
cat → [1,0,0]
dog → [0,1,0]
bird → [0,0,1]
```

- Problems
  - Very sparse vectors.
  - Doesn't capture meaning.
  - "Cat" and "Dog" are equally unrelated as "Cat" and "Car".

### 2. Bag of Words (BoW)

- Represents a document by counting how many times each word appears.
- Example:

```bash
Document:

"I like AI. AI is amazing."

Vocabulary:

["I", "like", "AI", "is", "amazing"]

Vector:

[1,1,2,1,1]

```

Problems

- Ignores word order.
- Doesn't understand meaning.

### 3. TF-IDF

- Improves BoW by giving more importance to rare words and less importance to common words.
- Example:

```bash
"the"   → Low weight
"NestJS" → High weight
```

TF-IDF is useful for keyword-based search but still doesn't understand semantics like modern embeddings.

### Modern Embeddings

These are the techniques you should mention when someone asks about embedding models:

- Word2Vec
- GloVe
- FastText
- BERT
- Sentence-BERT (SBERT)
- E5
- BGE
- OpenAI Embeddings
- Hugging Face embedding models

These generate dense vectors that capture semantic meaning.
