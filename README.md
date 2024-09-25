
# Retrieval-based QA System with Embeddings using LangChain

This project implements a retrieval-based question answering (QA) system using embeddings and the LangChain library. The system processes a text file, creates a vector store, and uses it to answer questions based on the content.

## Contents

The project consists of the following key files:

- `index.js`: The main JavaScript file containing the core logic
- `.env`: Environment file for storing API keys
- `package.json` and `package-lock.json`: Node.js project configuration files
- `readme.md`: Project documentation

## How it Works

1. **Setup and Initialization**:
   - The code imports necessary modules from LangChain and other libraries.
   - It loads environment variables, including the OpenAI API key.

2. **Vector Store Creation**:
   - If a vector store doesn't exist, the system:
     - Reads the input text file
     - Splits the text into chunks
     - Creates embeddings using OpenAI's model
     - Stores these embeddings in a vector store (HNSWLib)

3. **Question Answering**:
   - The system uses a RetrievalQAChain, which combines:
     - The OpenAI language model
     - The vector store as a retriever

4. **Query Processing**:
   - When given a question, the system:
     - Retrieves relevant information from the vector store
     - Uses the language model to generate an answer based on the retrieved context

## Usage

To use this system:

1. Ensure you have the required dependencies installed (see `package.json`).
2. Set up your OpenAI API key in the `.env` file.
3. Prepare your input text file (default name: "The_Creative_Act").
4. Run the `index.js` script, which will:
   - Create or load the vector store
   - Process the specified question
   - Output the answer

## Input and Output

### Input:
- A text file containing the corpus of information
- A question string defined in the `index.js` file

### Output:
- The system logs the answer to the console

## Dependencies

The project relies on several npm packages, including:
- `langchain`: For the core QA and embedding functionality
- `hnswlib-node`: For efficient similarity search
- `dotenv`: For managing environment variables

## Notes

- The system uses OpenAI's API, so ensure you have proper authentication set up.
- The vector store is saved locally, allowing for faster subsequent runs.
- This implementation is designed for Node.js environments.
