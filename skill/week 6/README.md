# Week 6 – Golden Question Set and Llama 3.2 Baseline Evaluation

## Introduction

In this week, I worked on creating a Golden Question Set and testing it using the Llama 3.2 model. The main aim was to check how well the model answers questions related to the topics covered in our Generative AI course.

I created a set of 30 questions with expected answers and keywords. I used these questions to evaluate the model and understand its response quality.

## Tools and Technologies Used

- Python
- Ollama
- Llama 3.2
- Requests library
- JSON
- CSV

## Project Files

The Week 6 folder contains the following files:

- `main.py` – Runs the questions through the Llama 3.2 model and evaluates the responses.
- `golden_set.json` – Contains 30 questions, expected answers, and keywords.
- `requirements.txt` – Contains the required Python package.
- `baseline_results.csv` – Stores the results of the model evaluation.

## Implementation

First, I checked whether Ollama was installed and whether the Llama 3.2 model was available on my system.

I created `golden_set.json` and added 30 questions related to topics such as tokenization, BPE, WordPiece, SentencePiece, token economics, context windows, rate limits, autoregressive generation, temperature, top-k, top-p, embeddings, and Transformers.

Next, I created `main.py` to connect Python with the local Ollama API. The program sends each question to the Llama 3.2 model and collects its response.

The program compares the model's answer with the expected answer using keyword matching. Based on the keyword coverage, each response is marked as PASS or REVIEW. If an error occurs while generating a response, it is marked as ERROR.

The results are saved automatically in `baseline_results.csv`.

## How to Run the Project

Open the terminal in the Week 6 folder and run these commands:

```powershell
..\.myenv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python main.py
```

Make sure Ollama is running and the Llama 3.2 model is available before starting the program.

## Output

After running the program, it processes all 30 questions one by one and displays the evaluation progress in the terminal.

The generated `baseline_results.csv` file contains:

- Question ID
- Expected answer
- Model answer
- Matched keywords
- Missing keywords
- Score
- Status
- Source
- Model name
- Release version

The evaluation is recorded as the first baseline, Release v0.1.

## Conclusion

Through this practical, I learned how to create a Golden Question Set and evaluate a local LLM using a fixed set of questions. I also learned how to connect Python with Ollama, send prompts to Llama 3.2, compare generated answers, and save evaluation results in a CSV file.

This practical helped me understand how baseline evaluation works and why testing an LLM with consistent questions is useful for checking its performance.