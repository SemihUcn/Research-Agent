# Deep Research Agent

Deep Research Agent is an **agentic AI research system** built using the OpenAI Agents framework.
It performs **automated deep research on any topic**, gathers information from the web, analyzes findings, generates a comprehensive report, and optionally sends the report via email.

The system demonstrates how to build **multi-tool AI agents**, orchestrate research workflows, and stream progress updates to a user interface.

---

# Features

* Automated research workflow
* Multi-agent tool orchestration
* Web search and information summarization
* Structured research planning
* Detailed report generation (1000+ words)
* Email delivery of generated reports
* Real-time progress streaming
* Simple Gradio web interface

---

# System Architecture

The project is built around a **main research agent** that coordinates several specialized tools.

Workflow:

1. **Research Planning**
   The system generates a list of search queries to explore the topic.

2. **Web Research**
   The agent performs web searches and summarizes results.

3. **Analysis**
   The collected research summaries are analyzed and organized.

4. **Report Writing**
   A structured markdown report is generated.

5. **Email Delivery**
   The final report can be converted to HTML and sent via email.

The research agent coordinates these steps automatically. 

---

# Project Structure

```
deep-research-agent/
│
├── agent.py        # Main research agent logic
├── app.py          # Gradio user interface
├── hook.py         # Run hooks for progress updates
│
├── tools/
│   ├── plan.py     # Research planning agent
│   ├── search.py   # Web search agent
│   ├── write.py    # Report writing agent
│   ├── email.py    # Email sending agent
│   └── __init__.py
│
├── util.py         # Logging configuration
├── __main__.py     # Package entry point
└── README.md
```

The Gradio interface allows users to enter a research query and receive a generated report. 

---

# Research Workflow

The research process follows this pipeline:

```
User Query
    │
    ▼
Search Planning Tool
    │
    ▼
Web Search Tool
    │
    ▼
Research Analysis
    │
    ▼
Report Generation Tool
    │
    ▼
Email Delivery Tool
```

Progress updates are streamed to the UI using **Run Hooks** during tool execution. 

---

# Installation

This project uses **Python 3.10+** and the **OpenAI Agents framework**.

Install dependencies:

```bash
pip install uv
uv add python-dotenv
uv add "openai>=1.55.0b0" "openai-agents>=0.0.23" --pre
uv add gradio sendgrid pydantic
```

---

# Environment Variables

Create a `.env` file and add the following:

```
OPENAI_API_KEY=your_openai_api_key
SENDGRID_API_KEY=your_sendgrid_api_key
```

---

# Running the Application

Start the system with:

```bash
uv run python -m deep_research_agent
```

or

```bash
python -m deep_research_agent
```

This will launch a **Gradio interface in your browser**.

---

# Usage

1. Enter a topic in the research box.
2. Click **Run**.
3. The agent will:

   * plan research
   * perform web searches
   * analyze results
   * generate a report
4. The final report will appear in the interface.

---

# Example Query

```
Impact of Artificial Intelligence on Global Labor Markets
```

The system will produce:

* A structured report
* A short summary
* Suggested follow-up research questions

---

# Technologies Used

* OpenAI Agents SDK
* GPT-5.x models
* Gradio
* SendGrid
* Python asyncio
* Pydantic



Developed as an example of an **agentic AI research system** using OpenAI Agents.
