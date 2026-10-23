# Employee Handbook RAG System

A Retrieval-Augmented Generation (RAG) project that answers questions about an employee handbook using document retrieval and a locally running language model.

## Overview

This project loads an employee handbook in PDF format, splits it into smaller text chunks, converts those chunks into embeddings, and stores them in a FAISS vector database. When a user asks a question, the system retrieves relevant content and uses a local language model to generate an answer grounded in the retrieved context.

## Technologies Used

- Python
- LangChain
- Ollama (`llama3.2:3b`)
- Sentence Transformers (`all-MiniLM-L6-v2`)
- FAISS
- Jupyter Notebook

## How It Works

1. Load the employee handbook PDF.
2. Split the document into chunks with overlapping text.
3. Generate embeddings for the chunks.
4. Store the embeddings in a FAISS vector database.
5. Retrieve relevant chunks for a user's question.
6. Pass the retrieved context and question to the language model.
7. Generate an answer based on the available context.

## Evaluation

The project includes a set of test questions covering employee leave policies and questions whose answers are not available in the handbook.

The current evaluation run passed **7 out of 7 tests**. These tests use expected-answer phrase matching, so this result is an initial check rather than a guarantee of accuracy for every question.

## Project Structure

```text
RAG_Project/
├── data/
│   └── employee_handbook.pdf
├── notebooks/
│   ├── RAG_Pipeline.ipynb
│   └── faiss_index/
├── README.md
└── requirements.txt
```

## Running the Project

1. Install the required Python packages listed in `requirements.txt`.
2. Install Ollama and download the `llama3.2:3b` model.
3. Open `notebooks/RAG_Pipeline.ipynb` in Jupyter Notebook or VS Code.
4. Start Ollama.
5. Run the notebook cells in order to build the index and test the RAG pipeline.

**Note:** The language model must be running to generate answers. The notebook currently builds and saves the FAISS index when its index-creation cell runs.

## Learning Objectives

- Understand the core components of a RAG pipeline.
- Learn document loading and text chunking.
- Explore semantic embeddings and vector search.
- Connect retrieved document context to a locally running language model.
- Test whether generated answers follow the information available in a source document.
