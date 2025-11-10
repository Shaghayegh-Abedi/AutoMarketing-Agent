# AutoMark: A Mini Multi-Agent Marketing Team (Enhanced)

A lightweight simulation of a multi-agent marketing team that autonomously creates and executes campaign plans from brand briefs. **Enhanced version** with vector-based memory, specialized agent prompts, and agent communication protocols.

## 🎯 Features

- **Manager Agent**: Breaks down briefs into tasks and orchestrates the team
- **Copywriter Agent**: Generates ad copy, slogans, and social media content
- **Data Analyst Agent**: Suggests audience segments and channels based on data
- **Outreach Agent**: Drafts outreach emails and influencer pitches
- **Shared Memory**: JSON-based context manager + Vector database for semantic search
- **Self-Improvement**: Evaluation and revision loops for quality control
- **Vector Memory**: Semantic search of past campaigns for learning
- **Specialized Prompts**: Expert-level prompts designed for fine-tuning
- **Agent Communication**: Structured messaging protocol for inter-agent communication

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- OpenAI API key

### Installation

1. Clone or download this repository

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up your OpenAI API key:
```bash
# Create .env file from template
# On Windows PowerShell:
Copy-Item .env.example .env

# On Mac/Linux:
cp .env.example .env

# Edit .env and add your OPENAI_API_KEY
```

Get your API key from: https://platform.openai.com/api-keys

### Usage

Run AutoMark with a campaign brief:

```bash
python automark.py --brief "Promote eco-friendly water bottle"
```

**Options:**
- `--brief`: Campaign brief (required)
- `--revisions`: Maximum revision cycles (default: 1)
- `--data-file`: Path to marketing dataset CSV (default: data/marketing_data.csv)
- `--context-file`: Path to context file (default: campaign_context.json)
- `--json-output`: Save JSON output to file
- `--json-only`: Output only JSON format

**Examples:**

```bash
# Basic usage
python automark.py --brief "Launch new fitness app"

# With more revision cycles
python automark.py --brief "Promote eco-friendly water bottle" --revisions 2

# Save JSON output
python automark.py --brief "Promote eco-friendly water bottle" --json-output campaign.json
```

## 📁 Project Structure

```
AutoMarketing Agent Enhanced/
├── automark.py                 # Main entry point
├── requirements.txt            # Dependencies
├── .env                        # Environment variables (create from .env.example)
├── campaign_context.json       # Generated context file
├── memory/
│   ├── __init__.py
│   ├── context_manager.py      # Shared memory system
│   └── vector_memory.py        # Vector database for semantic search
├── agents/
│   ├── __init__.py
│   ├── base_agent.py           # Base agent class
│   ├── copywriter_agent.py     # Copywriter specialist
│   ├── data_analyst_agent.py   # Data analyst specialist
│   ├── outreach_agent.py       # Outreach specialist
│   ├── manager_agent.py        # Manager orchestrator
│   ├── specialized_prompts.py  # Expert-level prompts
│   └── agent_communication.py  # Communication protocol
└── data/
    └── marketing_data.csv      # Sample marketing dataset
```

## 🔄 How It Works

1. **Manager** receives the brief and creates a task breakdown
2. **Specialists** work in parallel:
   - Copywriter generates content
   - Data Analyst suggests audiences/channels
   - Outreach creates email templates
3. **Manager** evaluates outputs and requests revisions if needed
4. **Manager** integrates all outputs into a final campaign plan
5. **Vector Memory** stores campaigns for future semantic search

## 📊 Output Format

The system outputs a structured campaign plan:

```json
{
  "target_audience": "Eco-conscious millennials",
  "core_message": "Sustain hydration, sustain the planet.",
  "content_examples": [
    "Instagram caption: ...",
    "Email draft: ...",
    ...
  ]
}
```

## 🛠️ Tech Stack

- **LLM**: OpenAI API (GPT-4o-mini)
- **Orchestration**: LangGraph
- **Memory**: JSON-based context manager + Vector database (ChromaDB) for semantic search
- **Agent Communication**: Structured messaging protocol for inter-agent communication
- **Specialized Prompts**: Expert-level prompts designed for fine-tuning (simulates fine-tuned models)
- **Data**: CSV marketing dataset

## 🆕 Recent Improvements

### Vector-Based Memory
- Semantic search of past campaigns using ChromaDB
- Agents can learn from similar past campaigns
- Enables RAG (Retrieval-Augmented Generation) for better context

### Specialized Agent Prompts
- Expert-level prompts for each agent type
- Designed with fine-tuning in mind
- Simulates fine-tuned model behavior

### Agent Communication Protocol
- Structured messaging system for agent-to-agent communication
- Enables dynamic collaboration beyond static workflows
- Ready for distributed systems (message queues)

## 📝 Notes

- The system uses GPT-4o-mini by default (cost-effective)
- Context is saved to `campaign_context.json` for persistence
- Each campaign execution creates a new context entry
- Vector memory stores campaigns for semantic search (requires ChromaDB)
- The data analyst can work with or without a dataset
- System gracefully degrades if ChromaDB is not available

## 🤝 Contributing

This is a demonstration project. Free to extend with:
- Additional specialist agents
- More sophisticated evaluation logic
- Database-backed memory (already implemented with vector DB)
- Web interface
- Multi-campaign management
- Model fine-tuning on proprietary data

## 📄 License

MIT License
