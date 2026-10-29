# Chapter04 — Understanding Temperature in Large Language Models
# Temperature — controlling randomness in generation

Temperature is a parameter that can influence how an LLM selects its next token.

In simplified terms:
- Lower temperature: generally makes the model's token selection more concentrated on higher-probability choices.
- Higher temperature: generally makes less likely choices more competitive, producing more varied outputs.

Temperature does not increase the model's intelligence, add knowledge, or guarantee accuracy.

Consider this prompt:

> Give me a name for a task management application.

At a lower temperature, the model might repeatedly favor conventional names such as "Task Manager" or "TaskFlow." At a higher temperature, it may explore more unusual possibilities.

## Temperature in practice

|Temperature|Typical use|
|---|---|
|`0` or near `0`|More consistent extraction or classification|
|`0.2–0.4`|Structured assistant responses, many coding tasks|
|`0.5–0.8`|General conversation and balanced creativity|
|`0.9+`|Brainstorming and more varied creative output|

These are rough starting points, not universal rules. Different models respond differently, and some APIs don't expose temperature for particular models or modes.

### Important detail

Even at temperature `0`, you shouldn't assume perfect determinism. Hardware, infrastructure, model updates, and other implementation details can cause variations. Some APIs also have restrictions on which sampling parameters can be used together.

As an AI engineer, you should evaluate model behavior on your actual task rather than blindly selecting a temperature from a table.

## When should you care about temperature?

Imagine you're building two features.

Feature A: Extract an email address

You want consistent, exact extraction. Start with a low temperature if supported, and validate the result. Temperature alone cannot guarantee a valid email address.


Feature B: Generate startup ideas
You may prefer a higher temperature to encourage variety. You'll still need to evaluate the ideas for relevance and quality.

Engineering takeaway: Use temperature to influence the style and variability of generation, not as a substitute for validation, testing, or good instructions.
