# Vector Search - Homework 02 Summary

This document summarizes the tasks performed in Homework 02 and key concepts from the vector search module.

## Homework Tasks Overview

### 1. Text Embeddings with Jina AI
- Used `jinaai/jina-embeddings-v2-small-en` model to convert text into 512-dimensional vectors
- Examined vector properties and found the minimum value to be approximately -0.11
- Practiced calculating dot products between vectors to determine their cosine similarity

### 2. Semantic Similarity Analysis
- Calculated cosine similarity between query and document embeddings
- Found high semantic similarity (~0.9) between the query "I just discovered the course. Can I join now?" and "Can I still join the course after the start date?"
- Demonstrated how vector representations capture meaning rather than just keywords

### 3. Document Ranking with Vector Embeddings
- Created embeddings for a collection of course-related documents
- Ranked documents based on semantic similarity to our query
- Used matrix operations for efficient similarity calculations across multiple documents
- Found that document index 1 was most similar when using only the "text" field

### 4. Field Selection in Vector Search
- Compared search effectiveness using different document fields:
  - Using only "text" field vs. combining "question" + "text" fields
- Discovered that adding the question field shifted the most relevant result to document 0
- Demonstrated how field selection can significantly impact search results

### 5. Embedding Model Selection
- Explored smaller embedding models available in FastEmbed
- Identified that 384 is the smallest dimensionality available in FastEmbed models
- Selected `BAAI/bge-small-en` as a more compact alternative model

### 6. Building a Complete Vector Search System
- Created and configured a Qdrant collection with the appropriate vector parameters
- Filtered documents from the machine-learning-zoomcamp course
- Combined fields (question + text) to create more effective document representations
- Retrieved semantically similar documents with a relevance score of ~0.87

## Key Concepts from Class Materials

### Vector Search Fundamentals
- Vector search uses semantic similarity rather than exact keyword matching
- Embeddings convert text into numerical vectors that capture meaning
- Similar concepts have similar vector representations, enabling semantic search

### Qdrant Vector Database
- Open-source vector search engine built in Rust for scalable search
- Provides specialized infrastructure for efficient vector operations
- Supports various distance metrics (cosine similarity, Euclidean, dot product)

### Embedding Models
- Models like Jina and BAAI/bge convert text to fixed-size numerical vectors
- Different models offer trade-offs between size, speed, and accuracy
- Normalized vectors simplify similarity calculations through dot products

### RAG (Retrieval-Augmented Generation)
- Vector search is a core component of RAG systems
- Documents are indexed as vectors for efficient similarity search
- Retrieved context is used to augment LLM responses with specific information

### Hybrid Search
- Combines dense vector search with sparse/keyword-based approaches
- BM25 is a statistical model that ranks documents based on term frequency and uniqueness
- Sparse vectors excel at exact matches for proper names or identifiers
- Hybrid approaches combine strengths of semantic understanding and keyword precision

## Practical Applications
- Building question-answering systems that retrieve relevant context
- Creating document search engines that understand semantic similarity
- Implementing conversational agents with access to specific knowledge bases
- Enhancing LLM outputs with accurate, relevant information retrieval

This homework provided hands-on experience with the fundamental building blocks of modern RAG systems, particularly focusing on the retrieval component that identifies and fetches relevant information.
