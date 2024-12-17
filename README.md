# SQL Data Exploration with Langchain and RAG

This project involves two main parts:
1. **Database Creation and Word Clouds (with TF-IDF)**: The first notebook (`sql-data-exploration-database-creation.ipynb`) generates an SQLite database and creates word clouds.
2. **RAG SQL Langchain Chatbot**: The second notebook (`rags-sql-langchain-chat-bot.ipynb`) leverages the database and Langchain to create an interactive chatbot for SQL-based queries.

## Overview

The system uses **Langchain** for structured query generation, **RAG** (Retrieval-Augmented Generation) to retrieve relevant documents from the database, and **OpenAI's GPT** to generate responses based on SQL query results. The two notebooks must be run in order to set up and utilize the database and chatbot functionality.

---

## Prerequisites

1. **Python 3.x** (Recommended: Python 3.7+)
2. **Install required Python packages**: You'll need to install the necessary dependencies from the `requirements.txt` file.

To install the required packages, use the following command:

```bash
pip install -r requirements.txt bash
```
3. OpenAI API Key: You'll need to set up your OpenAI API key to interact with GPT models. You can get your API key from OpenAI's API platform.

Create a .env file in the root of the project and add your OpenAI API key as follows:

```bash
OPENAI_API_KEY=your_openai_api_key
```

4. SQLite Database: The first notebook creates the SQLite database (main.db) that will be used in the second notebook. This file must exist before running the chatbot notebook.

# Steps

### Step 1: Run the Database Creation Notebook

The first notebook, `sql-data-exploration-database-creation.ipynb`, generates the SQLite database (`main.db`) and creates word clouds for visual exploration.

**To run the database creation notebook:**

1. Open Jupyter Notebook or JupyterLab.
2. Open the `sql-data-exploration-database-creation.ipynb` notebook.
3. Run the cells sequentially to:
   - Create the SQLite database (`main.db`).
   - Populate the database with your data (you can modify the notebook to customize the data source).
   - Generate word clouds based on the content of the database to visualize the data.

Once the notebook finishes, the `main.db` database and word clouds will be ready.

---

### Step 2: Run the RAG SQL Langchain Chatbot Notebook

Once the database is created, the second notebook, `rags-sql-langchain-chat-bot.ipynb`, leverages Langchain to build a chatbot capable of interacting with the SQLite database using natural language queries.

**To run the chatbot notebook:**

1. Open Jupyter Notebook or JupyterLab.
2. Open the `rags-sql-langchain-chat-bot.ipynb` notebook.
3. Run the cells sequentially to:
   - Use Langchain to generate SQL queries based on user input.
   - Execute the generated SQL queries on the `main.db` database.
   - Use OpenAI's GPT to generate human-readable answers based on the query results.
   - Present the results interactively, powered by Langchain and RAG.

---

# Example Usage

Once the chatbot is running, you can interact with it via the notebook interface. Example interactions:

- **User**: "How many customers purchased product X last month?"
  
  **Response**: The chatbot will generate an SQL query, execute it on the `main.db`, and return a response like: "Product X was purchased by 150 customers last month."

- **User**: "Show me the top 5 products sold in the last quarter."
  
  **Response**: The chatbot will execute a query to fetch the top 5 products from the database and display them.

---

# Future Improvements

- **Support for Additional Databases**: Enhance the tool to support other databases like MySQL, PostgreSQL, etc.
- **Error Handling**: Improve error handling for invalid SQL queries or database issues.
- **User Interface**: Consider adding a web interface with Gradio or a more interactive UI for ease of use.

