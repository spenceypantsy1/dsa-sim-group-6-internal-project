# SQL Data Exploration with Langchain and RAG 💬

This project involves three main parts:
1. **Database creation and EDA**: The first notebook(`eda-data-exploration.ipynb`) cleans the dataset and combines. both authors.csv & papers.csv into a single table. Exploratory Data Analysis is done here to understand the dataset better.
2. **NLP hot topics generation**: The second notebook (`nlp-hot-topics-generation.ipynb`) creates word clouds and finds hot topics for each year with TF-IDF NLP to upload into the SQLite database.
3. **RAG SQL Langchain Chatbot**: The third notebook (`rags-sql-langchain-chat-bot.ipynb`) leverages the database and Langchain to create an interactive chatbot for SQL-based queries.

The dataset used comes from https://www.kaggle.com/datasets/rowhitswami/nips-papers-1987-2019-updated/data

## Overview

This was a group effort as part of our SIM Data Analytics Club - Data Science Academy internal projects.

The system uses **Langchain** for structured query generation, **RAG** (Retrieval-Augmented Generation) to retrieve relevant documents from the database, and **OpenAI's GPT** to generate responses based on SQL query results. The two notebooks must be run in order to set up and utilize the database and chatbot functionality.

---

## Prerequisites

1. **Python 3.x** (Recommended: Python 3.7+ 🐍)
2. **Install required Python packages**: You'll need to install the necessary dependencies from the `requirements.txt` file.

To install the required packages, use the following command:

```bash
pip install -r requirements.txt bash
```
3. OpenAI API Key: You'll need to set up your OpenAI API key to interact with GPT models. You can get your API key from OpenAI's API platform 🌐.

Create a .env file in the root of the project and add your OpenAI API key as follows:

```bash
OPENAI_API_KEY=your_openai_api_key
```

4. SQLite Database: The first notebook creates the SQLite database (main.db) that will be used in the second notebook. This file must exist before running the chatbot notebook 🗃️.

# Steps

### Step 1: Run the Database Creation ane EDA Notebook

The first notebook, `eda-data-exploration.ipynb`, generates the SQLite database (`main.db`) and gives us an understanding on the intricacies of the data.

**To run the database creation notebook:**

1. Open Jupyter Notebook or JupyterLab 🖥️.
2. Open the `eda-data-exploration.ipynb` notebook.
3. Run the cells sequentially to:
   - Create the SQLite database (`main.db`) 🗃️.
   - Clean the data, removing NA fields and combining both data files into a single table.
   - Plot the emerging trends in NIPS research papers.

Once the notebook finishes, the `main.db` database and word clouds will be ready 🎉.

---

### Step 2: Run the Database Creation Notebook

The second notebook, `sql-data-exploration-database-creation.ipynb`, engaging NLP techniques like TF-IDF to hot-topic trends and updates our SQLite database.

**To run the database creation notebook:**

1. Open Jupyter Notebook or JupyterLab 🖥️.
2. Open the `sql-data-exploration-database-creation.ipynb` notebook.
3. Run the cells sequentially to:
   - Populate the database with your data (you can modify the notebook to customize the data source).
   - Generate word clouds based on the content of the database to visualize the data.

---

### Step 3: Run the RAG SQL Langchain Chatbot Notebook

Once the database is created, the second notebook, `rags-sql-langchain-chat-bot.ipynb`, leverages Langchain to build a chatbot capable of interacting with the SQLite database using natural language queries 💬.

**To run the chatbot notebook:**

1. Open Jupyter Notebook or JupyterLab 🖥️.
2. Open the `rags-sql-langchain-chat-bot.ipynb` notebook.
3. Run the cells sequentially to:
   - Use Langchain to generate SQL queries based on user input 📝.
   - Execute the generated SQL queries on the `main.db` database 🗃️.
   - Use OpenAI's GPT to generate human-readable answers based on the query results 💬.
   - Present the results interactively, powered by Langchain and RAG 🔄.

---

# Example Usage

Once the chatbot is running, you can interact with it via the notebook interface. Example interactions:

- **User**: "How many customers purchased product X last month?"
  
  **Response**: The chatbot will generate an SQL query, execute it on the `main.db`, and return a response like: "Product X was purchased by 150 customers last month."

- **User**: "Show me the top 5 products sold in the last quarter."
  
  **Response**: The chatbot will execute a query to fetch the top 5 products from the database and display them.

---

# Future Improvements 🛠️

- **Support for Additional Databases**: Enhance the tool to support other databases like MySQL, PostgreSQL, etc.
- **Error Handling**: Improve error handling for invalid SQL queries or database issues.
- **User Interface**: Consider adding a web interface with Gradio or a more interactive UI for ease of use.

