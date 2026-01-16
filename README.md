Below is a **clean, properly formatted, GitHub-ready `README.md`** for **Jurix**.
You can **copy–paste this directly** into `README.md` and push — it will render perfectly.

---

```md
# Jurix — Legal Document RAG System ⚖️

Jurix is a comprehensive **AI-powered legal assistant** that enables natural language querying over Indian legal documents and case law using a **Retrieval-Augmented Generation (RAG)** architecture with vector embeddings.

The system democratizes access to complex Indian law by combining authoritative legal sources with modern AI techniques.

---

## ✨ Key Features

- 🧠 **RAG Architecture** for accurate, source-backed answers  
- 📚 **Dual Data Sources**: Statutory law + judicial case law  
- 🔀 **Smart Query Routing** to decide which databases to search  
- 🔍 **Semantic Vector Search** using embeddings  
- ⚡ **Production-ready FastAPI backend** with async support  
- 💬 **Modern React 19 chat UI**  
- 🤖 **Automated case-law ingestion** via scrapers  
- 📈 **Scalable architecture** supporting concurrent users  

---

## 🚀 FastAPI Endpoints

### Base URL
```

[http://localhost:8000](http://localhost:8000)

````

---

### 📝 1. Query Legal Assistant

**POST** `/api/query`

Query the legal assistant using natural language. Supports both legal documents and case law.

**Request Body**
```json
{
  "query": "What is Article 21?",
  "debug": false
}
````

**Response**

```json
{
  "answer": "Article 21 of the Constitution states...",
  "query_plan": {
    "legal_docs": ["Article 21"],
    "cases": []
  },
  "debug_info": {
    "legal_docs_queries": 1,
    "cases_queries": 0
  }
}
```

**Parameters**

* `query` (string, required): User's legal question
* `debug` (boolean, optional): Enable query analysis output

---

### 📤 2. Upload Document

**POST** `/api/documents/upload`

Upload PDF documents for ingestion into the legal database.

**Request**

* `multipart/form-data`

  * `file`: PDF document
  * `title`: Document title

**Example**

```bash
curl -X POST http://localhost:8000/api/documents/upload \
  -F "file=@constitution.pdf" \
  -F "title=Constitution of India"
```

**Response**

```json
{
  "success": true,
  "filename": "constitution.pdf",
  "title": "Constitution of India",
  "message": "Document processed successfully"
}
```

---

### 🔍 3. Analyze Query

**POST** `/api/query/analyze`

Analyze which databases will be searched without executing the query.

**Request**

```json
{
  "query": "What does Article 21 say and show related case law"
}
```

**Response**

```json
{
  "will_search_legal_docs": true,
  "will_search_cases": true,
  "legal_docs_queries": ["Article 21"],
  "cases_queries": ["Article 21 case law"]
}
```

---

### ❤️ 4. Health Check

**GET** `/health`

```json
{
  "status": "healthy",
  "database_connected": true
}
```

---

### 📊 5. Statistics

**GET** `/api/stats`

```json
{
  "documents_processed": 15,
  "total_queries": 342
}
```

---

### 🗄️ 6. Test Database Connection

**GET** `/api/database/test`

```json
{
  "connected": true,
  "message": "Database connection successful"
}
```

---

### 🏠 7. Root Endpoint

**GET** `/`

Returns API metadata and available endpoints.

---

## 🛠️ Running the API

### Installation

```bash
pip install -r requirements.txt
```

### Start Server

```bash
python main.py
```

Or using Uvicorn:

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

---

## 📖 API Documentation

* **Swagger UI**: [http://localhost:8000/docs](http://localhost:8000/docs)
* **ReDoc**: [http://localhost:8000/redoc](http://localhost:8000/redoc)
* **OpenAPI Schema**: [http://localhost:8000/openapi.json](http://localhost:8000/openapi.json)

---

## 🧪 API Usage Examples

### Simple Query

```bash
curl -X POST http://localhost:8000/api/query \
  -H "Content-Type: application/json" \
  -d '{"query":"What is Section 420 IPC?"}'
```

### Debug Mode

```bash
curl -X POST http://localhost:8000/api/query \
  -H "Content-Type: application/json" \
  -d '{"query":"Show case law on property disputes","debug":true}'
```

---

## 🔧 Error Handling

Standard HTTP status codes:

* `200 OK`
* `400 Bad Request`
* `500 Internal Server Error`

**Error Response Format**

```json
{
  "detail": "Error message describing what went wrong"
}
```

---

## 🌐 CORS Configuration

CORS is enabled for all origins by default.

For production, update in `main.py`:

```python
app.add_middleware(
    CORSMiddleware,
    allow_origins=["https://yourdomain.com"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

## 📦 Tech Stack & Dependencies

* FastAPI
* Uvicorn
* LangChain
* Vector Databases
* Google Gemini API
* Python Multipart
* dotenv

---

## 📜 License

MIT License © 2026 — Jurix

```

---

### ✅ What this fixes
- Proper **Markdown spacing**
- Correct **code fences**
- Clean **headings & sections**
- Recruiter-friendly structure
- GitHub renders it perfectly

If you want next:
- 🔹 **Shorter README (recruiter version)**
- 🔹 **Architecture diagram using Mermaid**
- 🔹 **Badges (build, license, tech stack)**
- 🔹 **Frontend README + screenshots**

Just tell me.
```
