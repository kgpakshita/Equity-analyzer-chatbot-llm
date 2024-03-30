
# Equity Research Analyzer Chatbot

This chatBot is a user-friendly news research tool designed for effortless information retrieval. Users can input article URLs and ask questions to receive relevant insights from the stock market and financial domain.

![](chatbot.jpg)

## Problem statement

Financial analysts and investors face a growing challenge: staying informed in a fast-paced market flooded with financial news. Manually sifting through numerous articles to extract key insights is time-consuming and inefficient. Existing solutions, such as large language models (LLMs), often require copying entire documents and have limitations in handling large datasets or providing source attribution.

## Why Not ChatGPT?

While ChatGPT is powerful, it falls short in specific areas:

- **Inconvenient Input:** Copying full articles can be time-consuming. This chatbot eliminates that need.
- **Aggregate Knowledge Base:** When questions lack a clear source, comprehensive analysis is crucial. This chatbot builds a knowledge base to address this.
- **Input Length Limitations:** ChatGPT's 4000-word limit for input restricts its ability to handle large datasets. This chatbot leverages a knowledge base for scalability.

## Process

1. ### Document Ingestion:
   - Users provide news articles (URLs or PDFs).
   - The system utilizes `textloader` or `unstructuredURLLoader` (Langchain) for loading.

2. ### Efficient Text Splitting:
   - The loaded text is divided into 'n' smaller chunks.
   - A `characterTextsplitter` or `recursivetextsplitter` (Langchain) handles splitting, ensuring words remain intact to avoid information loss.
   - Chunked text is further merged and overlapped to optimize for search efficiency and alleviate token limitation issues.

3. ### Vector Database & Retrieval:
   - Chunks are converted into vector representations for efficient similarity search.
   - `faiss` (Facebook AI Similarity Search library) powers the retrieval engine.
   - It swiftly identifies text chunks most relevant to a user's question.

4. ### Question-Answering
   - `retrieval qna` identifies the most pertinent chunks based on the user's question.
   - These relevant chunks feed into a prompt generation process.

5. ### Large Language Model (LLM) & Answer Generation:
   - An LLM, leveraging the identified chunks, generates a comprehensive answer.
   - The answer reflects precise information extracted from the source materials.

6. ### Source Attribution:
   - Each answer includes a reference link back to the original source material using stored metadata, ensuring transparency and credibility.

## Features

- Load URLs or upload text files containing URLs to fetch article content.
- Process article content through LangChain's UnstructuredURL Loader
- Construct an embedding vector using OpenAI's embeddings and leverage FAISS, a powerful similarity search library, to enable swift and effective retrieval of relevant information
- Interact with the LLM's (Chatgpt) by inputting queries and receiving answers along with source URLs.


## Built with Streamlit:

This project is built using Streamlit, facilitating a user-friendly, interactive web-based experience.
Below is the video presentation of the app
## Video presentation

