## LLM Zoomcamp

## My Progress Tracker

Track my progress through the LLM Zoomcamp 2025 cohort:

- ✅ **Module 1**: Introduction to LLMs and RAG - Completed on June 2025
- ✅ **Module 2**: Vector Search - Completed on June 2025
- ✅ **Workshop**: Open-Source Data Ingestion - Completed on July 2025
- 🔲 **Module 3**: Evaluation
- 🔲 **Module 4**: Monitoring
- 🔲 **Module 5**: Best Practices
- 🔲 **Module 6**: Bonus - End-to-End Project
- 🔲 **Capstone Project**

## Module Summaries

### Module 1: Introduction to LLMs and RAG

In this module, I learned the fundamentals of:

- **LLMs (Large Language Models)**: Understanding their capabilities and limitations
- **RAG (Retrieval-Augmented Generation)**: Learning the architecture and components of RAG systems
- **Search Techniques**: 
  - Using MinSearch for lightweight in-memory search with TF-IDF vectorization
  - Setting up and configuring Elasticsearch for more robust search capabilities
  - Implementing `multi_match` queries to search across multiple document fields
- **OpenAI Integration**: Connecting to OpenAI API to generate responses based on retrieved context
- **End-to-End RAG Pipeline**: Building a complete system that:
  - Indexes Zoomcamp FAQ documents
  - Retrieves relevant documents based on user queries
  - Augments prompts with retrieved context
  - Generates answers using LLMs

**Projects & Homework**:
- Implemented a Q&A system for answering questions about Zoomcamp course FAQs
- Worked with Elasticsearch 8.x for document indexing and retrieval
- Created structured prompts with retrieved context for accurate LLM responses

### Module 2: Vector Search

In this module, I learned about vector-based search techniques:

- **Embedding Models**: Working with models like Jina and BAAI/bge to convert text into numerical vectors
- **Semantic Similarity**: Calculating cosine similarity between embeddings to find related content
- **Vector Databases**: Setting up and using Qdrant for efficient vector storage and retrieval
- **Search Optimization**: 
  - Comparing results from different text fields (text-only vs. question + text)
  - Evaluating the impact of embedding model selection on search quality
  - Understanding dimensionality trade-offs in vector embeddings
- **Hybrid Search**: Combining dense vector search with sparse/keyword-based approaches like BM25
- **End-to-End Vector Search Pipeline**: Building a complete system that:
  - Processes and embeds documents with combined fields
  - Indexes vectors in a specialized vector database
  - Retrieves semantically similar documents based on user queries
  - Ranks results by relevance scores

**Projects & Homework**:
- Built a vector search system using Qdrant and FastEmbed
- Experimented with different embedding models and dimensions
- Analyzed how field selection impacts search relevance
- Created a production-ready vector search collection for ML Zoomcamp FAQs

### Workshop: Open-Source Data Ingestion

In this workshop, I learned about data ingestion tools for RAG applications:

- **DLT (Data Loading Tool)**: Working with a Python library for building robust data pipelines
  - Creating resource definitions for data extraction
  - Configuring destinations for vector database integration
  - Running pipelines to extract, transform, and load document data
- **Qdrant Integration**: Setting up Qdrant as a vector database destination
  - Using local storage for development environments
  - Understanding collection metadata and configuration
- **Embeddings Generation**: Automatic embedding using models like "fast-bge-small-en"
  - Analyzing model configurations (384-dimensional vectors, cosine distance)
  - Understanding how embeddings are stored and indexed
- **Cognee**: Working with knowledge graph navigation and search
  - Different search types (GRAPH_COMPLETION, RAG_COMPLETION)
  - Using NodeSets for focused searches
  - Querying API documentation with semantic understanding

**Projects & Homework**:
- Built a data pipeline to load 948 Zoomcamp FAQ documents into Qdrant
- Analyzed embedding model configuration in Qdrant metadata
- Experimented with knowledge graph search using Cognee
- Set up a complete RAG-ready dataset for question answering
