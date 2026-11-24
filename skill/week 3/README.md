# Week 3 – LLM Usage Tracking and MongoDB Integration

## Overview

In this week, I extended the LLM client by adding usage tracking and MongoDB logging. The objective was to record information about model requests so that usage, latency, and estimated cost could be reviewed after execution.

## Work Completed

I continued using the provider-based LLM client and added a usage logger. The application records details associated with an LLM request and stores the usage information in MongoDB.

The project contains the following main files:

- `llm_client.py` – sends requests to the selected LLM provider.
- `main.py` – runs the application.
- `usage_logger.py` – handles usage-record logging.
- `test_client.py` – checks the client and logging workflow.
- `requirements.txt` – lists the project dependencies.
- `.env` – stores configuration values and connection settings.

The usage information tracked by the application includes:

- Input token count.
- Output token count.
- Request latency.
- Estimated request cost.

I configured the MongoDB connection through environment settings rather than placing connection details directly in the source code. I also tested the MongoDB Atlas connection after configuring network access for my current IP address.

## Testing and Results

I ran the unit test for the generate-and-log workflow. The test passed successfully:

```text
test_generate_and_log_usage – PASSED
1 passed
```

During a Gemini run, the application recorded an example usage entry with 8 input tokens and 21 output tokens. The recorded latency was approximately 181.6 seconds, and the estimated cost was 0.000084 USD. These values belong to that particular test run and can vary between requests.

## What I Learned

I learned how to capture usage information from an LLM request and store it in a database. I also understood why latency, token consumption, and estimated cost are useful when monitoring an AI-powered application.

## Conclusion

This activity added a monitoring and logging layer to the LLM client. It demonstrated how model usage information can be stored for later inspection and how a database can support the monitoring of generative AI applications.
