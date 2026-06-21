# AgenticLangraph

AgenticLangraph is a small Python learning project for building agentic chatbots with LangGraph and LangChain. The examples use Groq-hosted chat models, Tavily search tools, in-memory LangGraph state, and a human-in-the-loop workflow.

## Project Structure

```text
.
|-- basicchatbot/
|   |-- 1.basicchatbot.ipynb        # Basic LangGraph chatbot and tool-calling flow
|   `-- 2.HumanAssistance.ipynb     # Human-in-the-loop interrupt/resume example
|-- main.py                         # Minimal Python entry point
|-- pyproject.toml                  # Project metadata and dependencies
|-- requirement.txt                 # Simple requirements list
`-- uv.lock                         # Locked dependency versions for uv
```

## Requirements

- Python 3.10 or newer
- A Groq API key
- A Tavily API key for search-enabled examples
- Optional: LangSmith credentials for tracing and observability

## Setup

Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Install dependencies with `uv`:

```bash
uv sync
```

Or install with `pip`:

```bash
pip install -e .
```

## Environment Variables

Create a `.env` file in the project root and add the keys needed by the notebooks:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key

# Optional LangSmith tracing
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_TRACING=true
LANGSMITH_PROJECT=agenticlangraph
```

## Usage

Run the simple Python entry point:

```bash
python main.py
```

Open the notebooks in VS Code, JupyterLab, or Jupyter Notebook. If you need the classic notebook server, install and start it:

```bash
pip install notebook
jupyter notebook
```

Recommended order:

1. `basicchatbot/1.basicchatbot.ipynb`
2. `basicchatbot/2.HumanAssistance.ipynb`

## What the Notebooks Cover

- Defining LangGraph state with `TypedDict` and `add_messages`
- Building a chatbot node with `StateGraph`
- Calling Groq models through LangChain
- Adding Tavily search as a tool
- Routing tool calls with `ToolNode` and `tools_condition`
- Using LangGraph interrupts for human assistance
- Resuming an interrupted graph with `Command`

## Notes

The notebooks currently use the `groq:llama-3.1-8b-instant` model. Make sure your Groq account has access to the model before running the examples.
