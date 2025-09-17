AI Lawyer Chatbot with Deepseek RAG
This project implements a sophisticated AI Lawyer Chatbot using a Retrieval-Augmented Generation (RAG) pipeline. The application, built with a Streamlit front-end, allows users to upload legal documents in PDF format and ask questions related to their content. The chatbot leverages the power of Deepseek's language models through the Groq API to provide accurate and contextually relevant answers.

Table of Contents
Features

How it Works

Technologies Used

Setup and Installation

Usage

Project Structure

Acknowledgements

Features
Document Upload: Easily upload PDF documents for analysis.

Vector Database: Utilizes a FAISS vector database for efficient storage and retrieval of document embeddings.

Advanced AI Model: Employs the powerful Deepseek language model via the Groq API for high-quality responses.

Retrieval-Augmented Generation: Enhances the AI's responses by retrieving relevant information directly from the uploaded documents.

Interactive Chat Interface: A user-friendly chat interface built with Streamlit for seamless interaction.

How it Works
The application follows a complete RAG pipeline:

Document Loading: The user uploads a PDF document through the Streamlit interface. The application uses PDFPlumber to load and extract the text from the document.

Text Chunking: The extracted text is split into smaller, manageable chunks to ensure efficient processing and accurate retrieval.

Embedding and Storage: Each text chunk is converted into a numerical vector (embedding) using Ollama and Deepseek embeddings. These embeddings are then stored in a FAISS vector database for quick and efficient similarity searches.

User Query and Retrieval: When the user asks a question, the application converts the query into an embedding and searches the FAISS database for the most relevant text chunks from the document.

Response Generation: The retrieved text chunks are then passed to the Deepseek LLM, along with the user's original query. The model uses this context to generate a comprehensive and accurate answer.

Technologies Used
Python: The core programming language for the project.

Streamlit: For building the interactive web application and user interface.

LangChain: To orchestrate the RAG pipeline, including document loading, chunking, and retrieval.

Groq API: Provides access to the high-performance Deepseek LLM for response generation.

Deepseek LLM: The large language model used for understanding and generating answers.

Ollama: Used for generating the text embeddings.

FAISS: A library for efficient similarity search and clustering of dense vectors, used here as the vector database.

PDFPlumber: For robust PDF parsing and text extraction.

Setup and Installation
To run this project locally, please follow these steps:

Clone the repository:

Bash

git clone https://github.com/Shailu1964/rag-with-deepseek.git
cd rag-with-deepseek
Create and activate a virtual environment:

Bash

python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
Install the required dependencies:

Bash

pip install -r requirements.txt
Set up your environment variables:

Create a .env file in the root directory of the project.

Add your Groq API key to the .env file:

GROQ_API_KEY="your_groq_api_key"
Usage
Run the Streamlit application:

Bash

streamlit run frontend.py
Open your web browser and navigate to the local URL provided by Streamlit (usually http://localhost:8501).

Upload a PDF document using the file uploader in the sidebar.

Ask a question about the content of the document in the chat input box.

The AI Lawyer Chatbot will provide a context-aware answer based on the information in the document.

Project Structure
.
├── .env                  # Environment variables (Groq API key)
├── frontend.py           # Main Streamlit application file
├── rag_pipeline.py       # Core RAG pipeline logic
├── requirements.txt      # Project dependencies
├── vector_database.py    # Functions for vector database management
├── pdfs/                 # Directory to store uploaded PDFs
└── vectorstore/          # Directory for the FAISS vector database
Acknowledgements
This project was developed as a practical implementation of Retrieval-Augmented Generation with modern AI tools and technologies. Special thanks to the developers of Streamlit, LangChain, Groq, and Deepseek for their powerful and accessible platforms.
