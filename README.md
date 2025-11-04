
***

# Ecommerce AI Chat Assistant

**By Rithika Ashok**

## Project Overview

A cost-efficient, retrieval-augmented AI chatbot built for a demo ecommerce website to accurately answer customer FAQs and contextually promote the company’s digital products within live conversations. The solution is demoed via a web mockup and is designed for scalability.

***

## Sprint 1

### Objectives

- **FAQ Handling:** Retrieve & respond to customer queries from a predefined product dataset.
- **Product Promotion:** Naturally recommend relevant digital products within chat responses.
- **Budget Constraint:** Leverage RAG (Retrieval-Augmented Generation) to avoid expensive LLM training.
- **Integration:** Working demo using a web app and chatbot.
- **Scalability:** Extendable architecture for larger data and catalogs.

### Solution Approach

- **Mock Ecommerce Site:** Built with React.js to showcase chatbot.
- **Mock Data:** Generated synthetic product/furniture data via Google Gemini LLM (validated with Zod), seeded into MongoDB.
- **Database:** MongoDB Atlas stores product docs + vector embeddings, supports vector index (cosine similarity) for hybrid search.
- **Hybrid Retrieval Agent:**
  - **Semantic Vector Search:** For fuzzy, natural language matching.
  - **Keyword Search:** For exact matches.
  - **Result Fusion:** Combines both for accuracy and relevance.
- **Frontend:** React-based UI for chat interaction.
- **Backend:** Node.js, TypeScript, LangChain + Gemini API.

### System Architecture

```
User → React UI → LangChain Agent (Gemini) → MongoDB (Vector Index + Keyword) → Agent → UI
```

**Pipeline:**
- **Data Layer:** MongoDB (items & vector index)
- **Processing:** LangChain hybrid retriever (keyword & vector)
- **Reasoning:** Google Gemini LLM as core agent
- **UI:** React

### Key Features

- Decides dynamically between database search and direct answers
- Hybrid search combining semantic and keyword-based results
- Maintains conversational memory
- Multi-step reasoning: perceive → plan → act → respond
- Demo video:  
  - [Sprint 1 Demo #1](https://www.loom.com/share/26292708159c4903bbdb98c5faa5e63d)  
  - [Sprint 1 Demo #2](https://www.loom.com/share/bc7aab459fd14b8c8876d341f187ce28)  

***

## Next Steps & Goals

**From discussion:**
- Support multiple data/document sources in the retrieval agent
- Refine LLM prompts (handle sensitive topics, profanity, etc.)
- Establish more granular agent pathways based on intent & input
- Replace mock data with real-world catalog
- Improve result fusion/ranking algorithm
- Support user-based recommendations & personalization
- Prepare for deployment on cloud (e.g., AWS) for scalability

***

## Tech Stack

- **Frontend:** React.js
- **Backend:** Node.js, TypeScript
- **AI/NLP:** LangChain, Google Gemini API
- **Database:** MongoDB (NoSQL), Atlas Vector Index
- **Validation:** Zod

***

## Feedback

_(Space for reviewer notes here)_

***

## How to Run

1. Clone this repo and `cd` into the project folder.
2. Install dependencies:
    ```
    npm install
    ```
3. Setup environment variables for Google Gemini, MongoDB, etc.
4. Seed mock data (run provided scripts if available).
5. Start development servers for backend and frontend.
6. Access demo via local web browser.

***

## License

MIT (or your choice)

***

Feel free to expand sections for deployment, contributing, or more technical details if needed!
