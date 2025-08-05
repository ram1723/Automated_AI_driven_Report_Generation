**Project Title**  
Automated AI-driven Report Generation  

**Overview**  
This project demonstrates how to build an end-to-end AI-powered report generation system using NVIDIA AI Endpoints, Tavily for search, LangGraph, and LangChain. It plans and structures the report, retrieves relevant information, and synthesizes it into a polished technical report based on user-defined topics and guidelines.

---

## Table of Contents  
- [Features](#features)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Environment Setup](#environment-setup)  
- [Usage](#usage)  
- [Project Structure](#project-structure)  
- [Key Components](#key-components)  
- [Example Workflow](#example-workflow)  
---

## Features  
- **Topic Planning**: Generates search queries tailored to your report topic.  
- **Information Retrieval**: Fetches data using Tavily search and deduplicates sources.  
- **Structured Outline**: Uses LangChain structured outputs to define report sections with descriptions and research notes.  
- **Content Generation**: Leverages NVIDIA LLM endpoints to write detailed section content.  

---

## Prerequisites  
- Python 3.8 or later  
- Colab or local Jupyter environment  
- Access to NVIDIA AI Playground for API keys  

---

## Installation  
Install required Python packages via pip:

```bash
pip install -U langgraph langchain_community langchain_core tavily-python langchain_nvidia_ai_endpoints
Environment Setup
NVIDIA API Key

Create a key in the NVIDIA AI Playground.

In Colab, add it to the Secrets Manager (🔑) with the name NVIDIA_API_KEY.

Tavily API Key

Obtain your Tavily key and add it to Colab Secrets as TAVILY_API_KEY.

Local Setup (optional)

Create a .env file in the project root:

env
Copy
Edit
NVIDIA_API_KEY=your_nvidia_key_here
TAVILY_API_KEY=your_tavily_key_here
Load environment variables in your Python script:

python
Copy
Edit
from dotenv import load_dotenv
load_dotenv()
Usage
Open report_generation.ipynb in Google Colab or Jupyter Notebook.

Install dependencies (first cell).

Configure your API keys as shown above.

Define your report parameters (topic, structure, number of queries).

Run the planner and writer cells to generate your report.

Export or download the final report as needed.

Project Structure
bash
Copy
Edit
├── report_generation.ipynb    # Main Colab notebook with setup and pipeline
├── utils.py                   # Utility functions for search and formatting (if extracted)
├── requirements.txt           # Pin versions of dependencies
└── README.md                  # You are here
Key Components
Pydantic Models: Define data schemas for sections, queries, and overall report state.

LangChain & LangGraph: Orchestrate LLM calls with structured outputs.

Tavily Search: Perform synchronous and asynchronous web searches.

NVIDIA Chat Endpoint: Generate high-quality natural language content.

Example Workflow
python
Copy
Edit
from langchain_nvidia_ai_endpoints import ChatNVIDIA
from tavily import TavilyClient

# Initialize clients
client = ChatNVIDIA(model="meta/llama-3.3-70b-instruct", api_key="${NVIDIA_API_KEY}")
tavily = TavilyClient(api_key="${TAVILY_API_KEY}")

# Plan queries for topic
queries = plan_queries(topic="AI in Healthcare", report_organization=structure, number_of_queries=5)

# Retrieve sources
search_results = tavily_search(queries, topic="news", days=7)

# Generate report sections and content
generated_report = await generate_report(topic="AI in Healthcare", ...)
print(generated_report.final_report)
