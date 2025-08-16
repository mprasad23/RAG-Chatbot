# RAG-Chatbot
This project demonstrates a simple Retrieval-Augmented Generation (RAG) chatbot built using Ollama. It loads a text file (Ashoka the Great.txt), splits it into chunks, embeds them into vectors, and retrieves the most relevant knowledge when a user asks a question.

🚀 Features

Loads custom dataset (Ashoka the Great.txt) line by line.

Generates embeddings for each chunk using bge-base-en-v1.5 model.

Stores embeddings in a simple in-memory vector database (VECTOR_DB).

Uses cosine similarity for semantic search.

Retrieves the most relevant context for answering user queries.

Prepares a structured instruction prompt for the chatbot.

📂 Project Structure

├── Ashoka the Great.txt    # Dataset with knowledge about Ashoka

├── main.py                 # Main chatbot script

└── README.md               # Documentation

⚙️ Requirements

Python 3.8+
Ollama installed and running locally

Python packages:
pip install ollama

🛠️ How It Works
Load Dataset – Reads the file Ashoka the Great.txt.
Generate Embeddings – Calls ollama.embed() to embed each chunk.
Store in Vector DB – Saves (chunk, embedding) in a list.

Query – User enters a question.
Retrieve Relevant Chunks – Finds top N matches using cosine similarity.
Prepare Prompt – Formats the retrieved knowledge as context for answering.

▶️ Usage
Run the script:
python main.py


Example interaction:

Ask me a question: Who was Ashoka the Great?
Retrieved knowledge:
 - (similarity: 0.82) Ashoka was one of the greatest emperors of India...
 - (similarity: 0.78) He promoted Buddhism and peace...
 - (similarity: 0.65) The Kalinga War changed his life...

🔮 Future Improvements
Add chunking (split by paragraphs instead of lines).
Store embeddings in a persistent vector database (e.g., FAISS, ChromaDB).
Connect with the language model (Llama 3.2) to generate full answers.
Build a web UI using Streamlit or Flask.
