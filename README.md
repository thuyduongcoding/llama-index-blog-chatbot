# llama-index-blog-chatbot: RAG System with Llama-Index blogs

## Overview

This project involves the development of a Retrieval-Augmented Generation (RAG) system using Llama-Index. The system is designed to crawl, preprocess, and utilize the Llama-index blog content. 

Link to the blogs: [https://www.llamaindex.ai/blog](https://www.llamaindex.ai/blog)

## File Descriptions

1. **`crawl_data_and_build_from_scratch.ipynb`**  
   Contains the code for crawling and preprocessing Llama-Index blogs, as well as building the RAG system from scratch.

2. **`chatbot.ipynb`**  
   Demonstrates the implementation of the RAG system using Llama-Index.

3. **`crawl_content.pkl`**: generated after running the `crawl_data_and_build_from_scratch.ipynb`  
   A serialized file containing the extracted crawl content from the crawling process.

4. **`embedding.pkl`**: generated after running the `crawl_data_and_build_from_scratch.ipynb`  
   A serialized file containing the embeddings of the crawl content for future use.

## Chunking Methodology

To effectively organize and extract information from the crawled blogs, the following chunking strategy was employed:

- **Title Extraction**: The `<h1>` HTML component is identified as the blog title.
  
- **Session Chunking**: The content is divided into sections based on `<h2>` and `<h3>` components. Each section title is treated as a session title, with the subsequent content captured until the next session title is encountered. This approach allows for structured extraction of both blog titles and session titles within the RAG system.

## Model Selection

### Language Models (LLMs)

- **gpt-3.5-turbo**: 
  - Performance: Excellent; accurately answers all provided questions.
  
- **gpt-4**: 
  - Performance: Excellent; also answers all questions correctly.
  - Note: High cost incurred during testing ($4 mistakenly spent on generating test cases).

- **gpt-4o-mini**: 
  - Performance: Excellent; a cost-effective alternative.

### Embedding Models

- **text-embedding-3-small**:
  - Performance: Excellent; effectively handles query and response selection.
