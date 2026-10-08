# PDF RAG Chatbot using LangChain

A PDF-based Retrieval-Augmented Generation (RAG) chatbot built using **Python, Streamlit, LangChain, FAISS, OpenAI Embeddings, and OpenAI LLM**.

The application allows users to upload a PDF document and ask questions about its contents. The system retrieves relevant information from the uploaded document and uses an LLM to generate a contextual answer.

## Project Overview

Traditional chatbots may not have access to information contained in a user's private documents. This project uses a **Retrieval-Augmented Generation (RAG)** approach to connect an uploaded PDF with an LLM.

The application:

1. Accepts a PDF file from the user.
2. Extracts text from the PDF.
3. Splits the extracted text into smaller chunks.
4. Converts the chunks into vector embeddings.
5. Stores the embeddings in a FAISS vector database.
6. Searches for chunks relevant to the user's question.
7. Sends the retrieved context to the LLM.
8. Generates an answer based on the retrieved document content.

## RAG Architecture

```text
                 PDF Upload
                     │
                     ▼
             PDF Text Extraction
                     │
                     ▼
               Text Chunking
                     │
                     ▼
             OpenAI Embeddings
                     │
                     ▼
              FAISS Vector Store
                     │
                     │
              User Question
                     │
                     ▼
            Similarity Search
                     │
                     ▼
          Relevant PDF Chunks
                     │
                     ▼
               OpenAI LLM
                     │
                     ▼
              Generated Answer
```

## Features

* Upload PDF documents through a Streamlit interface
* Extract text from PDF files
* Split documents into manageable text chunks
* Generate vector embeddings using OpenAI
* Store and search document vectors using FAISS
* Retrieve relevant document content using similarity search
* Generate contextual answers using an OpenAI language model
* Simple and interactive web interface
* API key is kept outside the source code using environment variables

## Technologies Used

| Technology        | Purpose                         |
| ----------------- | ------------------------------- |
| Python            | Application development         |
| Streamlit         | Web interface                   |
| LangChain         | RAG application framework       |
| PyPDF2            | PDF text extraction             |
| OpenAI Embeddings | Text vectorization              |
| FAISS             | Vector similarity search        |
| OpenAI LLM        | Answer generation               |
| python-dotenv     | Environment variable management |

## Project Workflow

### 1. PDF Upload

The user uploads a PDF through the Streamlit interface.

### 2. Text Extraction

The application reads the uploaded PDF using PyPDF2 and extracts the available text from each page.

### 3. Text Chunking

The extracted text is divided into smaller chunks.

The project uses:

* Chunk size: 1000 characters
* Chunk overlap: 200 characters

Chunking helps the retrieval system work with manageable sections of the document.

### 4. Embeddings

Each text chunk is converted into a numerical vector using OpenAI Embeddings.

These vectors represent the semantic meaning of the document content.

### 5. FAISS Vector Store

The generated embeddings are stored in a FAISS vector database.

FAISS enables efficient similarity search over the document vectors.

### 6. Retrieval

When the user enters a question, the question is compared with the stored document embeddings.

The most relevant chunks are retrieved.

### 7. Answer Generation

The retrieved document chunks are provided to the OpenAI language model.

The model generates a response using the relevant information retrieved from the PDF.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Mayank234566778/PDF-RAG-Chatbot-LangChain.git
```

Move into the project directory:

```bash
cd PDF-RAG-Chatbot-LangChain
```

### 2. Create a virtual environment

```bash
python3 -m venv venv
```

Activate the environment on macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r "requirements (2).txt"
```

## OpenAI API Key Setup

This project uses OpenAI services for embeddings and language model responses.

You need to provide **your own OpenAI API key** to run the application.

Create a `.env` file in the project root:

```text
OPENAI_API_KEY=your_openai_api_key_here
```

The `.env` file should **never be committed to GitHub**.

The repository contains an `env.example` file as a safe template.

Example:

```text
OPENAI_API_KEY=your_openai_api_key_here
```

Replace the placeholder with your own key when running the application.

> **Security:** Never share your API key publicly or commit it to a Git repository.

## Running the Application

After installing the dependencies and configuring your API key, run:

```bash
python -m streamlit run "app (2).py"
```

Streamlit will provide a local URL, usually:

```text
http://localhost:8501
```

Open the URL in your browser.

## How to Use

1. Start the Streamlit application.
2. Upload a PDF document.
3. Wait for the document to be processed.
4. Enter a question related to the PDF.
5. The system retrieves relevant information.
6. The LLM generates an answer based on the retrieved content.

## Example Use Cases

This chatbot can be used for:

* Research papers
* Academic notes
* Technical documentation
* Business reports
* Product documentation
* Company policies
* Study material
* Other text-based PDF documents

## Project Structure

```text
PDF-RAG-Chatbot-LangChain/
│
├── app (2).py
├── README.md
├── requirements (2).txt
├── env.example
├── .gitignore
└── venv/                 # Local environment - not uploaded to GitHub
```

## Security

API credentials are intentionally excluded from this repository.

The `.gitignore` file prevents local environment files and virtual environments from being uploaded:

```text
.env
venv/
__pycache__/
*.pyc
.DS_Store
```

Users running the project should create their own `.env` file and provide their own API credentials.

## Future Improvements

Possible future enhancements include:

* Support for multiple PDF documents
* Conversation memory
* Improved document chunking
* Hybrid search
* Reranking of retrieved documents
* Retrieval evaluation metrics
* Chat history
* Source citations for retrieved content
* Improved error handling for scanned/image-based PDFs
* Local LLM support using Ollama
* Deployment using Streamlit Cloud or another hosting platform

## Learning Outcomes

Through this project, I worked with:

* Retrieval-Augmented Generation (RAG)
* LangChain
* Vector databases
* FAISS similarity search
* Text embeddings
* PDF document processing
* Large Language Models
* Prompt-based question answering
* Streamlit application development
* Environment variable and API-key management

## Author

**Mayank Goel**

GitHub:
https://github.com/Mayank234566778

---

## License

This project is intended for educational and portfolio purposes.
