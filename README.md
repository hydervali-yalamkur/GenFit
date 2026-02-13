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

graph TB
    User["👤 User"]
    UI["🌐 Frontend Interface"]
    API["🔐 Backend API (FastAPI/Flask)"]

    User -->|Ask Query| UI
    UI -->|Send Request| API

    API -->|Embed Query| Embed["🧠 Embedding Model"]
    Embed -->|Vector Search| VectorDB["📚 Vector Store (FAISS/DB)"]

    VectorDB -->|Relevant Context| RAG["🔎 Retrieval Layer"]
    RAG -->|Augmented Prompt| LLM["🤖 LLM API (GPT/Claude)"]

    LLM -->|Generated Response| API
    API -->|Return Answer| UI
    UI -->|Display Personalized Guidance| User

    DataIngest["📥 Data Ingestion Pipeline"]
    DataIngest -->|Clean & Chunk| VectorDB

    style User fill:#e1f5ff
    style UI fill:#f3e5f5
    style API fill:#fff3e0
    style Embed fill:#e0f2f1
    style VectorDB fill:#f1f8e9
    style RAG fill:#ede7f6
    style LLM fill:#fff9c4
    style DataIngest fill:#fce4ec






