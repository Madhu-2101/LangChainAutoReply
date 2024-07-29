# LangChainAutoReply

LangChainAutoReply is an automatic email reply system designed to categorize and respond to various types of emails related to film equipment rentals. Using advanced LangChain integrations and a Retrieval-Augmented Generation (RAG) pipeline, the system processes incoming emails, classifies them, retrieves relevant information, and generates appropriate responses. 

## Features

- **Email Categorization:** Classify emails into categories such as product inquiries, reviews, and assistance requests.
- **Product Information Retrieval:** Access a SQLite database to check product availability and suggest similar items.
- **Dynamic Email Responses:** Generate personalized email responses based on categorized emails and retrieved product information.
- **RAG Pipeline Integration:** Utilize LangChain for a robust Retrieval-Augmented Generation pipeline.

## Requirements

### Libraries

- `langchain`
- `langchain-groq`
- `duckduckgo-search`
- `langchain_community`
- `tiktoken`
- `faiss-cpu`
- `ipywidgets`
- `langchain_google_genai`
- `sqlite3`

You can install the required libraries using the following commands:

```bash
!pip install langchain
!pip install langchain-groq duckduckgo-search
!pip install -U langchain_community tiktoken langchainhub
!pip install -U langchain langgraph tavily-python
!pip install faiss-cpu
!pip install ipywidgets
!pip install langchain_google_genai
```

## Setup

### Database Schema and Implementation

1. **Database Schema:**
   The project uses a SQLite database to manage film equipment details. The schema includes the following table:

   ```sql
   CREATE TABLE Equipments (
       id INTEGER PRIMARY KEY AUTOINCREMENT,
       name TEXT NOT NULL,
       category TEXT NOT NULL,
       availability TEXT NOT NULL,
       price REAL
   )
   ```

2. **Database Setup:**
   Use the `setup_equipment_table()` function to create the database and insert sample data.

### RAG Pipeline Document

1. **Email Categorization:** Uses the LangChain `ChatGroq` model to categorize incoming emails.
2. **Product Name Extraction:** Extracts product names from emails for database queries.
3. **Product Information Retrieval:** Fetches product availability and similar items if necessary.
4. **Response Generation:** Generates email replies based on product information or review handling.

### Flowchart

The flowchart outlines the email processing logic:
1. **Receive Email**
2. **Categorize Email**
3. **Extract Product Name (if applicable)**
4. **Retrieve Product Information**
5. **Generate Response**
6. **Send Response**

## Source Code

The complete source code for the LangChainAutoReply project is available on [GitHub](https://github.com/Madhu-2101/LangChainAutoReply).

## Usage

1. **Run the Project:**
   - Execute the script in a Python environment that supports `ipywidgets` and `langchain`.

2. **Interact with the System:**
   - Input email content into the provided text area.
   - Click "Get Response" to process the email and receive a generated reply.
