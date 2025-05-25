# 🧠 Semantic Search with ChromaDB and OpenAI

This project is a lightweight, local semantic search engine built with [ChromaDB](https://www.trychroma.com/) and [OpenAI Embeddings](https://platform.openai.com/docs/guides/embeddings). It allows you to:

* Load and chunk `.txt` documents
* Generate embeddings using OpenAI's `text-embedding-3-small`
* Store and query embeddings via ChromaDB (persisted locally)
* Answer natural language questions based on document content using GPT-3.5-Turbo



## 🔧 Features

* ✅ Document loader from a local directory
* ✅ Text chunking for long documents
* ✅ Embedding generation with OpenAI API
* ✅ Persistent ChromaDB collection
* ✅ Natural language question answering using a context-aware prompt


## 📁 Project Structure

```
.
├── news_articles/           # Folder for .txt documents to index
├── chroma_persistent_storage/  # Auto-generated persistent ChromaDB storage
├── main.py                  # Main script
├── .env                     # Environment file for OpenAI API key
```


## ⚙️ Setup Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Install dependencies:**

   ```bash
   pip install openai chromadb python-dotenv
   ```

3. **Add your OpenAI API Key:**

   Create a `.env` file with:

   ```
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Add documents:**

   Place your `.txt` files into the `news_articles/` directory.

5. **Run the project:**

   ```bash
   python main.py
   ```


## ❓ Example Query

```python
question = "How much money OnlyFans is being sold for?"
```

Output:

```
Answer: OnlyFans is being sold for approximately $2 billion.
```

(*Depends on document context*)


## 🧠 How It Works

1. Documents are loaded and split into overlapping chunks.
2. Each chunk is embedded using OpenAI's embedding model.
3. Embeddings and texts are stored in ChromaDB locally.
4. When a query is made, ChromaDB retrieves semantically similar chunks.
5. GPT-3.5-Turbo generates a concise answer using the retrieved context.


## 📝 Notes

* ChromaDB uses persistent storage under `chroma_persistent_storage/`.
* OpenAI embedding and chat endpoints require API keys with sufficient quota.
* This is a basic implementation; retrieval quality and QA accuracy can be improved with better chunking, reranking, or prompt engineering.


## 📄 License

MIT License.
Feel free to use, modify, and distribute.
