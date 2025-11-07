# AutoMark: A Mini Multi-Agent Marketing Team

A lightweight simulation of a multi-agent marketing team that autonomously creates and executes campaign plans from brand briefs.

## 🎯 Features

- **Manager Agent**: Breaks down briefs into tasks and orchestrates the team
- **Copywriter Agent**: Generates ad copy, slogans, and social media content
- **Data Analyst Agent**: Suggests audience segments and channels based on data
- **Outreach Agent**: Drafts outreach emails and influencer pitches
- **Shared Memory**: JSON-based context manager for agent collaboration
- **Self-Improvement**: Evaluation and revision loops for quality control

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
AutoMarketing Agent/
├── automark.py                 # Main entry point
├── requirements.txt            # Dependencies
├── .env                        # Environment variables (create from .env.example)
├── campaign_context.json       # Generated context file
├── memory/
│   ├── __init__.py
│   └── context_manager.py      # Shared memory system
├── agents/
│   ├── __init__.py
│   ├── base_agent.py           # Base agent class
│   ├── copywriter_agent.py     # Copywriter specialist
│   ├── data_analyst_agent.py   # Data analyst specialist
│   ├── outreach_agent.py       # Outreach specialist
│   └── manager_agent.py        # Manager orchestrator
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
- **Memory**: JSON-based context manager
- **Data**: CSV marketing dataset

## 📝 Notes

- The system uses GPT-4o-mini by default (cost-effective)
- Context is saved to `campaign_context.json` for persistence
- Each campaign execution creates a new context entry
- The data analyst can work with or without a dataset

## 🤝 Contributing

This is a demonstration project. Feel free to extend it with:
- Additional specialist agents
- More sophisticated evaluation logic
- Database-backed memory
- Web interface
- Multi-campaign management

## 📄 License

MIT License

