# AIML_RAG_Study_Assistant

# DBMS RAG Assistant using LangChain and Ollama

## Introduction

This project implements a Retrieval-Augmented Generation (RAG) based assistant for answering questions from DBMS notes.

The assistant reads DBMS notes from a PDF file, converts the text into embeddings, stores them in a vector database, retrieves relevant content, and generates answers using a local LLM.

This project also compares:

• Small chunk size vs Large chunk size  
• Basic prompt vs Improved prompt  

This helps to understand how chunk size and prompt engineering affect answer quality.

The system uses Ollama with the Gemma3:1b model running locally.

---

## Objective

The main objectives of this project are:

• Load DBMS notes from PDF  
• Split notes into small and large chunks  
• Create vector embeddings  
• Store embeddings in vector database  
• Retrieve relevant context based on question  
• Generate answers using local LLM  
• Apply prompt engineering  
• Compare performance of chunk sizes and prompts  

---

## Tools and Technologies Used

Programming Language:
Python

Libraries Used:

• LangChain  
• ChromaDB  
• Sentence Transformers  
• Ollama  
• PyPDF  
• Transformers  

Model Used:

gemma3:1b (local LLM using Ollama)

Environment:

Jupyter Notebook

---

## Project Workflow

The project follows these steps:

---

### Step 1: Import Libraries

All required libraries such as LangChain, ChromaDB, embeddings, and Ollama are imported.

This helps in loading PDF, creating embeddings, and generating answers.

---

### Step 2: Load PDF

The DBMS notes PDF is loaded using PyPDFLoader.

The text is extracted and stored as documents.

This step converts the PDF into readable text format.

---

### Step 3: Create Small Chunks

The text is split into small chunks using:

chunk_size = 500  
chunk_overlap = 100  

Small chunks help in retrieving precise information.

---

### Step 4: Create Large Chunks

The text is split into large chunks using:

chunk_size = 1000  
chunk_overlap = 200  

Large chunks help in retrieving more context.

---

### Step 5: Create Embeddings

Embeddings are created using:

all-MiniLM-L6-v2

Embeddings convert text into numerical vectors so similarity search can be performed.

---

### Step 6: Create Vector Database

ChromaDB is used to store embeddings.

Two databases are created:

• Small chunk database  
• Large chunk database  

This allows comparison between chunk sizes.

---

### Step 7: Create Retriever

Retriever is used to fetch relevant chunks based on the user question.

Top 3 relevant chunks are retrieved.

---

### Step 8: Load Ollama Model

The local model used is:

gemma3:1b

This model generates answers based on retrieved context.

The model runs locally, so no API key is required.

---

### Step 9: Basic Prompt

Basic prompt format:

Answer based on context below.

This prompt gives simple answers.

---

### Step 10: Improved Prompt (Prompt Engineering)

Improved prompt format:

You are a DBMS expert assistant.  
Answer only using the provided context.  
Do not use outside knowledge.  
If answer is not found, say "Answer not found in notes."  
Explain clearly.

This prompt improves answer quality and accuracy.

---

### Step 11: Compare Results

Answers are compared based on:

• Small chunk vs Large chunk  
• Basic prompt vs Improved prompt  

This helps analyze performance.

---

## Experiment Results Summary

Observation 1:

Small chunks give more accurate answers because retrieval is more precise.

Observation 2:

Large chunks give more detailed answers but sometimes include extra information.

Observation 3:

Improved prompt gives better and clearer answers compared to basic prompt.

Observation 4:

Prompt engineering improves answer quality significantly.

---

## Example Questions Tested

• What is normalization?  
• What is primary key?  
• Explain ACID properties  
• What is indexing?  

Answers were generated using both chunk sizes and prompts.

--
## How to Run the Project

Step 1: Install requirements

Run:

pip install -r requirements.txt

---

Step 2: Install Ollama

Download from:

https://ollama.com/download

Install and open Ollama.

---

Step 3: Pull model

Run in terminal:

ollama pull gemma3:1b

---

Step 4: Run Notebook

Open Jupyter Notebook:

jupyter notebook

Open:

dbms_rag.ipynb

Run all cells.

---

## Conclusion

This project successfully implemented a RAG-based DBMS assistant.

Key conclusions:

• RAG improves answer accuracy  
• Vector database enables efficient retrieval  
• Small chunks improve precision  
• Large chunks improve context coverage  
• Prompt engineering significantly improves answer quality  
• Local LLM using Ollama works efficiently without API  

This system can be used as a smart assistant for DBMS notes.

---
