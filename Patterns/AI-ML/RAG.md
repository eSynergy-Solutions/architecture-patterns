# Retrieval-Augmented Generation (RAG)

## Summary
RAG enhances LLM responses by retrieving relevant data from external sources before generating answers.

## Context
Use when the LLM needs to answer questions with accurate, up-to-date, or private domain-specific information that isn't part of its training data.

## Problem
LLMs are limited to their training data and can hallucinate or provide outdated answers. RAG bridges this gap by injecting retrieved documents into the generation process.

## Solution
Combine vector-based document retrieval with LLM prompting to provide grounded and context-rich responses.

## Diagram
![rag-aws](images/RAG.drawio.png)

## Components
- **User Interface** – chat/web interface to input query
- **Query Preprocessor** – optional normalization and rephrasing
- **Vector Store** – FAISS, Pinecone, or Azure AI Search to store embeddings
- **Retriever** – converts query to embedding and fetches similar documents
- **LLM Engine** – OpenAI, Azure OpenAI, etc., receives retrieved context + original query
- **Prompt Builder** – constructs final prompt with context

## Benefits
- Domain-specific knowledge without retraining
- Improves accuracy and reduces hallucination
- Easily updateable context without touching the LLM

## Trade-offs
- Latency increases due to retrieval step
- Requires vector store and embedding pipeline
- May retrieve noisy or irrelevant documents if not tuned well

## Cloud-Specific Implementation

### Azure
- Embeddings: Azure OpenAI + `text-embedding-ada-002`
- Vector Store: Azure AI Search or Redis
- LLM: Azure OpenAI `gpt-35-turbo` or `gpt-4`
- Flow: Azure Functions or FastAPI on Azure App Service

### GCP
- Embeddings: Vertex AI Embedding API
- Vector Store: Vertex AI Matching Engine
- LLM: Vertex AI PaLM or Gemini
- Flow: Cloud Functions / Cloud Run

### AWS
![rag-aws](images/rag-aws.png)

- Embeddings: Bedrock with Titan Embeddings
- Vector Store: OpenSearch or Amazon Kendra or PostGres pgVector
- LLM: Anthropic Claude via Bedrock, OpenAI
- Flow: Lambda + API Gateway

## Related Patterns
- Semantic Search
- Hybrid Search (BM25 + Embeddings)
- Knowledge Base Integration

## References
- [Meta AI: RAG paper](https://arxiv.org/abs/2005.11401)
- [OpenAI Cookbook: RAG](https://github.com/openai/openai-cookbook/blob/main/examples/Retrieval_augmentation.ipynb)
- [Azure RAG Pattern](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/ai/azure-rag-architecture)

## Proof of Concepts
- [rag-azure-openai-fastapi](https://github.com/your-org/rag-azure-openai-fastapi) – Azure OpenAI + Azure AI Search + FastAPI
- [gcp-rag-vertexai-matchingengine](https://github.com/your-org/gcp-rag-vertexai-matchingengine) – GCP Matching Engine + Vertex AI + Streamlit
- [aws-bedrock-rag-demo](https://github.com/your-org/aws-bedrock-rag-demo) – AWS Bedrock RAG with OpenSearch

