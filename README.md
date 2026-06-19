# YouTube Video Summarizer - Basic RAG System

A Python-based application that automatically summarizes YouTube videos using Retrieval-Augmented Generation (RAG) techniques.

## 📋 Overview

This project leverages modern NLP and RAG (Retrieval-Augmented Generation) methods to:
- Extract transcripts from YouTube videos
- Process and chunk video content
- Generate accurate and concise summaries
- Provide question-answering capabilities based on video content

## ✨ Features

- **Automatic Transcript Extraction**: Retrieve transcripts from YouTube videos
- **RAG-Based Processing**: Utilize retrieval-augmented generation for improved summarization
- **Content Chunking**: Intelligent splitting of content for better context understanding
- **Question Answering**: Ask questions about video content and get relevant answers
- **Easy Integration**: Simple interface for processing multiple videos

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- YouTube video URLs
- Required API keys (LLM provider, YouTube API)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Swizknife/YOUTUBE_VDO_SUMMARIZER_BASIC-RAG-BASED-SYSTEM.git
cd YOUTUBE_VDO_SUMMARIZER_BASIC-RAG-BASED-SYSTEM
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
```bash
cp .env.example .env
# Edit .env with your API keys
```

## 💻 Usage

### Basic Example

```python
from youtube_summarizer import YouTubeSummarizer

# Initialize the summarizer
summarizer = YouTubeSummarizer()

# Summarize a YouTube video
video_url = "https://www.youtube.com/watch?v=your_video_id"
summary = summarizer.summarize(video_url)
print(summary)
```

### Advanced Usage

```python
# Ask questions about video content
answer = summarizer.ask(video_url, "What are the main topics discussed?")
print(answer)

# Get detailed analysis
analysis = summarizer.analyze(video_url)
print(analysis)
```

## 🏗️ Architecture

The system is built with the following components:

- **Transcript Extraction**: Uses YouTube's transcript API
- **Text Processing**: Breaks content into manageable chunks
- **Embedding Generation**: Creates vector embeddings for semantic search
- **RAG Pipeline**: Retrieves relevant context and generates summaries
- **LLM Integration**: Uses language models for intelligent summarization

## 📦 Project Structure

```
├── README.md
├── requirements.txt
├── .env.example
├── main.py
├── youtube_summarizer/
│   ├── __init__.py
│   ├── extractor.py
│   ├── processor.py
│   ├── rag_engine.py
│   └── summarizer.py
├── config/
│   └── settings.py
├── utils/
│   ├── helpers.py
│   └── validators.py
└── tests/
    └── test_summarizer.py
```

## 🔧 Configuration

Edit `.env` file to configure:

```env
# YouTube API
YOUTUBE_API_KEY=your_youtube_api_key

# LLM Provider (OpenAI, HuggingFace, etc.)
LLM_PROVIDER=openai
LLM_API_KEY=your_llm_api_key

# Vector Database
VECTOR_DB_TYPE=chroma
EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2

# RAG Settings
CHUNK_SIZE=500
CHUNK_OVERLAP=100
```

## 🤖 Models Used

- **LLM**: GPT-3.5-Turbo / GPT-4 (configurable)
- **Embeddings**: Sentence Transformers
- **Vector Store**: Chroma/FAISS
- **Transcript**: YouTube's built-in captions

## 📊 Output Examples

### Summary Output
```
Video Title: [Title]
Duration: [Duration]
Summary: [Generated summary]
Key Topics: [List of main topics]
```

### Q&A Output
```
Question: What are the main points?
Answer: [Relevant answer based on video content]
Confidence: [Score]
```

## 🧪 Testing

Run tests with:
```bash
pytest tests/
```

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit changes (`git commit -m 'Add your feature'`)
4. Push to branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Disclaimer

- Ensure you have rights to use YouTube content for summarization
- Respect YouTube's Terms of Service
- Be mindful of API rate limits
- Some videos may not have transcripts available

## 🐛 Troubleshooting

### Transcript Not Available
- Some videos disable transcripts; not all videos have transcripts
- Try enabling auto-generated captions in video settings

### API Rate Limits
- Implement request throttling
- Use caching for repeated queries

### Poor Summary Quality
- Ensure video has clear audio
- Try adjusting chunk size and overlap parameters
- Consider using a more capable LLM model

## 📞 Support

For issues and questions:
- Open an issue on GitHub
- Check existing documentation
- Review troubleshooting section

## 🔗 Related Projects

- [LangChain](https://github.com/langchain-ai/langchain)
- [Chroma](https://www.trychroma.com/)
- [Hugging Face Transformers](https://huggingface.co/transformers/)

---

**Made with ❤️ by Swizknife**
