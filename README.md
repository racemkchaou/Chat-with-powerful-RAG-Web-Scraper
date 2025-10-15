🤖 AI Web Scraper with RAG

A powerful AI-powered web scraper that uses Retrieval Augmented Generation (RAG) to answer questions about website content. Built with Streamlit, LangChain, and local LLMs via Ollama.

✨ Features
🌐 Web Scraping: Extract content from any website using Selenium
🧠 Local AI Processing: Uses Ollama LLMs (no API keys required)
🔍 Semantic Search: Find relevant content using vector embeddings
💬 Interactive Chat: Natural conversation about scraped content
📊 Real-time Processing: See scraping and processing progress
🚀 100% Local: Your data never leaves your machine

🛠️ Tech Stack
Frontend: Streamlit
AI Framework: LangChain
LLM: Ollama (Llama 3.2)
Embeddings: Ollama Embeddings
Vector Store: InMemoryVectorStore
Web Scraping: Selenium
Text Processing: RecursiveCharacterTextSplitter

📋 Prerequisites
Before you begin, ensure you have:

Python 3.8 or higher
Ollama installed on your system
Chrome/Firefox browser (for Selenium)

🚀 Quick Start
Step 1: Install Ollama
Windows:
Download from ollama.ai

Run the installer

macOS:
bash
brew install ollama

Linux:
bash
curl -fsSL https://ollama.ai/install.sh | sh

Step 2: Download AI Models
bash

# Download chat model and embedding model
ollama pull llama3.2
Step 3: Clone and Setup
bash
# Clone the repository
git clone https://github.com/racemkchaou/LLM-with-RAG-Web-Scraper.git
cd LLM-with-RAG-Web-Scraper

# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

Step 4: Run the Application
bash
# Make sure Ollama is running
ollama serve

# In a new terminal, run the Streamlit app
streamlit run ai_scraper.py
The application will open in your browser at http://localhost:8501

📖 Usage Guide
Enter URL: Paste any website URL in the input field

Scrape Content: The app automatically loads and processes the website
Ask Questions: Use the chat interface to ask questions about the content
Get Answers: AI provides concise answers based on the scraped content

Example Workflow:
text
URL: https://en.wikipedia.org/wiki/Artificial_intelligence
Question: "What are the main applications of AI?"
Answer: "Based on the content, the main applications of AI include..."
🗂️ Project Structure
text
LLM-with-RAG-Web-Scraper/
├── ai_scraper.py              # Main application file
├── requirements.txt           # Python dependencies
├── README.md                  # This file
└── .gitignore                # Git ignore file
🔧 Configuration
Customizing Models
You can modify the AI models in ai_scraper.py:

python
# For embeddings
embeddings = OllamaEmbeddings(model="llama3.2")

# For chat
model = OllamaLLM(model="llama3.2", temperature=0.3)
Available Ollama Models
Embedding Models: nomic-embed-text, all-minilm

Chat Models: llama3.2, llama3.1, mistral, codellama

🐛 Troubleshooting
Common Issues
1. "Model not found" error

bash
# Verify models are downloaded
ollama list

# Download missing models
ollama pull nomic-embed-text
ollama pull llama3.2
2. Selenium driver issues

bash
# Install webdriver manager
pip install webdriver-manager

# The application will automatically handle drivers
3. Ollama connection error

bash
# Start Ollama service
ollama serve

# Verify it's running
curl http://localhost:11434/api/tags
4. Memory issues with large websites

The app automatically chunks large content

Uses efficient vector search

Implements memory optimization

🎯 Performance Tips
For better accuracy: Use llama3.2:11b if you have sufficient RAM

For faster responses: Use mistral model

For large websites: Increase chunk_size to 1500

For precise answers: Set temperature=0.1

🔍 How It Works
Technical Pipeline:
text
1. URL Input → Selenium Scraping → HTML Content
2. Text Extraction → Recursive Text Splitting → Chunks
3. Ollama Embeddings → Vector Storage → Semantic Index
4. User Question → Vector Similarity Search → Relevant Context
5. LLM Generation → Context + Question → Concise Answer
RAG Architecture:
Retrieval: Finds most relevant text chunks using cosine similarity

Augmentation: Enhances LLM prompt with retrieved context

Generation: Produces accurate, context-aware answers

🤝 Contributing
We welcome contributions! Please feel free to submit issues and pull requests.

Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request


🙏 Acknowledgments
Streamlit for the amazing web framework

LangChain for the LLM orchestration

Ollama for local model management

Selenium for web scraping capabilities

📞 Support
If you encounter any problems or have questions:

Check the troubleshooting section
Open an issue
Contact the maintainer
