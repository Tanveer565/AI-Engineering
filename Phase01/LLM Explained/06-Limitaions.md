# Chapter06 — Understanding The Core  Limitations of LLMs
# The limitations of LLMs

This is where you begin thinking like an engineer rather than just a user of AI tools.

LLMs can be extremely useful, but they have limitations that your application must account for.

## Limitation 1: Hallucinations

An LLM can generate an answer that sounds convincing but is false.

For example, a user asks for an official university regulation. The model may produce a plausible rule even when it has no reliable source for it.

Why does this happen? The model is trained to generate outputs based on learned patterns and its available context. Generating a plausible statement is not the same as verifying that the statement is true.

Engineering response: Ground answers in reliable sources when appropriate, require citations or evidence where useful, and validate important claims.

RAG can help provide evidence, but it does not eliminate hallucinations.

## Limitation 2: A context window is not perfect recall

Even if a model can process a large amount of text, it may fail to use a relevant detail buried in that text.

Simply increasing the context size does not guarantee better answers.

Engineering response: Supply relevant information, organize it clearly, retrieve targeted passages, and test performance with realistic questions.

## Limitation 3: Knowledge can be outdated

A model may not know about a recent software release, a newly changed regulation, or today's stock price.

Its built-in knowledge is not automatically a live feed of current information.

Engineering response: Connect the application to appropriate up-to-date sources, APIs, or search systems when current facts matter.

## Limitation 4: Instructions can be misunderstood

A model may ignore a constraint, misunderstand a vague request, or return a different format than expected.

Engineering response: Write clear instructions, provide examples where useful, request structured output, and validate the result in your backend.

## Limitation 5: Outputs are not inherently trustworthy code or data

Suppose the model returns this object:

```
{
  "email": "not-an-email",
  "age": -5
}
```

The output is syntactically valid JSON, but the data may be invalid for your application.

This is why you will later learn TypeScript and Zod validation. Your backend should not assume that a model's output is correct just because it looks structured.

## Limitation 6: LLMs do not automatically perform actions

If you ask a model to send an email, it may generate an email draft. That doesn't mean it actually sent anything.

To perform actions, your application must provide suitable tools, enforce permissions, execute approved operations, and handle their results.

This is the foundation of tool calling and, later, agentic AI.
# Learn More about limitaion on this website :- https://llmguides.ai/learn/llm-limitations/
