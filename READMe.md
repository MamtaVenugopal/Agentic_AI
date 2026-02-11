
![rag-framework](https://github.com/user-attachments/assets/8b6a8592-9416-4534-a0ab-9823e50923bc)
Input: The question to which the LLM system responds is referred to as the input. If no RAG is used, the LLM is directly used to respond to the question.
Indexing: If RAG is used, then a series of related documents are indexed by chunking them first, generating embeddings of the chunks, and indexing them into a vector store. At inference, the query is also embedded in a similar way.
Retrieval: The relevant documents are obtained by comparing the query against the indexed vectors, also denoted as "Relevant Documents".
Generation: The relevant documents are combined with the original prompt as additional context. The combined text and prompt are then passed to the model for response generation which is then prepared as the final output of the system to the user.
