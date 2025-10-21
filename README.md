# RAG_Pipeline_for_LLMs
Large Language Models (LLMs) are powerful, but they have a major limitation: their knowledge is static and limited to the data they were trained on. This is where Retrieval-Augmented Generation (RAG) comes in.

So, What is a RAG Pipeline?
A Retrieval-Augmented Generation (RAG) pipeline consists of two key components:
1. Retriever: Searches a knowledge base for relevant documents based on the user’s query.
2. Generator: Uses retrieved documents as context to generate accurate and relevant responses.
   
RAG improves LLMs by reducing hallucinations through real-world context, ensuring responses are more accurate and grounded in factual information. It also keeps answers up-to-date by retrieving the latest knowledge, eliminating the need for frequent retraining. Additionally, by incorporating external data sources, RAG significantly enhances the factual accuracy of AI-generated responses, which makes LLMs more reliable and context-aware.
   
In the implementation I have :
1.Used Wikipedia as our external knowledge source.
2.Employed Sentence Transformers for embedding text and FAISS for efficient similarity search.
3.Utilized Hugging Face’s question-answering pipeline to extract answers from retrieved documents.

⚙️ Pipeline Flow:
Wikipedia content → Token chunking → Embedding → FAISS retrieval → Question answering

Highlights:
🔹 Disambiguates short/ambiguous terms (e.g., “AI” → “Artificial Intelligence”)
🔹 Token-based chunking with overlap for better context
🔹 Embeddings with all-mpnet-base-v2 + FAISS for fast semantic retrieval
🔹 QA extraction using RoBERTa from top retrieved chunks
🔹 Handles ambiguous queries, providing reliable answers
