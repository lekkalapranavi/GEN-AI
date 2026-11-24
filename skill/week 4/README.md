# Week 4 – Comparison of BPE, WordPiece and SentencePiece Tokenizers

## Overview

In this week, I compared three pretrained tokenizer implementations: BPE, WordPiece, and SentencePiece. I tested them using sample sentences in English, Telugu, and Hindi to observe how each tokenizer divides text into tokens.

## Tools and Models Used

I used the Hugging Face Transformers library and SentencePiece support.

The tokenizer configurations used in the program were:

- BPE – GPT-2 tokenizer.
- WordPiece – `bert-base-multilingual-cased` tokenizer.
- SentencePiece – `xlm-roberta-base` tokenizer.

The XLM-R tokenizer uses SentencePiece with a BPE-based subword model. The comparison therefore uses pretrained tokenizer implementations and their existing vocabularies.

## Input Sentences

English:

```text
Artificial intelligence is changing the world.
```

Telugu:

```text
కృత్రిమ మేధస్సు ప్రపంచాన్ని మారుస్తోంది.
```

Hindi:

```text
कृत्रिम बुद्धिमत्ता दुनिया को बदल रही है।
```

## Implementation

I created the Python program `tokenizer_comparison.py`. The program loads each pretrained tokenizer, tokenizes the sample sentences, and displays the generated tokens, token IDs, and token counts.

I enabled special tokens during tokenization and did not truncate the input sentences. This allowed the output to show the tokenization result for the complete sample text.

## Observed Results

The token counts produced by my program were:

| Language | GPT-2 BPE | mBERT WordPiece | XLM-R SentencePiece |
|---|---:|---:|---:|
| English | 8 | 10 | 10 |
| Telugu | 112 | 18 | 14 |
| Hindi | 68 | 17 | 14 |

These counts include special tokens.

## Analysis

For the English sentence used in this experiment, GPT-2 produced the lowest token count. For the Telugu and Hindi sentences used in this experiment, XLM-R produced the lowest token counts.

The results are specific to the selected sentences and pretrained tokenizers. Token counts can change depending on the sentence, tokenizer vocabulary, and tokenizer training data. The comparison does not establish that one tokenizer will always be more efficient for every language or input.

## What I Learned

I learned that tokenization is an important step in language-model processing. A tokenizer does not always divide text into complete words; it can split words into smaller subword units. I also observed that tokenization behavior can differ significantly across languages.

## Conclusion

This activity helped me compare different pretrained tokenizers using the same sample sentences. It showed how tokenization affects the number of tokens generated for multilingual text.
