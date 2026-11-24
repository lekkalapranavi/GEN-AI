# Week 1 – Introduction to Generative AI and Gemini API

## Overview

In this week, I worked on connecting a Python application with a Large Language Model using the Gemini API. The main objective was to understand how an application can send a prompt to an AI model, receive the generated response, and display it in the terminal.

## Work Completed

I explored the basic workflow of using an LLM through an API. I configured the project to use an API key and used the Google GenAI Python package to communicate with the Gemini model.

The application follows these main steps:

1. Read the API configuration from the environment.
2. Create a connection to the Gemini model.
3. Send a text prompt to the model.
4. Receive the generated response.
5. Display the response in the terminal.

I kept the API key in an environment configuration file instead of writing it directly inside the Python source code. This makes it easier to manage credentials separately from the application logic.

## What I Learned

Through this activity, I learned the basic structure of an LLM API request and how a Python program can use a hosted generative AI model. I also understood why API keys should be kept private and why environment variables are useful for configuration.

## Conclusion

This activity introduced me to practical interaction with a generative AI model. It provided the foundation for the later activities, where I worked with multiple LLM providers, usage tracking, tokenization, and cost estimation.
