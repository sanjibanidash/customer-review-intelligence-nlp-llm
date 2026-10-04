# What Can Go Wrong With Generative AI?

## Introduction

Generative AI can produce remarkably convincing answers. But that is also what makes it risky: something can sound correct without actually being correct.
While building my customer-review project, I learned that using an LLM is not the same as automatically getting reliable results.

## Hallucination and Inconsistency

An LLM may generate information that is not present in the input. If a customer review never mentions battery life, the model should not invent an opinion about it.
Outputs can also change when prompts, examples, or instructions change. This makes prompt design, validation, and evaluation important.

## Classification Is Not Always Simple
Consider a review saying:
"The remote is easy to program but doesn't work with my soundbar."

Is this about setup or compatibility?
It is actually about both. Forcing it into one category can create errors.
In my experiment, zero-shot classification achieved approximately 33.3% accuracy, while few-shot achieved approximately 20.8%.
That result was particularly useful because it showed that few-shot prompting does not automatically improve performance. The quality and coverage of examples matter.

## Other Risks
Generative AI also introduces concerns around:
- Cost and latency
- Privacy and API security
- Bias
- Unreliable output formats
- Difficulty reproducing results
- Lack of proper evaluation

## Conclusion
LLMs are powerful, but they should be treated as components of a system—not as unquestionable sources of truth. Good AI requires validation, evaluation, security, and human reasoning.