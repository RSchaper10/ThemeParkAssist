
# ParkPassQ&A

This notebook builds a question-answering (Q&A) pipeline that leverages web scraping, vector-based document retrieval, and LLMs to provide relevant answers to user queries, particularly in the context of amusement parks, such as Disney. The example used leverages Llama3 for local LLM functions.

## Setup Instructions

1. **Environment Setup**:
   - Install the required dependencies listed in `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

2. **Selenium Chrome Setup**:
   - You will need to have the Chrome browser installed and the appropriate ChromeDriver for your operating system. The notebook includes functionality to automate browsing using Selenium, enabling data retrieval from web pages.

3. **Chroma and Pinecone Configuration**:
   - Set up your Pinecone and Chroma vector databases to handle document embeddings and retrieval efficiently.

4. **OpenAI API Key**:
   - Ensure you have an API key from OpenAI to enable text generation capabilities for answering user queries.

## Notebook Workflow

1. **Browser Initialization**:
   - The `init_chrome_browser()` function sets up a Chrome browser with Selenium to interact with web pages for scraping content.

2. **Data Retrieval and Processing**:
   - The notebook integrates web scraping tools such as BeautifulSoup and Selenium to extract relevant information from websites based on user queries.

3. **Vector Search and Document Grading**:
   - Retrieved content is evaluated and graded for relevance using vector embeddings (via Chroma or Pinecone). The workflow automatically decides if the retrieved documents are useful for answering the query.

4. **Answer Generation**:
   - The notebook uses LangChain and OpenAI to generate answers based on the retrieved documents, simulating a question-answering system. The response is graded for accuracy before being returned.

5. **Testing the Workflow**:
   - A sample query about Disney's Genie Passes is included to test the workflow's functionality.

## Dependencies

- **Web Scraping**: `selenium`, `beautifulsoup4`, `requests`, `selenium-screenshot`
- **Data Processing**: `pandas`, `numpy`, `scipy`
- **Database**: `sqlalchemy`, `chromadb`, `pinecone-client`
- **LLM and Embeddings**: `openai`, `langchain`, `sentence-transformers`
- **Workflow and Graph**: `langgraph`, `langchain-community`

