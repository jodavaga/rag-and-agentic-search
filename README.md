# RAG and Agentic Search

Learning project exploring Retrieval-Augmented Generation (RAG) and agentic search patterns.

## What is RAG?

Retrieval-Augmented Generation combines a retrieval step (fetching relevant documents/chunks from a knowledge base) with a generation step (an LLM producing an answer grounded in those documents). Instead of relying solely on what the model learned during training, RAG injects up-to-date or domain-specific context at query time.

A basic RAG pipeline looks like:

1. **Ingest** — load source documents (PDFs, web pages, markdown, etc.)
2. **Chunk** — split documents into smaller pieces that fit within context limits
3. **Embed** — convert chunks into vector embeddings
4. **Store** — persist embeddings in a vector database (e.g. Chroma, Pinecone, FAISS)
5. **Retrieve** — given a query, embed it and find the most similar chunks
6. **Generate** — pass the retrieved chunks + query to an LLM to produce a grounded answer

## What is Agentic Search?

Agentic search goes a step further than plain RAG: instead of a single fixed retrieve-then-generate pass, an agent reasons about *how* to search, possibly issuing multiple queries, refining them based on intermediate results, calling tools, and deciding when it has enough information to answer.

Key differences from basic RAG:

- **Multi-step reasoning** — the agent can decide to search again, search differently, or stop
- **Tool use** — search can be combined with other tools (web search, calculators, APIs)
- **Query planning/decomposition** — complex questions get broken into sub-queries
- **Self-evaluation** — the agent can judge whether retrieved context is sufficient before answering

## First Steps

- [ ] Set up a Python environment (`venv` or `uv`)
- [ ] Pick an embedding model and vector store for a minimal RAG pipeline
- [ ] Build a simple ingest → chunk → embed → store pipeline
- [ ] Implement basic retrieval + generation (naive RAG)
- [ ] Evaluate retrieval quality (precision/recall on a small test set)
- [ ] Introduce an agent loop that can issue multiple searches and reason about results
- [ ] Add tool calling (e.g. web search, structured APIs) alongside vector search
- [ ] Compare naive RAG vs. agentic search on the same set of questions

## Project Structure

This repository is currently in early setup. Structure will evolve as the project grows.
