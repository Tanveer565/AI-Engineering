
# Context windows — the model's working context

Now imagine you're building a chatbot for a college.

A student asks:

> Based on my college regulations, can I transfer to another college after my second semester?

To answer, your application might send:

1. System instructions defining how the assistant should behave.
2. The student's question.
3. Relevant college regulations retrieved from a database.
4. Some previous conversation messages.

All of this contributes to the model's context.

A context window is the maximum amount of context a model can handle for a particular request, measured in tokens. The exact limit depends on the model.

Think of it as the model's available working space for the current interaction.

### Illustrative context window

System instructions
500 tokens

Conversation history
2,000 tokens

Retrieved documents
1,500 tokens

User question
200 tokens

Available remaining capacity
800 tokens

Illustration only: a hypothetical 5,000-token context budget. Real models have their own limits, and output-token reservations and other request details can affect the usable space.

In a real application, the context may include more than plain text, depending on the model and request type. The input, conversation history, retrieved information, and generated output all need to fit the model's relevant limits.

## What happens when context gets too large?

Suppose your chatbot keeps sending every message from a conversation that has lasted for 500 turns.

Eventually, the request may exceed the model's context limit. The API might reject it, or your application might need to reduce the input before sending it.

Common engineering solutions include:

- Truncation: remove less relevant older messages.
- Summarization: replace lengthy history with a concise summary.
- Retrieval: fetch only the documents or conversation details relevant to the current question.
- Context management: set sensible limits on how much data enters each request.

This leads to an important distinction:

A large context window does not mean the model permanently remembers everything.

If your application doesn't send relevant previous information, you generally cannot assume the model has access to it. Some products provide separate memory features, but that is distinct from the model's context window.

## Why context windows matter for RAG

You mentioned that you're interested in RAG, so here's how this connects to your future projects.

RAG stands for Retrieval-Augmented Generation. Instead of sending every document in a database to the model, your application retrieves the most relevant pieces and places them in the context.

For example:

Your document database
10,000 pages of information

Retriever
Find the most relevant passages

LLM context
Only the relevant passages plus the question and instructions

Generated answer
An answer based on the supplied context and the model's learned knowledge

This helps manage token usage and gives the model relevant source material. However, retrieval doesn't guarantee a correct answer: your retriever can find the wrong passage, and the model can still misinterpret good evidence.

### understand by video :- https://youtu.be/-uW5-TaVXu4?si=QCdAJdP-rlY3cfox