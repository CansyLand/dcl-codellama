# How to Train CodeLlama

This guide provides steps to fine-tune the CodeLlama-7b-Instruct model, specialized for generating code based on instructions.

## Download the LLM

First, obtain the CodeLlama-7b-Instruct model from its official repository:

[CodeLlama-7b-Instruct on GitHub](https://github.com/facebookresearch/codellama)

This model is the smallest variant trained specifically for code generation from instructions.

## Prepare the Data

You will find the training data within the `.jsonl` file, formatted as follows:

jsonCopy code

```
{
  "prompt": "Assign a parent to an entity.",
  "completion": "Transform.create(childEntity, { parent: parentEntity });"
}
```

## Formatting

Before feeding the data to the LLM, convert it into the instruction format on which CodeLlama Instruct was fine-tuned:

plaintextCopy code

```
<<SYS>>\n{{System Prompt}}\n<</SYS>>\n\n[INST]{{prompt}}[/INST]{{completion}}
// Example
<<SYS>>You are an expert DCL coder<</SYS>>\n\n[INST]Assign a parent to an entity.[/INST]Transform.create(childEntity, { parent: parentEntity });
```

This format ensures the model recognizes the structure of the prompts and completions as they were used during its initial fine-tuning.

## Fine-Tuning

I have initially tested the feasibility of fine-tuning on my M1 MacBook using [slowllama](https://github.com/okuvshynov/slowllama). However, for more extensive training sessions, it is advisable to utilize more powerful hardware to accommodate the computational demands.
