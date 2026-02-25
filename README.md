# DentAgent-AI
Agentic dental appointment system with LangGraph orchestration, human-in-the-loop governance, and dual UI/CLI interfaces. Designed to intelligently coordinate patient requests, reviewer oversight, and clinical safety workflows.

Instead of behaving like a typical chatbot, every patient request (cancel, reschedule, or preparation instructions) moves through a clearly designed decision graph. The system validates patient identity, checks appointment ownership, detects emergency risk, handles slot availability, requires confirmation, generates a draft response, and pauses for human review before finalizing the outcome.

The project was designed with a systems-thinking mindset. Each step updates the system’s state, and routing decisions determine what happens next. Terminal outcomes (READY, NEED_INFO, ESCALATE, FAILED) are explicitly defined, making the workflow predictable and traceable rather than reactive or ad-hoc.

Safety and governance are built into the architecture. Emergency text triggers structured escalation, and no final response is sent without passing through a human-in-the-loop approval layer. Middleware is used to control retry behavior and execution flow.

The system runs through both:

A structured Streamlit interface (Patient and Reviewer panels)

A CLI mode that executes the same workflow end-to-end with full trace visibility

This project focuses on designing a reliable, transparent AI workflow system — not just generating responses, but controlling how decisions are made and finalized.

🔎 What This Project Emphasizes

Explicit state transitions and routing logic

Human-in-the-loop governance before final output

Safety-aware escalation handling

Transparent execution tracing for reproducibility
