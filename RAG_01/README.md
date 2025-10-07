Docker Deep Dive RAG System
This project is a simple Retrieval-Augmented Generation (RAG) pipeline built using LangChain, Pinecone, and Google Generative AI. It processes the "Docker Deep Dive" book (provided as a PDF), embeds the content into a vector store, and allows users to query Docker-related topics. The system retrieves relevant document chunks from the book and generates answers using a large language model (Gemini).
Features

PDF document loading and processing using PyMuPDFLoader.
Text embedding with Google Generative AI Embeddings.
Vector storage and similarity search with Pinecone.
Query answering powered by Google Gemini LLM.
Interactive user input for querying Docker knowledge.

Prerequisites

Python 3.8+
API Keys:
Google API Key (for embeddings and LLM).
Pinecone API Key (for vector database).


The "Docker Deep Dive" PDF file (named docker.pdf in ../data/ directory).

Installation

Clone the repository:
git clone https://github.com/your-repo/docker-rag-system.git
cd docker-rag-system


Create a virtual environment:
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate


Install dependencies:
pip install langchain langchain-community langchain-google-genai langchain-pinecone pinecone-client pypdf uuid

(You may need additional libraries like google-generativeai if not covered.)

Set environment variables for API keys:
export GOOGLE_API_KEY=your_google_api_key
export PINECONE_API_KEY=your_pinecone_api_key


Place the docker.pdf file in the ../data/ directory relative to the notebook.


Usage

Open the Jupyter Notebook:
jupyter notebook document.ipynb


Run the cells step-by-step:

Load and process the PDF.
Embed and store documents in Pinecone (index name: rag-01).
Enter a query when prompted (e.g., "How to run a Docker image?").
The system will retrieve relevant book sections and generate an answer.



Example Query:
How may I help you? How to run a Docker image?

Output: A generated response based on the book's content.
Project Structure

document.ipynb: Main Jupyter Notebook with the RAG pipeline code.
../data/docker.pdf: The source PDF file (not included in repo; download separately).
(Optional) requirements.txt: List of dependencies.

How It Works

Document Loading: Uses PyMuPDFLoader to extract text from the PDF.
Embedding: Converts text chunks to vectors using Google Embeddings.
Vector Store: Stores embeddings in Pinecone for fast retrieval.
Query Processing: 
User inputs a query.
Performs similarity search to retrieve top-k relevant docs.
Constructs a prompt with context and queries the Gemini LLM.


Response: Outputs an AI-generated answer grounded in the book's content.

Limitations

The system is basic and may not handle very large PDFs efficiently without chunking optimizations.
Requires internet access for API calls.
Answers are limited to the content in "Docker Deep Dive" book.

Contributing
Feel free to open issues or submit pull requests for improvements, such as better chunking strategies or additional features.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

Based on the "Docker Deep Dive" book by Nigel Poulton.
Powered by LangChain, Pinecone, and Google Generative AI.
