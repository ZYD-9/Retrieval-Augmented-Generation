# Langchain question answering with Ollama

This project demonstrates how to perform question answering with Langchain and Ollama using a PDF document as a source of information.

## Installation

* Install the required libraries:
  - !pip install --q unstructured langchain
  - !pip install -U langchain-community
  - !pip install --q chromadb
  - !pip install colab-xterm
* Other Commands to do 
  - !ollama pull nomic-embed-text
  - !ollama pull llama2 (I switched to Mistral because its lighter)

## Usage

1. Upload your PDF document to Google Drive.
2. Update the `pdf_path` variable in the code with the path to your PDF document.
3. Run the code cells in the notebook to load the document, split it into chunks, create a vector database, and define the question answering chain.
4. Use the `chain.invoke()` function to ask questions and get answers.

## Notes

* This project uses the `mistral` model from Ollama for question answering. You can try other models like `llama2` by updating the `my_model` variable.
* The `RecursiveCharacterTextSplitter` is used to split the document into chunks of 1000 characters with an overlap of 100 characters. You can adjust these parameters as needed.
* The `Chroma` vector database is used to store the document chunks and their embeddings.
* The `MultiQueryRetriever` is used to retrieve relevant chunks from the vector database based on the question.
* The `ChatPromptTemplate` is used to format the question and context for the Ollama model.
