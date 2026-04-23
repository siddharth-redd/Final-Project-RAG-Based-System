# RAG-Based Customer Support Assistant using LangGraph and HITL

Overview

This project implements a Retrieval-Augmented Generation (RAG) system designed to act as a Customer Support Assistant.

The system:

  Processes a PDF knowledge base
  Retrieves relevant information using embeddings
  Generates contextual responses using an LLM
  Uses LangGraph for workflow orchestration
  Implements conditional routing
  Supports Human-in-the-Loop (HITL) escalation

Objective:

  The goal of this project is to:
  
  Build an intelligent support assistant
  Reduce dependency on human agents
  Ensure accurate and context-aware responses
  Handle complex queries via escalation

What is RAG?

  RAG (Retrieval-Augmented Generation) combines:
  
  Retrieval → Fetch relevant data from documents
  Generation → Use LLM to generate answers
  
  This reduces hallucination and improves accuracy.

System Architecture:
  
  User Query
     ↓
  Retriever (ChromaDB)
     ↓
  Relevant Chunks
     ↓
  LLM (Generate Answer)
     ↓
  LangGraph Decision Node
     ↓
  → Respond OR → Escalate (HITL)


Tech Stack:

  Component	Tool Used
  Language	Python
  Framework	LangChain
  Workflow	LangGraph
  Embeddings	HuggingFace
  Vector DB	ChromaDB
  LLM	GPT2 (local, free)
  Document Loader	PyPDFLoader


Workflow Explanation:
  
  1. Document Processing
  Load PDF using PyPDFLoader
  2. Chunking
  Split into smaller pieces using RecursiveCharacterTextSplitter
  3. Embeddings
  Convert chunks into vectors using HuggingFace
  4. Storage
  Store embeddings in ChromaDB
  5. Retrieval
  Fetch relevant chunks using similarity search
  6. Answer Generation
  Use LLM to generate answers from retrieved context
  7. Decision Making (LangGraph)
  Decide whether to:
  Respond
  Escalate
  8. HITL
  Escalate complex queries to human

Conditional Routing Logic:

The system decides:
  
  Respond → If relevant documents are found
  Escalate → If no relevant context is available
  uman-in-the-Loop (HITL)

HITL is triggered when:

  No relevant information is found
  Query is out of scope
  Confidence is low
  
Project Structure:

  project/
  │
  ├── notebook.ipynb
  ├── customer_support.pdf
  ├── chroma_db/
  ├── README.md
  ├── HLD.pdf
  ├── LLD.pdf
  └── Technical_Documentation.pdf
  
 How to Run:
  1. Install Dependencies
  pip install langchain langchain-community langgraph chromadb pypdf sentence-transformers transformers
  2. Run Jupyter Notebook
  jupyter notebook
  3. Execute Cells
  Load PDF
  Create embeddings
  Run query
  4. Example Query
  How do I reset my password?
   Sample Test Queries
   Normal Queries
  How do I reset my password?
  What is the refund policy?
   Edge Cases
  I forgot my password, what should I do?
   Escalation Queries
  I want to talk to a human
  My account is hacked
   Out-of-Scope
  What is AI?

 Challenges Faced:
  Handling LangChain version changes
  Model output inconsistency
  Balancing cost vs performance
  Designing routing logic
     Trade-offs
  Factor	Trade-off
  Accuracy	Better models cost more
  Speed	Smaller chunks are faster
  Cost	Free models are weaker
  
   Future Enhancements:
  Better LLM (Mistral / Llama)
  UI (Streamlit)
  Multi-document support
  Memory integration
  Deployment on AWS
  
 Key Features:

  ✔ RAG-based architecture
  ✔ LangGraph workflow
  ✔ Conditional routing
  ✔ HITL support
  ✔ Free/local setup

 Author:

Name: Siddharth P Reddy
Project: RAG Internship Project
