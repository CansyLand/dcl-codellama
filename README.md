
# dcl-codellama

This repository is dedicated to fine-tuning a CodeLlama model specifically for coding with Decentraland SDK 7. Our aim is to develop a system capable of generating training data to fine-tune Large Language Models (LLMs) for Decentraland code generation.

## Project Goal

The primary goal is to automate the extraction of documentation, code examples, and SDK 7 source code from GitHub repositories, converting them into structured training data for LLMs.

### Training Data Example

```
{
  "prompt": "Assign a parent to an entity.",
  "completion": "Transform.create(childEntity, { parent: parentEntity });"
}
```

Within the `.jsonl` file, you'll find over 300 lines of training data. Interestingly, fine-tuning a model does not require an extensive dataset, as the bulk of foundational knowledge has already been established. The model is adept at generating high-quality code; our task is merely to guide its understanding towards adapting new patterns and a detailed knowledge base specific to Decentraland SDK 7.

## Why This Approach?

### Rapid Development of Decentraland SDK

The Decentraland SDK is evolving quickly, outpacing the current AI models' understanding of its latest features and developments.

### Alternatives Considered

#### Why Not ChatGPT?

While Custom GPT models with knowledge retrieval or fine-tuned GPT-4 could technically serve our needs, ChatGPT's proprietary nature and potential high API costs for IDE integration make it less viable for this project.

#### Why Fine-Tuning Over RAG (Retrieval-Augmented Generation)?

LLMs excel at pattern recognition. Introducing new complex patterns, such as an entire SDK, poses challenges, especially when the model's training leans towards an older version like SDK 6. RAG, while useful for information retrieval, lacks the speed and pattern comprehensiveness required for our purposes. Moreover, RAG's reliance on vector-based search limits the scope of documentation parts retrievable in a single query.

## Open Source Philosophy

As Decentraland thrives on community-driven development, sharing research and tools openly aligns with our core values. Plus, the adage "apes together strong" remains relevant, emphasizing the strength found in collaborative effort.

## Why CodeLlama?

CodeLlama is fine-tuned from Llama2, representing the pinnacle of current open-source models. This repository aims to remain model-agnostic, ready to adapt as newer models emerge. It enables studios to further fine-tune the DCL models for their specific use cases with minimal effort.

## The Importance of Local AI

Running LLMs locally, such as through Ollama, offers several advantages:

-   Free usage and integration into IDEs like Visual Studio Code.
-   Immediate response times without the need for an internet connection.
-   No incurred API costs.
