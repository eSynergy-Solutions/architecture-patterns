# Legal Document Assistant

## Category
AI / NLP

## Summary
An AI assistant that extracts and answers legal questions from enterprise contracts using RAG architecture.

## Problem Statement
Legal teams spend too much time searching and reviewing documents manually. There is a need for a tool to summarize, extract clauses, and answer natural language questions.

## Solution Overview
Combines document processing, embedding, retrieval, and a generative LLM to answer domain-specific questions with contextual accuracy.

## Architecture Patterns Used
- [RAG (Retrieval-Augmented Generation)](../../Patterns/AI-ML/RAG.md)
- [Microservices - chat application](../../Apps/Microservices.md)

## System Diagram
![legal-doc-assistant-architecture](../../images/legal-doc-assistant-architecture.png)

## Cloud-Specific Implementation
**Azure**:
- Azure OpenAI
- Azure Cognitive Search
- Azure Functions

**GCP**:
- Vertex AI
- Matching Engine
- Cloud Run

## PoCs / Repositories
- [Red-bar-tool-backend](https://github.com/eSynergy-Solutions/red-bar-tool-backend)

- [Red-bar-tool-frontend](https://github.com/eSynergy-Solutions/red-bar-tool-frontend)

## Notes
- Optional feedback loop for human validation
- Data security controls required for sensitive legal content
