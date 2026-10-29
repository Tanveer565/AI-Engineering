# Chapter05 — Understanding Inference in Large Language Models
# Inference — what happens when you call an LLM

You've now learned about tokens, context windows, and temperature. Inference connects these concepts to the actual operation of an AI application.

Inference is the process of using a trained model to produce an output from an input.

Training is when the model learns from data and updates its parameters. Inference is when you use the trained model to answer a question, classify text, or generate code.

As a Node.js developer, think of inference as the stage where your application sends a request to a model and receives its result.

## What happens during inference?

1. Your Node.js backend
Receives a user request and constructs the prompt.

2. Tokenization and input preparation
The input is represented in a form the model can process.

3. Model inference
The model processes the context and generates output tokens.

4. API response
Your backend receives the output and relevant usage information, depending on the API.

5. Your application
Validates the result, handles errors, and returns the response to the user.

This is a simplified workflow; real model-serving systems may perform additional preprocessing, batching, caching, and other operations.

## Why inference matters to your projects

Imagine you build a customer-support assistant.

The user asks a question, your backend sends the relevant instructions and context to an LLM, and the model generates a response. Your application then checks whether the response is suitable to return.

The model is responsible for generating output. Your backend is responsible for controlling the application around it.

That distinction is central to AI engineering. You will eventually design systems for:

- Model selection
- Prompt construction
- Streaming responses
- Token and cost tracking
- Validation
- Retries and error handling
- Tool execution
- Retrieval and agent workflows

We'll study these in their respective topics rather than trying to learn everything at once.

