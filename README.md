# OpenAI RAG (Document Q&A)

This is a small RAG project that lets you ask questions about a PDF.

It works by turning the document into embeddings, finding the most relevant chunks for your question, and then sending those chunks to the chat model as context. So the answer comes from the document, not just the model guessing.

## Demo

I uploaded a short demo video here:
OpenAI RAG.mov

## What it does

- Loads a PDF and extracts the text
- Splits the text into chunks
- Creates embeddings for those chunks (OpenAI embeddings)
- Embeds your question and finds the closest chunks (cosine similarity)
- Sends the chunks + your question to the chat model
- Keeps basic chat history so follow-up questions work better

## About the document

The PDF I used for testing is not included in this repo because it’s large.

To run this on your own file, create a folder called `data` and add your PDF:


data/document.pdf


Then update the PDF path in the notebook if needed.

## Run it locally

1) Install dependencies:


pip install -r requirements.txt


2) Create a `.env` file in the project root:


OPENAI_API_KEY=your_api_key_here


3) Open the notebook and run it top to bottom:

- `openai-rag.ipynb`

The last part of the notebook runs a simple chat loop where you can ask questions.

## Built with

- Python
- OpenAI API (embeddings + chat)
- NumPy
- PyPDF
- tiktoken

## Notes

- Don’t upload your `.env` file to GitHub.
- Large PDFs are intentionally not tracked in the repo.

## Next things I’d improve

- Use FAISS (or a vector DB) for faster search on bigger document sets
- Better chunking (overlap + keeping headings/metadata)
- A small UI (Streamlit) so it’s easier to demo
