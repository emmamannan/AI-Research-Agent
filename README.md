# AI Research Agent

> A modular AI research assistant built with **LangChain** that can search, summarize, and save information using structured outputs.

---

## Overview

This **AI Research Agent** leverages **OpenAI’s GPT models** (with LangChain integration) and a set of tools to:

- **Search** for information  
- **Retrieve summaries** (via Wikipedia and search APIs)  
- **Save outputs** locally  
- **Generate structured research responses** with topic, summary, sources, and tools used  

This project demonstrates how to build a **tool-augmented research workflow** with LangChain.

---

## Features

- **Custom research schema**: returns topic, summary, sources, and tools used  
- **Tool integration**:
  - `search_tool` → external search for information  
  - `wiki_tool` → retrieve summaries from Wikipedia  
  - `save_tool` → save final structured output  
- **Interactive CLI**: accepts user queries and prints structured responses  

---

## Tech Stack

- **Python 3.10+**  
- **LangChain** for LLM orchestration  
- **OpenAI GPT models** (`gpt-5-nano` by default)  
- **Pydantic** for structured responses  
- **dotenv** for environment variable management  

---

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/emmamannan/AI-Research-Agent
cd AI-Research-Agent
````

### 2. Set up a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root and add your API keys:

```bash
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key   # if using Anthropic
```

### 5. Run the agent

```bash
python main.py
```

You’ll be prompted with:

```bash
What can I help you research?
```

Enter your query (e.g. *“Latest trends in AI research agents”*) and get a structured response.

---

## Example

**User Input**:

```
What can I help you research? 
Advances in renewable energy storage
```

**Output**:

```json
{
  "topic": "Advances in renewable energy storage",
  "summary": "Recent progress includes improved lithium-ion battery efficiency, expansion of solid-state batteries, and innovations in grid-scale storage like flow batteries and compressed air energy storage.",
  "sources": [
    "https://example.com/source1",
    "https://en.wikipedia.org/wiki/Renewable_energy_storage"
  ],
  "tools_used": ["search_tool", "wiki_tool", "save_tool"]
}
```

---


## Future Enhancements

* Add **citation tracking** for academic references
* Extend toolset with **PDF reader** or **scholarly article retriever**
* Support **multi-query aggregation** for longer research tasks
* Add **web UI** with Streamlit or FastAPI
