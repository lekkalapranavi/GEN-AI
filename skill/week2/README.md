# Week 2 – Building a Provider-Agnostic LLM Client

## Overview

In this week, I developed a provider-agnostic LLM client that can work with different language model providers. The objective was to separate the application code from provider-specific implementation details.

## Work Completed

I organized the project into separate Python files. The LLM client handles the model request, while the main program uses the client to generate a response. The project includes support for Gemini and Ollama as provider options.

The main project files are:

- `llm_client.py` – contains the LLM client implementation.
- `main.py` – runs the application and sends a prompt.
- `test_client.py` – contains the unit test for the client.
- `requirements.txt` – lists the required Python packages.
- `.env` – stores environment-based configuration.

I used `python-dotenv` to load configuration values from the environment file. The client structure makes it possible to select a provider without changing the overall application workflow.

## Testing and Results

I ran the application using Gemini and verified that it generated a response to the supplied prompt. I also executed the unit test using pytest.

The test completed successfully:

```text
1 passed
```

Ollama with the `llama3.2` model was also configured as a provider option. However, local inference could not complete in my environment because the system was unable to allocate the required CPU memory. Therefore, I used Gemini for the successful response-generation demonstration.

## What I Learned

I learned how to design a reusable client interface instead of writing provider-specific request code throughout an application. I also learned the importance of unit testing and how different providers can have different runtime and resource requirements.

## Conclusion

The activity helped me understand how to build a more flexible LLM application. Separating provider logic from the main program makes the application easier to maintain and extend.
