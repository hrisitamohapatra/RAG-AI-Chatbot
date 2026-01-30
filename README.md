# 📚 RAG PDF Chatbot with Gemini

A Retrieval-Augmented Generation (RAG) chatbot that allows you to upload PDF documents and ask questions about their content using Google's Gemini AI.

![Status](https://img.shields.io/badge/status-work%20in%20progress-yellow)
![Python](https://img.shields.io/badge/python-3.8+-blue)
![LangChain](https://img.shields.io/badge/langchain-%3C0.1.0-green)

## 🚀 Features

- **PDF Upload & Processing**: Upload any PDF document and extract its content
- **Intelligent Q&A**: Ask questions about your PDF and get accurate, context-aware answers
- **Modern UI**: Clean Gradio interface with chat history
- **Free Embeddings**: Uses HuggingFace sentence transformers (no API cost for embeddings)
- **Gemini 1.5 Flash**: Fast and efficient responses powered by Google's latest AI
- **Vector Search**: ChromaDB for semantic search through document chunks

## 🎯 Current Status

**⚠️ WORK IN PROGRESS ⚠️**

This project is actively being developed. While the core functionality works, there are known limitations and planned improvements.

### What Works ✅
- PDF upload and text extraction
- Document chunking and embedding
- Vector store creation with ChromaDB
- Question-answering with context retrieval
- Gradio web interface
- Custom prompt templates
- Chat history management

### Known Issues 🐛
- Large PDFs (>100 pages) may take time to process
- Vector store persists only in memory (lost on restart)
- No support for scanned PDFs (OCR needed)
- Limited to text-based PDFs only
- No multi-PDF support yet
- API key stored in session only (not persistent)

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- Google Colab account (recommended) OR local Python environment
- Google AI Studio API key ([Get one here](https://aistudio.google.com/app/apikey))

### Setup

1. **Clone or download this repository**
```bash
git clone <your-repo-url>
cd rag-pdf-chatbot
```

2. **Upload file to colab and run step by step**

## 📖 How to Use

1. **Get your API key**
   - Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
   - Create a new API key (starts with `AIza...`)
   - Keep it secure!

2. **Launch the app**
   - Run the Python script or Colab notebook
   - A Gradio interface will open

3. **Upload your PDF**
   - Enter your Google API key
   - Click "Upload PDF" and select your file
   - Click "🚀 Process PDF"

4. **Start chatting!**
   - Wait for the success message
   - Type your questions in the chat box
   - Get answers based on your PDF content

## 🏗️ Architecture

```
User uploads PDF
    ↓
PyPDFLoader extracts text
    ↓
RecursiveCharacterTextSplitter chunks the text
    ↓
HuggingFaceEmbeddings creates vector embeddings
    ↓
ChromaDB stores vectors for retrieval
    ↓
User asks question
    ↓
Retriever finds relevant chunks (k=3)
    ↓
Gemini 1.5 Flash generates answer using context
    ↓
Answer displayed in Gradio chat
```

## 🔮 Planned Features & Improvements

- [ ] **Persistent vector storage** - Save processed PDFs to disk
- [ ] **Multi-PDF support** - Upload and query multiple documents
- [ ] **Source citations** - Show which page/section the answer came from
- [ ] **Better error handling** - More descriptive error messages
- [ ] **API key persistence** - Save API key securely (with encryption)
- [ ] **Hybrid search** - Combine semantic + keyword search
- [ ] **Re-ranking** - Improve retrieval quality
- [ ] **Query expansion** - Generate related questions
- [ ] **Summarization mode** - Summarize entire documents
- [ ] **Fine-tuning** - Custom model for specific domains

## 🤝 Contributing

This is a work-in-progress project and contributions are welcome! Here's how you can help:

1. **Report bugs** - Open an issue with details
2. **Suggest features** - Share your ideas in Issues
3. **Submit PRs** - Fork, make changes, and submit a pull request
4. **Improve docs** - Help make the README better
5. **Test** - Try it with different PDFs and report issues


## 📝 Technical Details

### Dependencies
- **LangChain** (<0.1.0) - RAG framework
- **langchain-google-genai** (0.0.11) - Gemini integration
- **ChromaDB** - Vector database
- **Sentence Transformers** - Text embeddings
- **PyPDF** - PDF parsing
- **Gradio** - Web UI

### Model Configuration
- **Model**: Gemini 1.5 Flash
- **Temperature**: 0.7
- **Chunk Size**: 1000 characters
- **Chunk Overlap**: 200 characters
- **Top-K Retrieval**: 3 chunks
- **Embedding Model**: `sentence-transformers/all-MiniLM-L6-v2`

## ⚠️ Limitations

1. **Memory constraints** - Large PDFs may crash on limited RAM
2. **Text-only** - No support for images, charts, or scanned documents
3. **English-focused** - Best results with English documents
4. **Context window** - Limited by model's context length
5. **No authentication** - Anyone with the link can use the app
6. **Single session** - Data lost on page refresh

## 🔒 Security Notes

- Never share your API key publicly
- Don't commit API keys to version control
- Use environment variables for production
- Be cautious with sensitive PDFs in shared environments

---

**⭐ If you find this useful, please star the repository!**

**🐛 Found a bug? Open an issue!**

**💡 Have an idea? Start a discussion!**

---

*Last updated: January 2026*
*Version: 0.1.0-alpha*
