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

[Open in Colab](COLAB_LINK_01)

---

## 2. Structured Reasoning and Test-Time Intelligence

**Concepts**

- Chain of Thought and ReAct
- Planner–executor vs unified agents
- Test-time compute tradeoffs
- Error propagation and validation

**Exercise**

Compare a simple agent with a planner–judge setup.

[Open in Colab](COLAB_LINK_02)

---

## 3. Human-in-the-Loop Safeguards

**Concepts**

- Autonomy vs oversight
- Checkpointing and state inspection
- Interrupt and resume patterns

**Exercise**

Insert a human approval gate into your workflow.

[Open in Colab](COLAB_LINK_03)

---

## 4. From Single Agent to Multi-Agent System

**Concepts**

- Supervisor-based architectures
- Role separation
- Delegation and task routing

**Exercise**

Transform a single-agent workflow into a two-agent system.

[Open in Colab](COLAB_LINK_04)

---

## 5. Communication Patterns in MAS

**Concepts**

- Message passing vs shared memory
- Event-driven coordination
- Handoff reliability

**Exercise**

Swap a communication strategy and observe system behavior changes.

[Open in Colab](COLAB_LINK_05)

---

# Day 2 – Production-Ready Systems

## 6. Structured Data and MCP

**Concepts**

- Schema-based prompting
- Pydantic validation
- Model Context Protocol (MCP)

**Exercise**

Turn free-form input into validated structured tool calls.

[Open in Colab](COLAB_LINK_06)

---

## 7. Memory and Context Strategy

**Concepts**

- Episodic vs procedural memory
- Checkpointing
- Context engineering

**Exercise**

Add simple episodic and procedural memory to your agent.

[Open in Colab](COLAB_LINK_07)

---

## 8. Model and Architecture Tradeoffs

**Concepts**

- Planner vs unified agents
- Thinking vs non-thinking modes
- Dense vs MoE models
- KV cache considerations

**Exercise**

Switch planning modes and compare latency and decision quality.

[Open in Colab](COLAB_LINK_08)

---

## 9. Observability and Evaluation

**Concepts**

- Logging state transitions
- Monitoring workflows
- Task-specific evaluation

**Exercise**

Add logging hooks and compare two workflow runs.

[Open in Colab](COLAB_LINK_09)

---

## 10. Security and Guardrails

**Concepts**

- Tool misuse and memory poisoning
- Schema enforcement
- Secure execution patterns

**Exercise**

Add policy checks and validation to an existing workflow.

[Open in Colab](COLAB_LINK_10)


---

## Running the Notebooks

All notebooks are designed for **Google Colab**.

1. Click the Colab link  


---

Design deliberately.  
Deploy responsibly.

