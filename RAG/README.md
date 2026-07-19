# RAG (Retrieval-Augmented Generation)

- Is an AI technique that combines information retrieval with a Large Language Model (LLM) to generate accurate, context-aware answers.

- RAG is a technique where an AI first retrieves relevant information from a knowledge base and then uses an LLM to generate an answer based on that retrieved information instead of relying only on its trained knowledge.

## How RAG works

```bash
User Question
      │
      ▼
Convert question into an embedding
      │
      ▼
Semantic Search in Vector Database
      │
Retrieve the most relevant chunks
      │
      ▼
Send Question + Retrieved Chunks to LLM
      │
      ▼
LLM generates the final answer
```

## Real-world example

- Imagine your company has an Employee Handbook.
- A user asks: "How many annual leaves do employees get?"
- Instead of expecting the LLM to know your company's policy:
  - The question is converted into an embedding.
  - A vector database finds the most relevant handbook sections.
  - Those sections are sent to the LLM as context.
  - The LLM answers: "According to your employee handbook, employees receive 20 paid annual leave days after completing one year of service."
- The answer is based on your company's document, not the model's memory.

## Why use RAG?

Without RAG:

- The model only knows what it learned during training.
- It may hallucinate.
- It cannot answer questions about your private documents.

With RAG:

- Uses your latest data.
- Answers from company documents.
- Reduces hallucinations.
- No need to retrain the model whenever documents change.

## Example pipeline

```bash
EmployeeHandbook.pdf
        │
        ▼
PDF Loader
        │
        ▼
Chunking
        │
        ▼
Embedding Model
        │
        ▼
Vector Database
        │
        ▼
──────────────────────────────────────
User asks a question
        │
        ▼
Embedding of Question
        │
        ▼
Semantic Search
        │
        ▼
Top 5 Relevant Chunks
        │
        ▼
Prompt:
Question
+
Retrieved Chunks
        │
        ▼
LLM
        │
        ▼
Final Answer
```
