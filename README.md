# LangChain Documentation Helper

This is a Streamlit application that allows you to ask questions about the LangChain documentation. It uses a Retrieval-Augmented Generation (RAG) pipeline to retrieve relevant information from the documentation and generate answers.

## Features

- **Ask questions in natural language**: Ask questions about LangChain and get answers in a conversational format.
- **Cited sources**: The application cites the sources from the LangChain documentation that were used to generate the answer.
- **Streamlit interface**: The application is built with Streamlit, providing a simple and intuitive user interface.
- **RAG pipeline**: The backend is powered by a RAG pipeline that uses LangChain, OpenAI, and Pinecone to retrieve and generate answers.

## How to run the application

1. **Install dependencies**:
   ```bash
   pipenv install
   ```

2. **Set up your environment variables**:
   Create a `.env` file in the root of the project and add the following environment variables:
   ```
   OPENAI_API_KEY="your-openai-api-key"
   PINECONE_API_KEY="your-pinecone-api-key"
   TAVILY_API_KEY="your-tavily-api-key"
   ```

3. **Run the Streamlit application**:
   ```bash
   streamlit run main.py
   ```

## How it works

The application uses a RAG pipeline to answer questions about the LangChain documentation. The pipeline consists of the following components:

- **Streamlit**: The user interface is built with Streamlit.
- **LangChain**: The RAG pipeline is built with LangChain, which orchestrates the different components of the pipeline.
- **OpenAI**: The application uses OpenAI's `gpt-5.2` model to generate answers and `text-embedding-3-small` for embeddings.
- **Pinecone**: The LangChain documentation is stored in a Pinecone vector store, which is used to retrieve relevant documents based on the user's query.

When a user asks a question, the application retrieves the most relevant documents from the Pinecone vector store. The retrieved documents are then passed to the OpenAI model, which generates an answer based on the retrieved information. The application then displays the answer to the user, along with the sources that were used to generate the answer.

## Ingesting documents

To ingest the LangChain documentation, you need to run the `ingestion.py` script. This script will crawl the LangChain documentation, split the documents into chunks, and store them in a Chroma vector store.

1. **Run the ingestion script**:
   ```bash
   python ingestion.py
   ```

This will create a `chroma_db` directory in the root of the project, which will contain the vectorized documentation.
