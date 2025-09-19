
Overview
---------
This application is a Retrieval-Augmented Generation (RAG) system that allows users to interact with PDF and excel documents
using natural language queries. It combines the power of local language models, efficient text embedding, 
and vector search to provide accurate and context-aware responses to user questions based on the content of uploaded PDFs and excel sheet.


Features
----------
PDF upload and processing
Question answering using local language models
PDF viewer with zoom functionality
Vector database for efficient information retrieval
Multi-query retrieval for improved accuracy
How It Works
PDF Processing: Users upload PDF documents which are then processed and converted into text.
Text Embedding: The extracted text is split into chunks and converted into vector embeddings.
Vector Storage: These embeddings are stored in a vector database for quick retrieval.
Query Processing: User questions are processed using a language model to generate multiple query variations.
Retrieval: Relevant text chunks are retrieved from the vector database based on the queries.
Answer Generation: The language model uses the retrieved context to generate an accurate answer.
Components

Embedding Model
---------------
Nomic Embed: We use the nomic-embed-text model for generating text embeddings. This model is optimized for creating high-quality vector representations of text, which is crucial for accurate information retrieval.
Vector Database
FAISS (Facebook AI Similarity Search): An efficient similarity search and clustering library for dense vectors. We use FAISS as our vector database due to its high performance and ability to handle large-scale datasets.
Why These Components?
Local Language Models: Using Ollama models allows for privacy-preserving, offline operation while maintaining high-quality language understanding and generation.
RAG System: By combining retrieval with generation, we can provide answers that are both relevant to the user's question and grounded in the actual content of the PDFs.
Vector Embeddings and Search: This allows for semantic understanding of both the document content and user queries, enabling more accurate and context-aware information retrieval.
Multi-Query Retrieval: By generating multiple variations of the user's query, we increase the chances of finding relevant information, especially for complex or ambiguous questions.
Prerequisites


Before running the application, make sure you have the following installed:
-------------------------------------------------------------------------
Python 3.8 or higher
Ollama - for running local language models
Clone the Repository: If applicable, clone the repository containing the code.
Install Python Dependencies: The following libraries are required. You can install them using pip:
Bash
pip install streamlit pdfplumber ollama PyPDF2 langchain langchain-ollama faiss-cpu python-dotenv pandas openpyxl

Usage
------
Start the Ollama Server: Make sure your Ollama server is running.
Run the Streamlit App: Open your terminal in the project directory and run the following command:
Bash
streamlit run your_app_file_name.py
(Note: Replace your_app_file_name.py with the name you saved the code file as.)


Interact with the UI:
---------------------
Upload one or more PDF or Excel files.
Select a chat model from the dropdown list.
Click "Submit & Process" to create the document vector store.
Once processing is complete, use the chat input at the bottom to ask questions about your documents.
Use the "⚠️ Delete collection" button to clear the loaded files and start fresh.


Troubleshooting
----------------
If you encounter any issues with Ollama or the language models, make sure Ollama is properly installed and running on your system.
Check that you have successfully pulled all required models (nomic-embed-text, llama2, and mistral).
Check the console output for any error messages or logs that might help identify the problem.
