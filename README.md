
# RAG Employee Handbook

A Retrieval-Augmented Generation (RAG) system that allows users to ask questions about an employee handbook and receive answers based on the information retrieved from the document.

## Overview

This project demonstrates a basic RAG pipeline that combines document retrieval with a local Large Language Model (LLM).

The system processes an employee handbook, divides it into smaller chunks, converts the chunks into vector embeddings, and stores them in a FAISS vector database. When a user asks a question, the system retrieves the most relevant chunks and provides them as context to the LLM to generate the answer.

## RAG Pipeline

```text
Employee Handbook (PDF)
        ↓
Document Loading
        ↓
Text Chunking
        ↓
Sentence Transformer Embeddings
        ↓
FAISS Vector Store
        ↓
Similarity Retrieval
        ↓
Ollama LLM
        ↓
Generated Answer
```

## Technologies Used

- Python
- LangChain
- FAISS
- Sentence Transformers
- Ollama
- LLMs

## Features

- PDF document processing
- Text chunking with overlapping sections
- Semantic search using vector embeddings
- FAISS-based similarity retrieval
- Local LLM-based response generation
- Answers grounded in retrieved document content

## Example

**Question:** Are personal leaves paid?

The system retrieves the relevant sections from the employee handbook and uses the retrieved context to generate the answer.

## How It Works

1. The employee handbook is loaded and split into smaller chunks.
2. Each chunk is converted into a vector embedding using a Sentence Transformer model.
3. The embeddings are stored in a FAISS vector database.
4. When a question is asked, the system searches for the most relevant chunks.
5. The retrieved content is passed to the local LLM through the RAG prompt.
6. The LLM generates an answer based on the retrieved context.

## Note

This project was built as a practical implementation to understand the architecture and workflow of Retrieval-Augmented Generation systems.
