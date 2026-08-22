# Multi-Agent Healthcare RAG

A multi-agent Retrieval-Augmented Generation (RAG) system for healthcare insurance queries using GPT-4o, LangChain, FAISS, and Hugging Face embeddings.

## Overview

This project explores a multi-agent architecture for answering healthcare insurance-related questions using retrieval-augmented generation.

Instead of relying on a single LLM agent, the system separates the workflow into specialized agents responsible for intent classification, document retrieval, response generation, and safety verification.

The goal is to produce responses that are more grounded in retrieved information and less prone to unsupported or hallucinated answers.

## Architecture

```text
User Query
   ↓
Intent Classifier Agent
   ↓
RAG Retrieval Agent
   ↓
Response Generator Agent
   ↓
Safety Verification Agent
   ↓
Final Response
```

### Agents

* **Intent Classifier Agent**
  Identifies the type and intent of the incoming user query.

* **RAG Retrieval Agent**
  Retrieves relevant information from the domain knowledge base using semantic search and FAISS.

* **Response Generator Agent**
  Generates a response using the retrieved context and GPT-4o.

* **Safety Verification Agent**
  Reviews the generated response for unsupported claims, hallucinations, and grounding issues before returning the final answer.

## RAG Pipeline

The retrieval pipeline uses Hugging Face embeddings to represent domain documents as vectors.

These embeddings are stored and searched using FAISS, allowing the system to retrieve semantically relevant information for each user query.

The retrieved context is then passed to the language model to support grounded response generation.

## Evaluation

The multi-agent system was compared with a single-agent baseline.

Evaluation focused on:

* response grounding
* hallucination reduction
* citation quality
* answer relevance
* overall response quality

Weights & Biases was used for experiment tracking and evaluation.

## Technologies

* Python
* GPT-4o
* LangChain
* FAISS
* Hugging Face Embeddings
* Retrieval-Augmented Generation (RAG)
* Multi-Agent Systems
* Weights & Biases

## Project Structure

```text
multi-agent-healthcare-rag/
│
├── README.md
└── multi_agent_healthcare_rag.ipynb
```

## Running the Project

1. Clone the repository.
2. Open the notebook locally or in Google Colab.
3. Install the required dependencies.
4. Configure the required API keys securely.
5. Run the notebook cells in order.

## Background

This project was developed as the final project for **DSAI 585 — Generative AI**.

## Author

**Hatice Nur Alan**
MSc Data Science & Artificial Intelligence
