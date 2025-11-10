# Quick Setup Guide - Interview Prep

## 🚀 Install New Dependencies (5 minutes)

```bash
# Install ChromaDB for vector memory
pip install chromadb

# Or update all requirements
pip install -r requirements.txt
```

## ✅ Test the New Features

### 1. Test Vector Memory
Run a campaign to see vector memory in action:

```bash
python automark.py --brief "Promote eco-friendly water bottle"
```

The system will now:
- Store the campaign in vector memory
- Enable semantic search for similar campaigns
- Agents can learn from past campaigns

### 2. Test Multiple Campaigns
Run a few campaigns to build up the memory:

```bash
python automark.py --brief "Launch new fitness app"
python automark.py --brief "Promote sustainable fashion brand"
python automark.py --brief "Market organic food delivery service"
```

### 3. Verify Vector Memory is Working
Check if campaigns are being stored:

```python
from memory.context_manager import ContextManager

cm = ContextManager()
stats = cm.get_vector_memory_stats()
print(f"Vector memory available: {stats['available']}")
print(f"Campaigns stored: {stats['campaign_count']}")

# Search for similar campaigns
similar = cm.get_similar_campaigns("fitness and health", n=3)
print(f"Found {len(similar)} similar campaigns")
```

## 🎯 What's New

### 1. Vector-Based Memory
- **Before**: JSON file with basic storage
- **Now**: Vector database with semantic search
- **Benefit**: Agents can find similar past campaigns, not just exact matches

### 2. Specialized Prompts
- **Before**: Generic prompts for each agent
- **Now**: Expert-level specialized prompts
- **Benefit**: Simulates fine-tuned models, ready for actual fine-tuning

### 3. Agent Communication Protocol
- **Before**: Only shared context
- **Now**: Structured messaging system between agents
- **Benefit**: Enables dynamic agent-to-agent communication

## 📝 Interview Talking Points

### Vector Memory
- "I upgraded from JSON to vector database for semantic search"
- "Agents can now retrieve relevant past campaigns based on similarity"
- "This enables learning from past experiences"

### Specialized Prompts
- "I've designed the system with fine-tuning in mind"
- "Each agent has specialized prompts that simulate fine-tuned models"
- "In production, I would fine-tune separate models for each agent type"

### Communication Protocol
- "I've implemented a communication protocol for agent-to-agent messaging"
- "This enables dynamic collaboration beyond the static workflow"
- "In production, this would use message queues (Kafka, RabbitMQ)"

## 🔧 Troubleshooting

### ChromaDB not installing?
```bash
# Try upgrading pip first
pip install --upgrade pip
pip install chromadb
```

### Vector memory not working?
- Check if ChromaDB is installed: `pip list | grep chromadb`
- The system will continue working without it (graceful degradation)
- Check console for warnings

### Import errors?
- Make sure you're in the project root directory
- Check that all files are in place:
  - `memory/vector_memory.py`
  - `agents/specialized_prompts.py`
  - `agents/agent_communication.py`

## 🎯 Next Steps for Interview

1. **Run the system** - Make sure everything works
2. **Review the code** - Understand what you built
3. **Practice explaining** - Be ready to discuss the improvements
4. **Study the concepts** - Review multi-agent systems, fine-tuning, vector DBs
5. **Prepare questions** - Think about what to ask the interviewers

## 📚 Key Files to Review

- `memory/vector_memory.py` - Vector database implementation
- `memory/context_manager.py` - Updated with vector memory integration
- `agents/specialized_prompts.py` - Expert prompts for each agent
- `agents/agent_communication.py` - Communication protocol
- `agents/manager_agent.py` - Updated with communication bus
- `agents/copywriter_agent.py` - Updated with specialized prompt and vector search

## 🚀 You're Ready!

You've added:
- ✅ Vector-based memory for semantic search
- ✅ Specialized prompts (fine-tuning ready)
- ✅ Agent communication protocol
- ✅ Learning from past campaigns

Good luck with your interview! 🎉

