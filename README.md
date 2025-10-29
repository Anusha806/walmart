** Hybrid Fashion Product Search Engine**

A multimodal vector search application that enables users to search for fashion products using:

**- Text Queries
- Voice Search
- Image-based Reverse Search
**
Powered by Hybrid Search (Dense + Sparse embeddings) using Pinecone, Sentence Transformers, BM25, and CLIP, with a beautiful UI built in Gradio.

Features
**Feature	Description**
Text Search                 Semantic + keyword-aware search using hybrid vector retrieval
Voice Query	                Speech-to-text using Whisper, automatically converts voice to query
Image Search	    Reverse image lookup using CLIP vision embeddings
Metadata Filtering	    Smart filtering for gender, article type, sub-category, colors
Intent Extraction	    Optional OpenAI-based NLP intent understanding
Hybrid Architecture	    bm25 sparse + CLIP dense = accurate & relevant recommendations
Duplicate Removal	    Perceptual hashing avoids repeat results
Pre-loaded Dataset	    Uses “Fashion Product Images Small” dataset (45K products)


**Tech Stack****
Layer	Tools**
Vector DB	                  Pinecone Serverless Index
Sparse Encoding	      BM25Encoder
Dense Encoding	      SentenceTransformer clip-ViT-B-32
Image Embedding	      OpenAI CLIP
Voice Recognition	      OpenAI Whisper
UI 	                  Gradio
Dataset	                  HuggingFace: ashraq/fashion-product-images-small


**Installation**
1️⃣ Create Virtual Environment (Optional but recommended)

**python -m venv venv
source venv/bin/activate    # MacOS / Linux
venv\Scripts\activate       # Windows
**

2️⃣ Install Dependencies
**pip install -r requirements.txt
**

 Environment Variables

**Create a .env file in your project root:**

**OPENAI_API_KEY=your_openai_key
PINECONE_API_KEY=your_pinecone_key
PINECONE_REGION=us-east-1
PINECONE_CLOUD=aws**

Run the App

**python app.py**


Then open your browser at:

**👉 http://localhost:7860/**

**🧩 Architecture**

User Input (Text / Voice / Image)
            │
            ▼
Intent Parser (OpenAI GPT) ───► Metadata Filters
            │
            ▼
Hybrid Encoder ───────────────► Pinecone Index
  - BM25 Sparse Vector         │
  - CLIP Dense Embedding       ▼
                      Ranked Matching Results
                                |
                                ▼
                             Gradio UI (Gallery)


**UI Preview**

<img width="1449" height="940" alt="image" src="https://github.com/user-attachments/assets/73b04915-8377-47f1-beab-dd4dea0f30a1" />



Pull requests are welcome!
If you have suggestions, open an issue 🌟
