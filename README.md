# Chat with your PDFs

This is a Streamlit application that allows users to chat with an AI model about the content of multiple uploaded PDF documents. The application leverages various NLP and document processing libraries to enable a seamless conversational experience.

<b>Please note that the application might run slower than expected due to the usage of HuggingFace, a free alternative to OpenAI API, which may have limitations in terms of processing speed.</b>

## Setup

To run the application, please ensure you have the following dependencies installed:

- Streamlit
- Python-Dotenv
- PyPDF2
- Langchain
- HuggingFace Transformers

You can install the dependencies using pip:

```bash
pip install streamlit python-dotenv pypdf2 langchain transformers
```

## Usage

1. Upload your PDFs by clicking on the "Upload your PDFs here" button in the sidebar.
2. After uploading, click on the "Process" button to initiate the document processing.
3. Enter your questions in the text input box and receive AI-generated responses.

## How it Works

### PDF Processing

1. The uploaded PDFs are processed using PyPDF2 to extract the text content from each page.
2. The extracted text is split into smaller chunks for more efficient processing using the `CharacterTextSplitter` module.

### Conversational AI

1. HuggingFace's Transformers library is used to generate embeddings for the text chunks.
2. The embeddings are then stored using the FAISS library for efficient retrieval.
3. The conversational AI model, based on the `google/flan-t5-xxl` model, is used to provide responses based on the user's queries.
4. The conversation history is maintained using the `ConversationBufferMemory` module.

## Files

- `app.py`: The main script containing the Streamlit application and the necessary functions for document processing and conversation handling.
- `htmlTemplates.py`: HTML templates for formatting the user and bot messages in the chat interface.

## Note

- Make sure to set up your environment variables using a `.env` file for any sensitive information.

Feel free to customize the application and explore the codebase further to enhance its functionality.




