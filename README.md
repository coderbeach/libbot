# 🎓 LibBot – University Open Access Research Assistant

An AI-powered academic resource discovery chatbot that helps students and researchers find relevant open-access databases through natural-language queries.

LibBot combines **Retrieval-Augmented Generation (RAG), semantic search, vector similarity retrieval, and a Large Language Model (LLM)** to provide context-based answers from a structured collection of academic resources.

---

## 🚀 Project Overview

Finding relevant academic databases and research resources can be time-consuming. LibBot aims to simplify this process by allowing users to ask questions in natural language and receive relevant resource recommendations.

The system currently works with 20 open-access resource records extracted from the Presidency University Open Access Databases webpage.

Instead of relying only on keyword matching, LibBot uses semantic embeddings and FAISS similarity search to retrieve relevant resources before generating an answer using Qwen.

## ✨ Features

- **Web Data Extraction:** Extracts open-access resource information from a university webpage.
- **Structured Dataset:** Organizes resources into a structured dataset using Pandas.
- **Semantic Search:** Understands the meaning of user queries using sentence embeddings.
- **Vector Similarity Search:** Uses FAISS to retrieve the most relevant records.
- **RAG Pipeline:** Combines retrieved context with an LLM to generate answers.
- **LLM Integration:** Uses Qwen 2.5 3B Instruct for natural-language response generation.
- **Interactive Chatbot:** Provides a conversational interface using Gradio.
- **Context-Grounded Responses:** Instructs the model to answer using retrieved records and avoid inventing database information.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core development |
| Requests | Webpage extraction |
| Pandas | Dataset processing |
| Sentence Transformers | Text embeddings |
| all-MiniLM-L6-v2 | Embedding model |
| FAISS | Vector similarity search |
| Qwen 2.5 3B Instruct | Response generation |
| Hugging Face Transformers | LLM integration |
| BitsAndBytes | 4-bit model quantization |
| Gradio | Chatbot interface |
| Google Colab | Development environment |

## 🏗️ System Architecture

```text
Presidency University Open Access Webpage
                  |
                  v
          Web Data Extraction
                  |
                  v
           Structured Dataset
             (20 Records)
                  |
                  v
       Sentence Transformer Model
                  |
                  v
           Text Embeddings
                  |
                  v
             FAISS Index
                  |
                  |
          User Query
                  |
                  v
        Query Embedding
                  |
                  v
       Semantic Retrieval
                  |
                  v
        Relevant Context
                  |
                  v
          Qwen 2.5 3B
                  |
                  v
        Generated Response
                  |
                  v
          Gradio Chatbot
```

## 📚 Dataset Information

The initial dataset is extracted from the Presidency University Open Access Databases webpage.

**Source:** [Presidency University – Open Access Databases](http://182.72.188.195/opac-tmpl/bootstrap/images/OADATABASE/OA%20Databases.html)

The dataset currently contains **20 resource records** with the following fields:

- `title` – Name of the resource.
- `url` – Website link.
- `category` – Resource category.
- `description` – Brief description.
- `icon` – Associated icon identifier.

The records cover categories such as:

- Law & Judiciary
- Economics & Finance
- Statistics & Data
- Academic Research
- Journals & Books
- Preprints & Archives
- University Resources

## 🧠 How RAG Works in LibBot

LibBot follows a Retrieval-Augmented Generation workflow:

1. **User Query:** The user enters a natural-language question.
2. **Embedding Generation:** The query is converted into a numerical vector using `all-MiniLM-L6-v2`.
3. **Semantic Retrieval:** FAISS searches the vector index for the most relevant records.
4. **Context Preparation:** The retrieved records are combined into a context.
5. **Response Generation:** Qwen receives the question and retrieved context.
6. **Chatbot Output:** Gradio displays the generated response.

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/coderbeach/libbot.git
cd libbot
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the project

The main development notebook is:

```text
libbot.ipynb
```

Open it in Google Colab or Jupyter Notebook and execute the cells in sequence.

**Note:** The Qwen model download requires an internet connection the first time. A compatible GPU is recommended for efficient model inference.

## 💬 Example Queries

Users can ask questions such as:

- Where can I find Indian legal judgments?
- Suggest databases for economic research.
- Where can I find open-access journals?
- Which databases provide Indian government statistics?
- Where can I find PhD theses?
- Which databases provide engineering research?

## 📸 Screenshots

Screenshots of the chatbot, semantic search results, and system workflow will be added here.

<!-- Add screenshots from your screenshots folder here -->

## ⚠️ Current Limitations

- The current knowledge base contains 20 resource records.
- The chatbot retrieves resource descriptions and links, not the complete contents of all linked websites or research papers.
- Some external databases may require authentication, subscriptions, or API access.
- Answer quality depends on the relevance and completeness of the available dataset.

## 🔮 Future Enhancements

- Integration with public academic research APIs.
- Automated retrieval of publicly available research papers.
- PDF extraction and document-level question answering.
- Multi-document research summarization.
- Literature review generation.
- Research gap identification.
- Source-linked answers and academic citations.
- Expansion of the knowledge base with additional open-access repositories.

## 👩‍💻 Author

**Nisarga N.**

GitHub: [@coderbeach](https://github.com/coderbeach)

---

⭐ If you find this project interesting, consider giving the repository a star!

**LibBot – Making academic resource discovery smarter with AI.**
