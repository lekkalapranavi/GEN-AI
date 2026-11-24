# Week 7 – Autoregressive Text Generation

## Introduction

In Week 7, I worked on a simple autoregressive text generation program using Python. The main aim of this practical was to understand how text can be generated one word at a time by predicting the next word based on the current word.

I used a small collection of sentences related to students and teachers as training text.

## Tools Used

- Python
- VS Code
- Random module

## Project Files

- `autoregression.py` – Python program for generating text.
- `Week7_Output.txt` – Stores the program output.

## Implementation

First, I created a small training dataset containing sentences about students and teachers.

I converted the text into lowercase and split it into individual words using the `split()` function.

Next, I created a dictionary to store the words that appear after each word in the training text. This dictionary is used to select the next word during text generation.

I implemented a function called `generate_text()` that takes a starting word and the maximum number of words to generate.

The program uses `random.choice()` to select the next word from the available words in the dictionary. After selecting a word, it uses that word as the input for the next prediction.

This process continues until the maximum number of words is generated or no next word is available.

## How to Run the Program

Open the terminal in the Week 7 folder and run:

```powershell
python autoregression.py
```

To save the output in a text file, run:

```powershell
python autoregression.py > Week7_Output.txt
```

## Output

I executed the program multiple times and observed that it generated different sentences.

Example 1:

```text
Generated Text:
the student passed examination the teacher explained concepts students the student
```

Example 2:

```text
Generated Text:
the teacher taught students studied hard and passed examination the student
```

The output changes because the program randomly selects the next word using `random.choice()`.

## Conclusion

Through this practical, I learned the basic concept of autoregressive text generation. I understood how a program predicts the next word using the current word and continues generating text step by step.

I also learned how tokenization, dictionaries, loops, and random selection can be used to build a simple next-word prediction system using Python.