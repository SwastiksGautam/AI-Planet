Interactive AI Agent for Retrieval-Augmented Generation (RAG)
This project is an initial prototype for a no-code/low-code web application that demonstrates key functionalities of a Retrieval-Augmented Generation (RAG) system. It's designed as a session-based environment where each new file upload creates a clean slate for both the knowledge base and conversation history.

🌟 Features
Two-Way Interaction: Upload a PDF document and then query its content using an interactive chat interface.

Session-Based Architecture: The system resets its knowledge base and conversation history with each new file upload, ensuring a clean slate for every session.

Automated Workflow: The backend uses a fixed LangGraph agent to orchestrate the RAG workflow, which is visualized on the frontend.

Visual Workflow Canvas: The frontend uses React Flow to visually display the RAG workflow, providing an intuitive understanding of the system's logic.

⚙️ Technical Stack
Frontend: React (Single Page Application)

Backend: FastAPI (Python)

AI/LLM: OpenAI API

Vector Store: Pinecone (Prototype)

Database: SQLite (Local & Temporary)

🏗️ High-Level Design
The application follows a standard client-server architecture with three main layers:

Client (Frontend): A React-based SPA for all user interactions, file uploads, and displaying chat history.

Server (Backend): A FastAPI server that processes files, manages the vector database, and orchestrates the AI agent.

External Services: Services like OpenAI and Pinecone that the backend interacts with.

Key Data Flows
Flow 1: New Session via File Upload

The user uploads a PDF.

The backend processes the PDF, extracts text, and creates vector embeddings using the OpenAI API.

The embeddings are stored in the vector database.

A success message is returned to the frontend.

Flow 2: Answering a Question (RAG)

The user sends a query to the backend.

The backend's LangGraph agent calls the rag_retriever_tool.

The tool performs a similarity search on the vector database to retrieve the most relevant text chunks from the uploaded PDF.

The retrieved text is sent to the LLM as context to generate a final answer.

The final answer is sent to the frontend for display.

🚀 Setup and Installation
Prerequisites
Python 3.8+

Node.js & npm

An OpenAI API Key

A Pinecone API Key
