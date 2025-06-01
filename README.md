# Graphiti-Pydantic

Graphiti-Pydantic is a Python project that demonstrates how to build, search, and interact with a temporal knowledge graph of Large Language Models (LLMs) using [Graphiti Core](https://github.com/zepresearch/graphiti-core), [Pydantic AI](https://github.com/zepresearch/pydantic-ai), and Neo4j. The project provides scripts and an agent for adding, evolving, and querying knowledge about LLMs, with a focus on temporal and factual accuracy.

## Features
- **Knowledge Graph Construction:** Add structured and unstructured episodes (facts) about LLMs to a Neo4j-powered knowledge graph.
- **Temporal Reasoning:** Track the evolution of LLMs and their facts over time.
- **Hybrid Search:** Perform semantic and BM25-based searches over the knowledge graph.
- **Conversational Agent:** Interact with the knowledge graph using a Pydantic AI-powered agent.
- **Extensible Recipes:** Use and customize search recipes for advanced graph queries.

## Requirements
- Python 3.8+
- Neo4j (local or remote instance)
- See `requirements.txt` for all Python dependencies.

## Setup
1. **Clone the repository:**
   ```bash
   git clone https://github.com/devjothish/Graphiti-Pydantic.git
   cd Graphiti-Pydantic
   ```
2. **Create and activate a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Set up environment variables:**
   Create a `.env` file in the project root with the following content:
   ```env
   NEO4J_URI=bolt://localhost:7687
   NEO4J_USER=neo4j
   NEO4J_PASSWORD=your_password
   OPENAI_API_KEY=your_openai_api_key  # Only needed for agent.py
   MODEL_CHOICE=gpt-4.1-mini           # Optional, for agent.py
   ```
   Adjust values as needed for your Neo4j and OpenAI setup.

## Usage

### 1. Quickstart: Build and Search the Knowledge Graph
Run the quickstart script to initialize the graph, add example episodes, and perform searches:
```bash
python quickstart.py
```
- Adds sample facts about LLMs (text and JSON episodes)
- Demonstrates hybrid search, center node reranking, and node search with recipes

### 2. LLM Evolution: Simulate the Evolution of LLMs
Run the evolution script to simulate how LLMs and their facts change over time:
```bash
python llm_evolution.py
```
- Adds, updates, and benchmarks LLMs in the knowledge graph
- Shows how to update facts and track temporal changes

### 3. Conversational Agent: Query the Knowledge Graph
Run the agent to interact with the knowledge graph using natural language:
```bash
python agent.py
```
- Provides a conversational interface powered by Pydantic AI and Graphiti
- Answers questions about LLMs using the knowledge graph
- Streams responses with markdown formatting

## Project Structure
- `quickstart.py` — Example script for initializing, populating, and searching the knowledge graph
- `llm_evolution.py` — Script to simulate the evolution and benchmarking of LLMs over time
- `agent.py` — Conversational agent for querying the knowledge graph
- `requirements.txt` — Python dependencies
- `.env` — Environment variables (not committed to version control)

## Dependencies
All dependencies are listed in `requirements.txt`. Key libraries include:
- `graphiti-core` — Knowledge graph construction and search
- `pydantic-ai` — Conversational agent framework
- `neo4j` — Graph database
- `python-dotenv` — Environment variable management
- `rich` — Console output formatting

## License
This project is licensed under the Apache License 2.0. See the source files for details.

## Acknowledgments
- [Graphiti Core](https://github.com/zepresearch/graphiti-core)
- [Pydantic AI](https://github.com/zepresearch/pydantic-ai)
- [Neo4j](https://neo4j.com/)