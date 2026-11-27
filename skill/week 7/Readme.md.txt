# Week 7 – GPT-2 Next-Token Probability Analysis

## Introduction

In Week 7, I worked on understanding how a language model predicts the next token using GPT-2. The main aim of this practical was to observe how the model assigns probabilities to different possible next tokens based on the given input prompt.

I used a pretrained GPT-2 model from Hugging Face and implemented the program using Python.

## Tools and Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- GPT-2
- VS Code

## Project Files

- `main.py` – Main Python program for loading GPT-2 and calculating next-token probabilities.
- `requirements.txt` – Contains the required Python libraries.
- `week7_probability_results.csv` – Stores the predicted tokens and their probabilities.
- `README.md` – Project documentation.

## Implementation

First, I installed the required libraries, PyTorch and Transformers.

Next, I loaded the pretrained GPT-2 model and its tokenizer using Hugging Face Transformers.

I used four input prompts:

1. The cat is
2. Artificial intelligence is
3. India is a
4. Machine learning helps

The program converts each prompt into token IDs using the tokenizer.

Then, GPT-2 processes the input and generates logits for the next-token position. I used the softmax function to convert these logits into probabilities.

After that, I used top-k selection with K = 5 to display the five most probable next-token candidates for each prompt, along with their token IDs and probability values.

Finally, I saved the results in a CSV file named `week7_probability_results.csv`.

## How to Run the Program

Open the terminal in the Week 7 folder and activate the virtual environment:

```powershell
..\.myenv\Scripts\Activate.ps1
```

Install the required libraries:

```powershell
python -m pip install -r requirements.txt
```

Run the program:

```powershell
python main.py
```

The first execution requires an internet connection to download the pretrained GPT-2 model.

## Output

The program displays:

- Input prompts
- Input token IDs
- Top 5 next-token candidates
- Candidate token IDs
- Probability values

The results are automatically saved in `week7_probability_results.csv`.

The CSV file contains the prompt, rank, candidate token, token ID, and probability.

## Conclusion

Through this practical, I learned how GPT-2 predicts the next token based on an input sequence. I understood how tokenization, logits, softmax, and top-k selection are used to calculate and display next-token probabilities.

I also learned how to use a pretrained language model with PyTorch and Hugging Face Transformers and save the prediction results in a CSV file.