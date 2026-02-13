# Retrieval Augumented Generation

## Steps to run the project

### Option 1:

- Step 1: cd into backend directory: 
`cd backend`

- Step 2: run the python file app.py:
`python app.py`

- Step 3: Open a new terminal

- Step 4: cd into frontend:
`cd frontend`

- Step 5: run frontend: `npm start`

- Step 6: open localhost at
[http://localhost:3000](http://localhost:3000)

### Option 2:

- Step 1: Go to file `app.py` in backend directory.

- Step 2: Run the application

- Step 3: Open a new terminal

- Step 4: cd into frontend:
`cd frontend`

- Step 5: run frontend: `npm start`

- Step 6: open localhost at
[http://localhost:3000](http://localhost:3000)# GenFit

🏗️ Architecture

GenFit follows a modular Retrieval-Augmented Generation (RAG) architecture that separates user interaction, semantic retrieval, and LLM-based reasoning.
Each layer is independently scalable and communicates through REST-based services.

```mermaid
graph TB
    User["👤 User"]
    UI["🌐 Frontend (React/UI)"]
    API["🔐 Backend API (FastAPI/Flask)"]

    User -->|Submit Health Query| UI
    UI -->|POST Request| API

    API -->|Authenticate| Auth["🔑 Auth Layer (JWT/Session)"]
    Auth -->|Validated Request| Router["📡 Request Router"]

    Router -->|Generate Embedding| Embed["🧠 Embedding Model"]
    Embed -->|Vector Search| VectorDB["📚 Vector Database (FAISS)"]

    VectorDB -->|Top-K Results| Retriever["🔎 Retrieval Engine"]

    Retriever -->|Build Augmented Prompt| Prompt["📝 Prompt Builder"]
    Prompt -->|Send Context| LLM["🤖 LLM API (GPT/Claude)"]

    LLM -->|Generated Response| Validator["⚖️ Response Validator"]

    Validator -->|Safe Output| API
    API -->|Return Response| UI
    UI -->|Display Personalized Plan| User

    DataIngest["📥 Data Ingestion Pipeline"]
    DataIngest -->|Clean & Chunk| Embed
    DataIngest -->|Store Vectors| VectorDB

    API -->|Store History| DB["📦 PostgreSQL / User DB"]
    API -->|Log Events| Logs["📊 Monitoring & Logs"]

    style User fill:#e1f5ff
    style UI fill:#f3e5f5
    style API fill:#fff3e0
    style Auth fill:#fff3e0
    style Router fill:#e0f2f1
    style Embed fill:#e0f2f1
    style VectorDB fill:#f1f8e9
    style Retriever fill:#ede7f6
    style Prompt fill:#ede7f6
    style LLM fill:#fff9c4
    style Validator fill:#ffccbc
    style DataIngest fill:#fce4ec
    style DB fill:#e8f5e9
    style Logs fill:#f5f5f5
```




