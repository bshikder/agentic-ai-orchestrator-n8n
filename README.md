## 🧩 Architecture Diagram

The following diagram illustrates the agentic AI orchestration flow implemented in n8n.

![Architecture Diagram](diagram_n8n.png‎)



## 🔍 Diagram Walkthrough

1. **Trigger**
   - Manual trigger simulates incoming user requests.

2. **Fallback Context Builder**
   - Prepares a minimal, safe context for unsupported or invalid tasks.

3. **Task Type Classifier**
   - Classifies user intent (e.g., calculation, search, reasoning).

4. **Task Validation Gate**
   - Deterministic control logic:
     - `TRUE` → Primary AI Orchestrator
     - `FALSE` → Fallback AI Orchestrator

5. **Primary AI Orchestrator**
   - Uses OpenAI Chat Model
   - Has access to:
     - Calculator tool
     - HTTP / Search tools
     - Shared session memory

6. **Fallback AI Orchestrator**
   - Gracefully handles:
     - Invalid tasks
     - Unsupported intents
   - Uses shared memory to maintain continuity

7. **Shared Memory**
   - Both agents use a common session memory
   - Ensures conversational consistency

👤 Author

Bashirul Shikder
Data Analyst | AI & Agentic Systems
🔗 GitHub: https://github.com/bshikder

🔗 LinkedIn: https://linkedin.com/in/bashirulshikder

⭐ Acknowledgment

Built to explore agentic AI patterns beyond prompt engineering, focusing on control, safety, and orchestration.
