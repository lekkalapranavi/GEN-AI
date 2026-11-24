# Week 5 – Token Economics: Cost and Rate-Limit Budgeting

## Overview

In this week, I worked on estimating the token usage, API cost, and rate-limit requirements of a hypothetical LLM feature before building it. The objective was to understand whether the planned request volume could fit within the configured usage limits and budget.

## Project Files

The project contains:

- `budget.py` – calculates token usage, estimated cost, and capacity checks.
- `test_budget.py` – contains unit tests for the budgeting calculations.
- `requirements.txt` – lists the required package.
- `.env` – stores the input assumptions and budget settings.

## Configuration

I used the following example assumptions in the environment configuration:

```env
INPUT_PRICE_PER_MILLION=0.30
OUTPUT_PRICE_PER_MILLION=1.20
REQUESTS_PER_DAY=2000
AVG_INPUT_TOKENS=1200
AVG_OUTPUT_TOKENS=300
PEAK_REQUESTS_PER_MINUTE=30
RPM_LIMIT=60
TPM_LIMIT=100000
MONTHLY_BUDGET_USD=50
DAILY_BUDGET_USD=2
SAFETY_MARGIN_PERCENT=20
```

These are the configured example values used for the budgeting exercise. They are assumptions for the calculation, not measured usage from a deployed application.

## Implementation

I created a `FeatureBudget` class in `budget.py`. The program reads the configuration values and calculates the expected daily input tokens, output tokens, and total tokens.

It also estimates daily and monthly API costs using the configured input and output prices. The program applies a safety margin when checking peak requests per minute and tokens per minute against the configured limits.

The program checks:

- Whether the estimated peak RPM fits within the RPM limit.
- Whether the estimated peak TPM fits within the TPM limit.
- Whether the daily cost fits within the daily budget.
- Whether the monthly cost fits within the monthly budget.

## Observed Results

With the configured assumptions, the program produced these results:

```text
Input tokens per day: 2,400,000
Output tokens per day: 600,000
Total tokens per day: 3,000,000
Estimated daily cost: $1.4400
Estimated monthly cost: $43.20
Peak RPM with safety margin: 36
Peak TPM with safety margin: 54,000
```

The RPM capacity check passed. The TPM capacity check passed. The daily budget check passed. The monthly budget check required review.

The monthly budget check required review because the estimated monthly cost with the 20 percent safety margin is $51.84, which is above the configured monthly budget of $50. The program therefore recommended revising the assumptions, limits, or design before implementation.

## Testing

I created four unit tests in `test_budget.py` to check the budgeting calculations and limit validations.

The tests covered:

- Cost estimation.
- A case where capacity checks pass.
- A case where the RPM limit is exceeded.
- A case where the monthly budget is exceeded.

All four tests passed:

```text
Ran 4 tests
OK
```

## What I Learned

I learned how token counts and model pricing can be used to estimate the cost of an LLM feature. I also understood that checking only the average daily cost is not enough; peak request rates, token-per-minute limits, and a safety margin should also be considered.

## Conclusion

This activity demonstrated how to perform an initial cost and rate-limit assessment before developing an LLM-based feature. The calculations and unit tests helped verify the budgeting logic and identify that the example monthly budget needed review after applying the safety margin.
