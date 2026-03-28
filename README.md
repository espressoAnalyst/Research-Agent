# 🔍 Research Agent

An AI-powered **Research Agent** that autonomously explores a given topic and generates a well-structured report in seconds. Built using **LangChain** and **Groq (LLaMA 3)**, the system gathers information from live web sources and Wikipedia, then converts it into a clean Markdown report.

This project demonstrates automated research on topics like **Lithium Batteries**, combining real-time insights with foundational knowledge.

---

## 🌟 Features

- **Autonomous Reasoning Agent**  
  Uses a ReAct-style architecture to think, act, and refine results in an intelligent loop.

- **Multiple Data Sources**
  - 🌐 *Tavily Search*: Retrieves latest updates, trends, and real-world insights  
  - 📚 *Wikipedia API*: Provides reliable background and core concepts  

- **Optimized Token Usage**  
  Smart truncation ensures responses stay within API limits while preserving useful data.

- **Two-Step Processing Pipeline**
  1. **Research Phase** – Collects raw, unstructured information  
  2. **Synthesis Phase** – Converts data into a structured report  

- **Execution Transparency**  
  Logs all actions, queries, and tool calls for better debugging and understanding.

---

## 🛠️ Tech Stack

- Python 3.12  
- LangChain (Core + Community)  
- Groq API (`llama-3.1-8b-instant`)  
- Tavily Search API  
- Wikipedia API  
- Pytest (for testing and performance validation)  

---

## ⚙️ Workflow

When the agent is triggered, it follows these steps:

1. **Understanding the Query (`🧠 thinking...`)**  
   Interprets the topic (e.g., Lithium Batteries) and identifies required information.

2. **Data Collection (`🔍 searching...` / `📚 extracting...`)**  
   Generates queries and fetches results from web and Wikipedia sources.

3. **Iterative Refinement**  
   Repeats the process until enough relevant information is gathered.

4. **Processing Insights (`💭 analyzing...`)**  
   Organizes and filters collected data.

5. **Report Generation (`📝 generating report...`)**  
   Produces a structured Markdown report.

---

![Research Agent Workflow](./image-1.png)

---

## 📝 Output (`research_report.md`)

The generated report includes:

1. **Title & Topic Details**  
2. **Introduction**  
3. **Key Insights**  
4. **Challenges**  
5. **Future Scope**  
6. **Conclusion**  
7. **References (with source links)**  

---

## 🚀 Getting Started

### Prerequisites
1. Clone the repository.
2. Create a `.env` file at the root containing:
   ```env
   TAVILY_API_KEY="your-tavily-key"
   GROQ_API_KEY="your-groq-key"
   ```
3. Initialize the virtual environment and install dependencies:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

### Running the Agent
Trigger the agent using the main execution pipeline module. You can pass any topic you'd like:
```bash
python -m src.main "Artificial Intelligence and Quantum Computing"
```

### Testing & Validation
The project includes a full integration testing suite enforcing tool outputs, LLM formatting constraints, and the strict **< 60-second end-to-end latency limit**:
```bash
pytest tests/ -v -s
```
