# TechNest UK – AI Customer Support Chatbot 🤖

An AI-powered customer support chatbot built for **TechNest UK**, a fictional online electronics retailer. The assistant answers customer questions about pricing, shipping, returns, warranties, payments, and general store policies — powered by OpenAI's API and served through a simple Gradio chat interface.

## ✨ Features

- **Streaming responses** — answers appear token-by-token for a natural chat feel
- **Role-grounded system prompt** — the assistant only discusses TechNest UK products/services and avoids inventing policies, prices, or specs
- **Multi-turn conversation history** — maintains context across the chat session
- **Simple web UI** — powered by [Gradio](https://www.gradio.app/)'s `ChatInterface`
- **Guardrails** — politely declines legal/financial/medical advice and stays calm with frustrated customers

## 🛠️ Tech Stack

| Component        | Details                          |
|-------------------|-----------------------------------|
| Language          | Python 3.12                       |
| LLM               | OpenAI `gpt-5-nano` (via Chat Completions API) |
| UI                | Gradio `ChatInterface`            |
| Env management    | `python-dotenv`                   |

## 📂 Project Structure

```
.
├── chatbot.ipynb        # Main notebook with chatbot logic and Gradio UI
├── .env                   # Environment variables (not committed)
└── README.md
```

## 🚀 Getting Started

### 1. Clone the repository

### 2. Create a virtual environment and install dependencies

```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate

pip install openai gradio python-dotenv httpx
```

### 3. Set up your API key

Create a `.env` file in the project root:

```
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxxx
```

### 4. Run the notebook

Open `chatbot.ipynb` in Jupyter or VS Code and run all cells. This will:

- Verify your API key
- Launch a Gradio chat interface at `http://127.0.0.1:7860`

```bash
jupyter notebook chatbot.ipynb
```

## 💬 Example Interaction

> **User:** Do you offer free shipping?
> **Assistant:** Yes! Orders over £50 qualify for free standard shipping (2–5 business days). We also offer Express (Next Business Day) delivery for an additional fee.

## 🔒 Notes on the System Prompt

The assistant is grounded with detailed company information (business hours, return policy, warranty terms, payment methods, etc.) so it responds accurately and avoids hallucinating facts about TechNest UK.

## 📌 Roadmap / Ideas for Improvement

- [ ] Add order-tracking lookup via a mock database
- [ ] Deploy publicly (Hugging Face Spaces / Render / Railway)
- [ ] Add authentication for support agents to review chat logs
- [ ] Swap in retrieval-augmented generation (RAG) for live product data


## 🙋 About

Built as a hands-on project to practice building LLM-powered customer support tools with the OpenAI API and Gradio.
