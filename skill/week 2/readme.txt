 Week 2 – Building a Provider-Agnostic LLM Client

 Introduction

In Week 2, I worked on developing a provider-agnostic LLM client. The purpose of this practical was to understand how an application can communicate with different Large Language Model providers without completely changing its application logic.

I integrated Google Gemini and Ollama into the project and created a common client structure to handle requests from different providers.

 Objectives

- Understand the concept of provider-agnostic LLM applications.
- Integrate multiple LLM providers into one application.
- Learn how to send prompts and receive model responses.
- Implement provider selection.
- Understand API communication and error handling.
- Test the functionality using unit tests.

 Implementation

I extended my previous practical by creating an LLM client that supports different AI providers.

I integrated Google Gemini using the Google GenAI library and configured Ollama to communicate with a locally available language model.

The client was designed to select the required provider and generate responses using the corresponding implementation.

I also used environment variables to manage configuration settings and created a separate test file to verify the client functionality.

 Technologies Used

- Python
- Google Gemini API
- Ollama
- Requests
- Python-dotenv
- Pytest

 Project Files

- llm_client.py – Handles communication with the supported LLM providers.
- main.py – Executes the application.
- test_client.py – Contains unit tests for the LLM client.
- requirements.txt – Lists the required Python libraries.
- .env – Stores configuration values.

 Execution

To execute the application:


python main.py


To execute the unit tests:


python -m pytest -v


 Output and Observation

The application was tested using the configured LLM client.

The unit testing process completed successfully with the following result:


Gemini response generation was tested successfully.

Ollama was also configured as a provider. However, local model execution was limited by the available system memory, which prevented successful inference on the system.

Learning Outcomes

Through this practical, I understood how multiple LLM providers can be integrated into a single application.

I learned about provider selection, API communication, reusable code structures and unit testing.

I also understood that different AI providers may have different system requirements and configuration methods.
