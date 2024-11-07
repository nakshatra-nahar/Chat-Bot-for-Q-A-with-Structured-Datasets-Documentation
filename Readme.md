# Chat Bot for Q&A with Structured Datasets Documentation

## Overview
This documentation describes the architecture and workflow for an intermediate-level chat bot designed to interact with structured datasets. The chat bot can take user prompts and respond with data-driven answers by converting queries into SQL, executing them against a database, and returning results in natural language. It leverages Gradio for the user interface and advanced LLMs like OpenAI and Anthropic for processing.

## Components
1. **Gradio**: A web-based framework for creating an interactive user interface. It is used to collect user prompts and display responses.

2. **User Prompt**: The input provided by the user, typically a natural language question or query that needs to be translated into an actionable request.

3. **System Prompt**: A specialized instruction given to the LLM to convert the user prompt into an SQL query. It may include schema details and context for accurate query generation.

4. **SQL Schema Injection**: The process of incorporating the relevant SQL schema into the system prompt to guide the LLM in generating a correct and efficient SQL query.

5. **Large Language Model (LLM)**: 
   - **OpenAI/Anthropic**: These are advanced LLMs that process the prompts and generate corresponding SQL queries. They are also used to interpret and format the results retrieved from the database.

6. **Databases**: The structured datasets are hosted in databases such as:
   - **MariaDB**
   - **MySQL**
   
7. **Gemini**: A component or service used to manage chat history or improve the bot’s understanding of context over multiple interactions.

8. **Chat History**: The ability to include previous conversations to provide continuity in responses and maintain an understanding of context.

## Workflow
1. **User Input**: 
   - The user provides a prompt via the Gradio interface, asking a question related to the structured dataset.
   
2. **System Prompt Conversion**: 
   - The system prompt is created, incorporating the user input and SQL schema details. This is essential for accurately converting the prompt into an SQL query.
   
3. **LLM Processing**: 
   - The combined prompt is sent to an LLM (OpenAI/Anthropic), which generates a valid SQL query based on the input.
   
4. **Query Execution**: 
   - The generated SQL query is run against the connected database (e.g., MariaDB or MySQL).
   - The database returns the requested records or results.
   
5. **Result Interpretation**: 
   - The LLM takes the raw data retrieved from the database and translates it into a human-readable format or a structured answer for the user.
   
6. **Response Display**: 
   - The final response is displayed to the user in the Gradio interface.
   - The bot also stores relevant results and updates the chat history to improve future interactions.

## Future Enhancements
- **Improved Query Optimization**: Enhance the LLM’s ability to generate optimized SQL queries.
- **Database Scalability**: Support additional database types (e.g., PostgreSQL, SQLite) for more flexibility.
- **Enhanced Context Awareness**: Refine the use of chat history to provide even more accurate and context-aware responses.
- **Schema Updates**: Implement mechanisms to automatically update and inject new schema details as the database evolves.
