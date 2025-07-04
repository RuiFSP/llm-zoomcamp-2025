# LLM Zoomcamp Workshop Summary

## Overview

This document summarizes the key concepts and exercises covered in the DLT (Data Loading Tool) and Cognee workshops as part of the LLM Zoomcamp 2025. The workshop focused on data ingestion, indexing, and querying using vector databases for Retrieval Augmented Generation (RAG) applications.

## DLT and Qdrant Integration

### Key Components:

1. **DLT (Data Loading Tool)**: A Python library for building data pipelines
   - Used for extracting and loading data into vector databases
   - Supports transformation of data during the pipeline process
   - Provides a simple API for defining resources and pipelines

2. **Qdrant**: Vector database used for storing and querying vector embeddings
   - Efficient similarity search capabilities
   - Used for storing document embeddings for RAG applications

## Workshop Notebooks

### 1. `cognee_taxi_dataset_demo.ipynb`

This notebook demonstrates:
- Using DLT to load data from the NYC Taxi dataset
- Processing and transforming the data
- Creating embeddings for vector search
- Storing the data in a vector database
- Basic querying capabilities

### 2. `search_knowledge_graph.ipynb`

This notebook focuses on:
- Using Cognee for knowledge graph search
- Different search types (GRAPH_COMPLETION, RAG_COMPLETION)
- Working with NodeSets for focused searches
- Querying API documentation (Ticketmaster API example)
- Comparing broad vs. focused search approaches

## Homework Workshop

In the `homework_workshop.ipynb` notebook, we:

1. **Set up a DLT pipeline with Qdrant**:
   - Installed DLT with Qdrant support (version shown in output)
   - Created a resource function to fetch and yield Zoomcamp FAQ documents
   - Configured a Qdrant destination with local storage in `db.qdrant`

2. **Ran the pipeline**:
   - Successfully loaded 948 rows of data into the `zoomcamp_data` collection
   - Data was automatically embedded using the vector embedding model

3. **Examined the embedding model**:
   - Inspected the `meta.json` file to determine the embedding model
   - Identified that the "fast-bge-small-en" model was used
   - The model creates 384-dimensional embeddings with Cosine distance

## Key Takeaways

1. **Data Pipeline Creation**: DLT simplifies the creation of data pipelines for loading data into vector databases.

2. **Embedding Generation**: Automatic embedding generation using pre-trained models like "fast-bge-small-en".

3. **Vector Search**: Efficient similarity search for retrieving relevant documents based on semantic meaning.

4. **Knowledge Graph Navigation**: Using Cognee to navigate and search through knowledge graphs.

5. **RAG Applications**: Foundation for building Retrieval Augmented Generation applications by providing a searchable knowledge base.

## Next Steps

- Explore more complex RAG applications using the loaded data
- Experiment with different embedding models for improved performance
- Combine with LLMs to create complete question-answering systems
- Evaluate and fine-tune retrieval quality
