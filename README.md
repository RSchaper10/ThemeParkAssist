
# ThemeParkAssist

This notebook builds a question-answering (Q&A) pipeline that leverages web scraping, vector-based document retrieval, and LLMs to provide relevant answers to user queries, particularly in the context of amusement parks, such as Disney. The example used leverages Llama3 for local LLM functions.

## Setup Instructions

1. **Environment Setup**:
   - Install the required dependencies listed in `requirements.txt`:
     ```bash
     pip install -r requirements.txt
     ```

2. **Selenium Chrome Setup**:
   - You will need to have the Chrome browser installed and the appropriate ChromeDriver for your operating system. The notebook includes functionality to automate browsing using Selenium, enabling data retrieval from web pages.

3. **Chroma DB Configuration**:
   - Set up Chroma vector databases to handle document embeddings and retrieval efficiently. 


## Notebook Workflow

1. **Browser Initialization**:
   - The `init_chrome_browser()` function sets up a Chrome browser with Selenium to interact with web pages for scraping content.

2. **Data Retrieval and Processing**:
   - The notebook integrates web scraping tools such as BeautifulSoup and Selenium to extract relevant information from websites based on user queries.

3. **Vector Search and Document Grading**:
   - Retrieved content is evaluated and graded for relevance using vector embeddings (via Chroma or Pinecone). The workflow automatically decides if the retrieved documents are useful for answering the query.

4. **Answer Generation**:
   - The notebook uses LangGraph and Llama3 to generate answers based on the retrieved documents, simulating a question-answering system with self-reflection and hallucination detection steps to fully grade for accuracy before returning the response.

5. **Testing the Workflow**:
   - The Q&A process is only one stage of a journey for theme park visitors -- with tools and access to other data sources, a more complete journey orchestration process can be created.

## Dependencies

- **Web Scraping**: `selenium`, `beautifulsoup4`, `requests`, `selenium-screenshot`
- **Database**:  `chromadb`
- **LLM and Embeddings**: `llama3`, `langchain`, `sentence-transformers`,`langchain-huggingface`
- **Workflow and Graph**: `langgraph`, `langchain-community`

