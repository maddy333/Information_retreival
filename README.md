Information Retrieval from PDF with BLOOM 

This project is a Streamlit-based application that enables users to upload single or multiple PDF documents and interactively ask questions based on the content of those documents. The system leverages Bloom LLM for text generation, LangChain for orchestration, and ChromaDB for semantic search and vector-based text retrieval.

Features

Upload Multiple PDFs: Users can upload multiple PDF documents via the app's sidebar.

Text Extraction: Extracts text from PDF documents using PyPDF2.

Semantic Search: Uses ChromaDB to store text embeddings and retrieve relevant content efficiently.

Conversational Responses: Employs Bloom LLM for natural language generation, enabling users to receive accurate, conversational answers.

Interactive Interface: Simple and user-friendly web interface powered by Streamlit.

Technologies Used

Streamlit: To build the web-based user interface.

LangChain: Framework for building workflows involving text chunking and conversational retrieval chains.

ChromaDB: Open-source vector database for managing and querying embeddings.

Bloom LLM: Multilingual large language model for generating human-like responses.

PyPDF2: Library for extracting text from PDF documents.

Sentence Transformers: For generating vector embeddings of text chunks.

HuggingFace Transformers: For integrating the Bloom LLM.

Installation

Prerequisites

Python 3.8 or higher

pip (Python package manager)

Steps

Clone the Repository:

git clone https://github.com/maddy333/Information_retreival/tree/main
cd information-retrieval-system

Install Dependencies:

pip install -r requirements.txt

Download Bloom LLM:
Download the Bloom LLM model using the Hugging Face Transformers library:

from transformers import AutoTokenizer, AutoModelForCausalLM
tokenizer = AutoTokenizer.from_pretrained("bigscience/bloom-560m")
model = AutoModelForCausalLM.from_pretrained("bigscience/bloom-560m")

Usage

Running the Application

Start the Application:

streamlit run app.py

Access the App:
Open your browser and navigate to http://localhost:8501.

Upload PDFs:

Use the sidebar to upload your PDF files.

Click the "Submit & Process" button to extract and process the content.

Ask Questions:

Use the input box to type your questions about the uploaded documents.

Receive answers in a conversational format based on the document content.

Project Structure

information-retrieval-system/
|
├── app.py                 # Main Streamlit application
├── src/
│   ├── helper.py          # Helper functions for processing PDFs and setting up components
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables
└── README.md              # Project documentation

Key Functions

app.py

Main Script: Manages the Streamlit app interface and user interactions.

User Question Handling: Captures user input and provides conversational responses using the preprocessed PDFs.

Sidebar Menu: Allows users to upload PDF documents and triggers the processing workflow.

helper.py

get_pdf_text(pdf_docs): Extracts text from uploaded PDF documents.

get_text_chunks(text): Splits extracted text into manageable chunks for embedding.

get_vector_store(text_chunks): Creates a vector store using ChromaDB and sentence-transformer embeddings.

get_conversational_chain(vector_store): Sets up a conversational retrieval chain using Bloom LLM and ChromaDB.

Requirements

The requirements.txt includes all the dependencies:

streamlit
PyPDF2
langchain
sentence-transformers
chromadb
transformers
torch
python-dotenv