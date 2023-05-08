
# File Question Answering Web Server

This project aims to build a web server that hosts the ChatGPT service to answer questions related to files uploaded to the server. The web server utilizes OpenAI's GPT-3.5 language model for generating answers and Pinecone for indexing and searching the uploaded files.

## Prerequisites

1. **Python**: Install Python with a version between 7 and 10. OpenAI has not yet tested GPT-3.5 on Python version 11 as of March 3, 2023. You can download Python version 10 from the [official Python website](https://www.python.org/downloads/).

2. **OpenAI API key**: Set up an OpenAI API key by following the instructions in the [OpenAI API documentation](https://platform.openai.com/docs/api-reference/introduction). Install the official Python bindings by running the following command:

3. **Pinecone API key and index setup**: Create a Pinecone account and index by visiting the [Pinecone website](https://www.pinecone.io/). Follow the instructions to create an index with the desired settings (e.g., index name, dimensions, metric, pod type). Retrieve your Pinecone API key from the account settings page.

4. **Google Colab trial run**: Validate your Pinecone account by running the [Google Colab notebook](https://colab.research.google.com/github/pinecone-io/examples/blob/master/integrations/openai/semantic_search_openai.ipynb). Enter your OpenAI and Pinecone API keys in the notebook as instructed. Run the notebook up to the second-to-last cell, without running the last cell that deletes the index.

5. **Node.js and npm**: Install Node.js and npm, which are required for the Next.js client. You can install them from the official [Node.js website](https://nodejs.org).

## Setup

1. Download the source code from the [OpenAI Cookbook GitHub repository](https://github.com/openai/openai-cookbook). Unzip the downloaded file, which contains the client and server directories.

2. Configure environment variables:
- In the server directory, create a `.env` file using a text editor.
- Add the following lines to the `.env` file, replacing `YOUR_OPENAI_API_KEY`, `YOUR_PINECONE_API_KEY`, and `Your_environment` with your actual API keys and Pinecone environment:
  ```
  OPENAI_API_KEY=YOUR_OPENAI_API_KEY
  PINECONE_API_KEY=YOUR_PINECONE_API_KEY
  PINECONE_ENV=Your_environment
  ```

3. Server setup:
- In the server directory, run the following commands in a PowerShell window:
  ```
  pip install openai
  npm install openai
  python -m venv venv
  .\venv\Scripts\activate
  pip install -r .\requirements.txt
  python .\app.py
  ```
- You should see the Flask server running on `http://127.0.0.1:8080`.

4. Client setup:
- Open a new PowerShell window and change directory to the client directory.
- Run the following commands to install Node dependencies:
  ```
  pip install openai
  npm install openai
  ```
- Run the Next.js client:
  ```
  npm run dev
  ```
- The client should start running on `http://localhost:3000`.

## Usage

1. Open `http://localhost:3000` in your browser to access the web application
