# Specs
Code 3.0 Framework allows developers to easily create self-improving LLM-based agents by abstracting the repetitive components:
```
🔁 Core Architecture:
[Goal/Task]
   ↓
[Generate Solution (LLM)]
   ↓
[Execute or Simulate]
   ↓
[Evaluate Results]
   ↓
[Reflect & Improve (LLM)]
   ↓
[Loop or Store to Memory]
```

| Module         | Responsibility                                         |
| -------------- | ------------------------------------------------------ |
| `Agent`        | Defines the task, prompts, and behavior                |
| `Executor`     | Runs generated code or logic                           |
| `Evaluator`    | Compares outputs vs expected behavior (tests, metrics) |
| `Critic`       | Uses LLM to reflect and improve                        |
| `Memory`       | Stores results, decisions, and revisions               |
| `Orchestrator` | Manages the loop and coordination                      |

Technologies
- LLMs: OpenAI API, Claude, or local models via Ollama
- Memory: SQLite, Redis, or vector DBs like Chroma/Weaviate
- Agent orchestrators (optional): LangChain, CrewAI, AutoGen
- Execution sandbox: exec(), subprocess, or Docker containers for safety

## Architecture
```
code3/
├── agent.py         # BaseAgent, goal-driven
├── executor.py      # Code or task execution
├── evaluator.py     # Task result evaluation logic
├── critic.py        # Self-reflection using LLM
├── memory.py        # Persistent storage
├── orchestrator.py  # Main loop controller
├── examples/
│   └── self_improving_scraper.py
```

Example:
```
from code3 import Agent, Orchestrator

agent = Agent(task="Scrape product prices from site X")
orchestrator = Orchestrator(agent=agent)
orchestrator.run()
```

## Self-improvement
While running or developing the application, its logics could be grown. For example:
- Expense app that tracks user's expenses and record it into database or memory. 
- Users list out today's expenses and see there is one mistaken expense, he/she wants to delete it. However, the program doesn't have delete feature. Now it's improving itself by adding that new feature, and update the prompt and its tool/API.





