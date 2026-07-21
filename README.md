![OReilly_logo_rgb.png](resources%2FOReilly_logo_rgb.png)

This repository contains the hands-on exercises for the O’Reilly Live Event:

# AI Agents Bootcamp – Designing and Deploying Enterprise Agentic Systems

## Repository Structure

```
.
├── hands_on/  # Hands-on exercises
├── helper_functions/  # Helper functions for some notebooks     
└── README.md
```

---

# Day 1 – Foundations and Multi-Agent Design

## 1. From Stateless LLM to Stateful Agent

**Concepts**

- State machines and typed state
- Tool integration in LangGraph
- Deterministic control flow

**Exercise**

Build a minimal stateful agent with one tool.


---

## 2. Structured Reasoning and Test-Time Intelligence

**Concepts**

- Chain of Thought and ReAct
- Planner–executor vs unified agents
- Test-time compute tradeoffs
- Error propagation and validation

**Exercise**

Compare a simple agent with a planner–judge setup.



---

## 3. Human-in-the-Loop Safeguards

**Concepts**

- Autonomy vs oversight
- Checkpointing and state inspection
- Interrupt and resume patterns

**Exercise**

Insert a human approval gate into your workflow.



---

## 4. From Single Agent to Multi-Agent System

**Concepts**

- Supervisor-based architectures
- Role separation
- Delegation and task routing

**Exercise**

Transform a single-agent workflow into a two-agent system.



---

## 5. Communication Patterns in MAS

**Concepts**

- Message passing vs shared memory
- Event-driven coordination
- Handoff reliability

**Exercise**

Swap a communication strategy and observe system behavior changes.



---

# Day 2 – Production-Ready Systems

## 6. Structured Data and MCP

**Concepts**

- Schema-based prompting
- Pydantic validation
- Model Context Protocol (MCP)

**Exercise**

Turn free-form input into validated structured tool calls.



---

## 7. Memory and Context Strategy

**Concepts**

- Episodic vs procedural memory
- Checkpointing
- Context engineering

**Exercise**

Add simple episodic and procedural memory to your agent.



---

## 8. Model and Architecture Tradeoffs

**Concepts**

- Planner vs unified agents
- Thinking vs non-thinking modes
- Dense vs MoE models
- KV cache considerations

**Exercise**

Switch planning modes and compare latency and decision quality.



---

## 9. Observability and Evaluation

**Concepts**

- Logging state transitions
- Monitoring workflows
- Task-specific evaluation

**Exercise**

Add logging hooks and compare two workflow runs.



---

## 10. Security and Guardrails

**Concepts**

- Tool misuse and memory poisoning
- Schema enforcement
- Secure execution patterns

**Exercise**

Add policy checks and validation to an existing workflow.




---

## Running the Notebooks

All notebooks are designed to run in **Google Colab**.

1. Open a notebook using its Colab link.
2. Install the required dependencies when prompted.
3. Configure the API key for the model provider used in the notebook.
4. Run the notebook cells in order.

### Using OpenRouter

The notebooks can use OpenRouter through LangChain’s `ChatOpenAI` integration by specifying the OpenRouter API endpoint:

```python
from langchain_openai import ChatOpenAI

LLM = ChatOpenAI(
    model=OPENROUTER_MODEL,
    base_url="https://openrouter.ai/api/v1",
    api_key=OPENROUTER_API_KEY,
    temperature=0,
)
```

Use the OpenRouter model identifier shown on the model’s OpenRouter page, for example:

```text
openai/gpt-5.4-nano
```

### Configuring API Keys

Never commit API keys to the repository.

The notebooks support loading configuration from a `.env` file:

```python
from dotenv import load_dotenv
import os

load_dotenv()

OPENROUTER_API_KEY = os.getenv("OPENROUTER_API_KEY")
OPENROUTER_MODEL = os.getenv(
    "OPENROUTER_MODEL",
    "openai/gpt-5.4-nano",
)
```

#### Option 1: Create a `.env` File

In Colab environments that provide terminal access, such as some paid Colab plans, create a `.env` file in the notebook’s working directory:

```bash
cat <<'EOF' > .env
LLM_PROVIDER=openrouter
OPENROUTER_API_KEY=your_openrouter_key_here
OPENROUTER_MODEL=openai/gpt-5.4-nano
EOF
```

Replace `your_openrouter_key_here` with your actual API key.

To use OpenAI directly instead, the file could contain:

```bash
cat <<'EOF' > .env
LLM_PROVIDER=openai
OPENAI_API_KEY=your_openai_key_here
OPENAI_MODEL=gpt-5.4-nano-2026-03-17
EOF
```

#### Option 2: Create the `.env` File from a Notebook Cell

When terminal access is unavailable, create the file from a Colab code cell:

```python
from pathlib import Path

Path(".env").write_text(
    """
LLM_PROVIDER=openrouter
OPENROUTER_API_KEY=your_openrouter_key_here
OPENROUTER_MODEL=openai/gpt-5.4-nano
""".strip()
)
```

Then load it:

```python
from dotenv import load_dotenv

load_dotenv(override=True)
```

#### Option 3: Set Environment Variables Directly

For a temporary Colab session, environment variables can also be set directly in a notebook cell:

```python
%env LLM_PROVIDER=openrouter
%env OPENROUTER_API_KEY=your_openrouter_key_here
%env OPENROUTER_MODEL=openai/gpt-5.4-nano
```

These values exist only for the current Colab runtime and must be entered again after the runtime is restarted.

---

Design deliberately.  
Deploy responsibly.

