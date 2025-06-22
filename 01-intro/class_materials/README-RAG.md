# RAG System Implementation with MinSearch and Elasticsearch

This repository contains a Jupyter notebook that demonstrates the implementation of a Retrieval-Augmented Generation (RAG) system using two different search backends: MinSearch and Elasticsearch.

## Overview

The implementation shows how to build a complete RAG pipeline that:

1. **Indexes** course FAQ documents
2. **Retrieves** relevant documents based on user queries
3. **Augments** prompts with retrieved context
4. **Generates** accurate answers using LLMs

## Components

### 1. Data Preparation
- Loading JSON documents containing course FAQs
- Processing documents to include course information
- Structuring data for search indexing

### 2. MinSearch Implementation
- Simple in-memory vector search engine
- TF-IDF based document vectorization
- Cosine similarity for matching queries to documents
- Field boosting for prioritizing question matches

### 3. OpenAI Integration
- Connecting to OpenAI API using environment variables
- Creating structured prompts with retrieved context
- Generating responses using GPT-4o models

### 4. Elasticsearch Integration
- Setting up Elasticsearch in Docker
- Creating proper index mappings with text and keyword fields
- Implementing boolean queries with multi-match and filtering
- Handling version compatibility between ES client and server

## Version Compatibility Challenge

A significant part of the implementation addresses version compatibility issues between the Elasticsearch Python client and server:

- Recent ES Python clients (8.x) send API compatibility headers for version 9
- ES 8.x servers reject these headers, causing BadRequestErrors
- Solution: Either use ES Python client 7.17.0 or override default request headers

## RAG Pipeline Architecture

The RAG pipeline follows a three-step process:

1. **Retrieval**: Find relevant documents using either MinSearch or Elasticsearch
2. **Augmentation**: Build a prompt incorporating retrieved context and the user's question
3. **Generation**: Generate an answer using OpenAI's models based on the augmented prompt

## Key Features

- Graceful fallback from Elasticsearch to MinSearch if ES is unavailable
- Detailed diagnostic functions for inspecting search results
- Comparison tools to evaluate MinSearch vs. Elasticsearch results
- Comprehensive function documentation and comments

## MinSearch vs. Elasticsearch Comparison

| Feature | MinSearch | Elasticsearch |
|---------|-----------|---------------|
| **Complexity** | Simple, in-memory | Full-featured search engine |
| **Scalability** | Limited to RAM | Horizontally scalable |
| **Search Features** | Basic TF-IDF + cosine similarity | Advanced queries, filters, analyzers |
| **Setup** | Simple Python import | Requires server infrastructure |
| **Speed** | Fast for small datasets | Optimized for large-scale search |
| **Deployment** | Single process | Distributed architecture |

## Getting Started

1. Install required packages:
```bash
uv pip install minsearch openai python-dotenv
```

2. For Elasticsearch:
```bash
uv pip install elasticsearch==7.17.0

# Run Elasticsearch in Docker
docker run -it \
    --rm \
    --name elasticsearch \
    -m 4GB \
    -p 9200:9200 \
    -p 9300:9300 \
    -e "discovery.type=single-node" \
    -e "xpack.security.enabled=false" \
    docker.elastic.co/elasticsearch/elasticsearch:8.12.2
```

3. Set up `.env` file with your OpenAI API key:
```
OPENAI_API_KEY=your_api_key_here
```

4. Run the notebook `rag-intro.ipynb`

## Conclusion

This implementation demonstrates how RAG systems combine the power of retrieval engines with language models to provide accurate, context-aware responses. The comparison between MinSearch and Elasticsearch highlights the trade-offs between simplicity and advanced features when choosing a retrieval component for RAG applications.
