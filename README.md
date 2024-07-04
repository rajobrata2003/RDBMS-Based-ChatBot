# SQL Query Generator with Gradio Interface

This repository contains a Gradio-based application that allows users to generate and execute SQL queries on the Chinook database. The application uses LangChain, OpenAI, and other libraries to expand user prompts, generate SQL queries, and provide natural language responses based on the query results.

## Features

- **User Prompt Expansion**: Expands user prompts to make them more SQL-friendly.
- **SQL Query Generation**: Generates SQL queries based on the expanded prompts and the database schema.
- **Query Execution**: Executes the generated SQL queries on the Chinook database.
- **Natural Language Response**: Provides a natural language summary of the query results.
- **Gradio Interface**: User-friendly interface to interact with the application.

## Setup

### Prerequisites

- Python 3.7+
- MySQL database with the Chinook schema
- An OpenAI API key
- A .env file containing your OpenAI API key

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/sql-query-generator.git
    cd sql-query-generator
    ```

2. Create and activate a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the root directory and add your OpenAI API key:
    ```env
    OPENAI_API_KEY=your_openai_api_key
    ```

5. Update the `mysql_uri` variable in the code to match your MySQL database credentials:
    ```python
    mysql_uri = 'mysql+mysqlconnector://username:password@localhost:3306/chinook'
    ```

## Usage

1. Run the Gradio application:
    ```bash
    python app.py
    ```

2. Open the application in your web browser. You should see the Gradio interface.

3. Enter your question in the input field and click the "Submit" button to generate and execute the SQL query.

## Code Overview

### Main Functions

- `get_schema(_)`: Retrieves the database schema information.
- `expand_prompt(user_question)`: Expands the user question to make it more SQL-friendly.
- `run_query(query)`: Executes the SQL query and returns the results.
- `generate_response(user_question)`: Expands the user question, generates the SQL query, executes it, and generates the final response.
- `gradio_interface(user_question)`: Handles the user input and retries if necessary to generate the response.

### Gradio Setup

The Gradio interface is defined to take user input, process it using the main functions, and display the expanded prompt, natural language response, and query results in a DataFrame.

## Contributing

Contributions are welcome! If you have any ideas, suggestions, or bug reports, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License.

## Acknowledgments

- [Gradio](https://gradio.app/)
- [LangChain](https://langchain.com/)
- [OpenAI](https://openai.com/)
- [Pandas](https://pandas.pydata.org/)
