
# LLMs, Transformers, Tokens & Tokenization

## 1. What is an LLM?

LLM stands for Large Language Model.

A Large Language Model is an AI model trained on large amounts of data so that it can understand patterns in language and generate text in response to a prompt.

### Breaking down the term

- Large: The model is trained on large datasets and typically has many learned parameters.
- Language: It works with human language, including text and, in some models, other modalities.
- Model: A mathematical system that learns patterns from data.

LLMs are trained using data such as books, articles, websites, code, and other text sources. The exact training data varies by model.

### Examples of LLMs

- ChatGPT models from OpenAI
- Gemini models from Google
- Claude models from Anthropic

### What can LLMs do?

- Answer questions.
- Generate text and summaries.
- Explain programming concepts.
- Write and debug code.
- Translate languages.
- Help build AI-powered applications.

Key idea: An LLM learns patterns from training data and uses those patterns to generate responses. It does not simply retrieve a memorized answer for every question.

## 2. What does GPT stand for?

GPT stands for Generative Pre-trained Transformer.

G — Generative

The model can generate new content, such as text, answers, and code.

P — Pre-trained

The model learns general patterns from a large training dataset before being adapted or fine-tuned for particular tasks.

T — Transformer

A neural network architecture that uses attention mechanisms to process relationships between elements in a sequence.

## 3. What is a Transformer?

A Transformer is a neural network architecture introduced in the 2017 research paper Attention Is All You Need by researchers at Google and other institutions.

Transformers became foundational to many modern language models because they can process sequences while learning which parts of the input are relevant to one another.

### What is the attention mechanism?

Attention helps a model determine which other words or tokens are relevant when interpreting a particular token.

Consider this sentence:

> The bank was too steep to climb.

The word bank can have multiple meanings:

- A financial institution.
- The land beside a river.

The word steep and the phrase to climb provide clues that bank refers to a slope or riverbank, not a financial institution.

Attention helps the model use relationships between tokens to interpret the context.

Remember: Attention does not work by simply comparing two words. It computes relationships across token representations to determine how information should be combined.

### How does a Transformer generate text?

Most autoregressive language models generate text one token at a time.

For example:

Input prompt

We finally sat

Predict next token

## down

Updated sequence

We finally sat down

Next token

## on

Continuing generation

We finally sat down on the bench.

The process works as follows:

1. The model receives the input prompt.
2. The prompt is converted into tokens and then token IDs.
3. The model processes the token representations using its learned parameters.
4. It calculates probabilities for possible next tokens.
5. A decoding strategy selects the next token.
6. The selected token is added to the sequence.
7. The process repeats until a stopping condition is reached.

The model generally calculates a distribution over possible next tokens, rather than generating a complete sentence in one step. The chosen token is not necessarily the highest-probability token every time; the decoding strategy and settings influence selection.

Important distinction: GPT is one family of Transformer-based models. Gemini and Claude also use Transformer-based techniques, but they are not all GPT models.

## 4. Tokens and Tokenization

### What is a token?

A token is a small unit of text that a language model processes.

A token can be:

- A complete word
- Part of a word
- Punctuation
- A text fragment that includes a space

For example, the sentence:

`Who is PM of India?`

could be split into tokens such as `Who`, ` is`, ` PM`, ` of`, ` India`, and `?`.

The exact split depends on the tokenizer and model.

Important: One token does not always equal one word.

### What is tokenization?

Tokenization is the process of breaking input text into tokens.

The software that performs this process is called a tokenizer.

```
Input Text
    ↓
Tokenizer
    ↓
Tokens
    ↓
Token IDs
```

### Why do we need tokenization?

Language models generally process numerical representations rather than raw text strings.

Therefore, the input text is split into tokens, and those tokens are mapped to numerical IDs.

## 5. What are Token IDs?

A token ID is an integer assigned to a token in a tokenizer's vocabulary.

For example, imagine a tokenizer uses the following mapping:

| Token    | Example ID |
| -------- | ---------- |
| `Hello`  | 101        |
| ` world` | 205        |
| `!`      | 12         |

