# Evaluating and Optimizing RAG Pipelines with BeyondLLM

This project demonstrates how to utilize the BeyondLLM library to create and optimize a Retrieval-Augmented Generation (RAG) pipeline for extracting and analyzing information from YouTube videos using advanced AI models. The primary goal is to develop a robust pipeline that can retrieve specific information from video transcripts and generate accurate answers to user queries.

## Project Overview

### 1. Installation of Required Libraries

The project relies on several key Python libraries:
- **beyondllm**: A toolkit for sourcing, retrieving, and generating responses from data.
- **youtube_transcript_api**: For fetching YouTube video transcripts.
- **llama-index-readers-youtube-transcript**: For reading YouTube transcripts into llama-index.
- **llama_index.embeddings.huggingface**: For embedding text data using models from HuggingFace.

### 2. Setting Environment Variables

To access the necessary APIs, you need to set environment variables for HuggingfaceHub and Google API keys. The keys are securely entered and stored as environment variables to ensure smooth API access during the pipeline execution.

### 3. Data Loading from YouTube Video

Data is sourced from a YouTube video by providing the video URL. The `source.fit` function is used to load and chunk the transcript data, making it easier to manage and process large transcript data efficiently. This step involves specifying the chunk size and overlap to optimize the data handling process.

### 4. Embedding Model Configuration

An embedding model from HuggingFace is configured for transforming text data into embeddings. The model used in this project is `BAAI/bge-small-en-v1.5`. This embedding model helps in encoding the text data into a format suitable for retrieval tasks.

### 5. Creating the Retriever

The retriever component is created using the `retrieve.auto_retriever` function, which takes the loaded data and the embedding model as inputs. The retriever is configured to operate in a hybrid mode with a specified top-k value, allowing it to efficiently retrieve the most relevant data chunks based on the query.

### 6. Setting the Language Model

A language model from the BeyondLLM library, `GeminiModel`, is set up using the Google API key. This model is responsible for generating coherent and contextually relevant answers to user queries based on the retrieved data.

### 7. Generating Answers

The pipeline for generating answers is created using the `generator.Generate` class. This pipeline combines the retriever and the language model to process the user query and generate an accurate response. The generated answers are evaluated using RAG (Retrieval-Augmented Generation) triad evaluations to ensure the quality and relevance of the responses.

## How It Works

1. **Installation**: Install the required libraries using pip.
2. **Environment Setup**: Set the environment variables for HuggingfaceHub and Google API keys.
3. **Data Loading**: Load and chunk the transcript data from the specified YouTube video URL.
4. **Embedding Model**: Configure the HuggingFace embedding model for encoding the text data.
5. **Retriever Creation**: Create a retriever to fetch relevant data chunks based on user queries.
6. **Language Model**: Set up the GeminiModel for generating responses.
7. **Answer Generation**: Use the pipeline to generate and evaluate answers to user queries.

This project showcases the integration of advanced AI models and tools to create an efficient RAG pipeline, enabling the extraction and generation of valuable insights from video content.
