# Phase 1.1 — Understanding Large Language Models (LLMs)

## 1. What exactly is an LLM?

LLM stands for Large Language Model. Examples include models from OpenAI, Anthropic, and Google.

An LLM is an AI model trained on enormous amounts of data to learn patterns in language and other information. It uses those learned patterns to generate responses, write code, summarize documents, answer questions, and perform many other tasks.

But here's the most important idea:

An LLM generates output by repeatedly predicting what token should come next.

Let's understand that.

Imagine you give an LLM this input:

YOUR INPUT

## JavaScript is a

POSSIBLE NEXT TOKENS

### language

High probability

### programming

Possible

### framework

Possible

Illustrative possibilities, not actual model probabilities.

The model selects a next token, then predicts another token using the context available to it. This process repeats until it reaches a stopping condition.

For example:

- Input: `JavaScript is a`
    
- Generated continuation: `programming language used to build web applications.`
    

The model doesn't necessarily plan the entire sentence in advance. It generates a sequence of tokens, each influenced by the preceding context.

### How does it know what to say?

During training, the model learns statistical patterns and representations from data. Through additional training and alignment techniques, models can also become better at following instructions and producing useful responses.

It does not simply store every sentence it has seen and retrieve the correct one. It learns patterns that help it generate new combinations of information.

This is why LLMs can write code they have never seen in precisely that form, but can also confidently produce incorrect information.

Why this matters to you: When building an AI application, you aren't directly programming every answer. You're providing instructions, context, tools, and constraints to a model that generates the output.

### understand by video :- https://youtu.be/LPZh9BOjkQs?si=oek-i0Wn3HmldaVz