These are illustrative numbers, not actual IDs from a particular model.

### How does the process work?

1. The user enters a prompt.
2. The tokenizer splits the text into tokens.
3. Each token is mapped to its corresponding ID.
4. The sequence of IDs is passed to the model.
5. The model generates output token IDs.
6. The tokenizer decodes those IDs back into text.

```
"Hello world!"
      ↓
   Tokenizer
      ↓
 [101, 205, 12]
      ↓
  Language Model
      ↓
 Generated Token IDs
      ↓
    Decoder
      ↓
 Generated Text
```

Remember:

- Token = a unit of text.
- Token ID = an integer associated with that token.
- Tokenizer = software that converts between text and token IDs.

Each model's tokenizer may have a different vocabulary. Consequently, the same sentence can produce different token boundaries and IDs when different tokenizers are used.

## 6. Visualizing Tokens

The instructor demonstrates tokenizer visualization tools to show how text is split into tokens and how IDs are assigned.

You can explore:

- [Hugging Face](https://huggingface.co/) — tokenizer tools and model resources.
- [OpenAI Tokenizer](https://platform.openai.com/tokenizer) — inspect tokenization for supported OpenAI models.

Try entering:

`Who is PM of India?`

Observe:

- How many tokens are produced.
- Whether spaces are included in tokens.
- Whether a word is split into multiple pieces.
- The token IDs.
- How the output changes when you select another supported model.

The exact output depends on the tokenizer selected.

## 7. Implementing Tokenization Using Python

The lecture uses the `tiktoken` library to encode text into token IDs and decode IDs back into text.

### Step 1: Install the library

```
%pip install tiktoken
```

### Step 2: Import the library

```
import tiktoken
```

### Step 3: Create a tokenizer

```
encoding = tiktoken.encoding_for_model("gpt-4o")
```

This selects the tokenizer encoding associated with a supported OpenAI model.

### Step 4: Convert text into token IDs

```
text = "Who is PM of India?"token_ids = encoding.encode(text)print(token_ids)print("Number of tokens:", len(token_ids))
```

- `encode()` converts text into token IDs.
- `len(token_ids)` counts the number of IDs.

### Step 5: Convert token IDs back into text

```
result_ids = encoding.encode("PM of India is Modi ji")result = encoding.decode(result_ids)print(result)
```

Expected output:

```
PM of India is Modi ji
```

### Complete example

```
import tiktokentext = "Hello, world!"encoding = tiktoken.encoding_for_model("gpt-4o")token_ids = encoding.encode(text)decoded_text = encoding.decode(token_ids)print("Original text:", text)print("Token IDs:", token_ids)print("Number of tokens:", len(token_ids))print("Decoded text:", decoded_text)
```

### Important notes

- Token IDs depend on the selected encoding.
- `tiktoken` supports OpenAI encodings; it is not a universal tokenizer for every LLM.
- Decoding a complete sequence produced by the same encoding should reproduce the original text.
- A tokenizer does not itself generate an LLM response; it handles text-to-token and token-to-text conversion.

## 8. What is a Context Window?

A context window is the amount of tokenized information a model can process in a single request.

It may include:

- System instructions.
- User prompts.
- Previous conversation messages.
- Retrieved documents.
- Tool instructions and results.
- Other input information.
- Generated output, depending on the model's context rules.

### Example

Imagine an LLM has a context capacity of 8,000 tokens.

If the application sends a large conversation history and a long document, that information uses part of the available context budget. The application must also account for the response it wants the model to generate.

The number 8,000 is only an example; actual limits vary by model.

### Why is the context window important?

When a request exceeds the model's limits, an application may need to:

- Remove older conversation messages.
- Summarize previous discussions.
- Retrieve only relevant document sections.
- Reduce unnecessary prompt text.
- Leave sufficient space for the model's response.

### Context window vs. memory

These concepts are related but different.

- Context window: Information available to the model during a request.
- Memory: Information that an application or product stores or maintains for use beyond an individual request.

A chat application's memory or conversation-history behavior is not necessarily the same as its model's context capacity.

## 9. Maximum Tokens and Token Limits

When using an LLM API, developers may be able to configure the maximum number of tokens generated in a response.

This helps control:

- Response length.
- API cost.
- Latency.
- Application behavior.

For example, an application might limit a response to 300 output tokens.

```
max_output_tokens = 300
```

This is a conceptual example, not a complete API call. The actual parameter name depends on the provider and API.

Important distinction:

| Term                  | Meaning                                    |
| --------------------- | ------------------------------------------ |
| Context window        | Token capacity available for a request     |
| Input tokens          | Tokens supplied to the model               |
| Output tokens         | Tokens generated by the model              |
| Maximum output tokens | The configured ceiling on generated output |

A maximum output-token limit does not mean the model must generate exactly that many tokens. It may stop earlier.

## 10. How Do LLM Providers Charge for Tokens?

Many hosted LLM APIs charge according to token usage.

Costs can depend on:

- The model selected.
- Input tokens processed.
- Output tokens generated.
- Cached input tokens, if separately priced.
- Additional tools or services used.

For example, sending a long document in every request can increase input-token usage even if the response is short.

Pricing changes over time, so check the provider's current official pricing page before estimating costs.

### How can we optimize token usage?

1. Keep prompts concise.
2. Retrieve only relevant sections of documents.
3. Summarize long conversation histories when appropriate.
4. Set a suitable maximum output-token limit.
5. Choose a model appropriate for the task.
6. Monitor actual API usage.

Key takeaway: Tokenization is not only a technical concept. Understanding tokens is also important for building cost-effective AI applications.

## 11. Complete LLM Workflow

Memorize this sequence:

```
User Prompt
    ↓
Tokenization
    ↓
Token IDs
    ↓
LLM Processing
    ↓
Generated Token IDs
    ↓
Decoding
    ↓
Text Response
```

Real-world applications may also include special tokens, chat templates, retrieval, tool calls, and safety processing.

## 12. Key Terms for Revision

| Term                  | Definition                                                            |
| --------------------- | --------------------------------------------------------------------- |
| LLM                   | Large Language Model                                                  |
| GPT                   | Generative Pre-trained Transformer                                    |
| Transformer           | Neural network architecture used by many language models              |
| Attention             | Mechanism that helps a model combine information from relevant tokens |
| Token                 | A unit of text processed by a tokenizer                               |
| Tokenization          | Converting text into tokens                                           |
| Tokenizer             | Software that converts text into tokens and token IDs                 |
| Token ID              | Integer associated with a token in a vocabulary                       |
| Encoding              | Converting text into token IDs                                        |
| Decoding              | Converting token IDs back into text                                   |
| Context window        | Token capacity available to a model request                           |
| Input tokens          | Tokens sent to the model                                              |
| Output tokens         | Tokens generated by the model                                         |
| Maximum output tokens | Upper limit on generated response tokens                              |

## 13. Quick Revision Questions

Try answering these questions without looking at the notes.

1. What does LLM stand for?
2. What does GPT stand for?
3. What is a Transformer?
4. What is the purpose of attention?
5. Does one token always equal one word?
6. What is tokenization?
7. What is the difference between a token and a token ID?
8. What does `encoding.encode()` do?
9. What does `encoding.decode()` do?
10. Why can two models tokenize the same sentence differently?
11. What is a context window?
12. What is the difference between context and long-term memory?
13. What is the difference between input and output tokens?
14. Why would a developer set a maximum output-token limit?
15. How can token usage affect API costs?

## 14. One-Minute Recap

- LLMs learn language patterns from large datasets and generate responses.
- GPT stands for Generative Pre-trained Transformer.
- Transformers use attention to learn relationships between tokens.
- Many LLMs generate text one token at a time.
- Tokenization splits text into model-specific units.
- Token IDs are integer labels assigned to tokens.
- `tiktoken` can encode text into IDs and decode IDs back into text for supported OpenAI encodings.
- A context window limits the tokenized information available to a model request.
- Input and output token usage can affect API costs.
- Efficient prompts, relevant retrieval, and sensible output limits help control token usage.

