# ResearchMind · AI Research Agent

ResearchMind is a multi-agent AI system powered by LangChain and Google Gemini. It automates the research process by deploying specialized AI agents to search the web, scrape articles, draft comprehensive reports, and constructively critique the final output. 

You can interact with the system via a beautiful Streamlit Web UI or directly through the Command Line Interface (CLI).
Features
- Multi-Agent Collaboration - Search Agent:** Uses the Tavily API to scour the web for recent and reliable information.
  - Reader Agent: Extracts and cleans deep content from the most relevant URLs.
  - Writer Chain: Synthesizes the gathered research into a structured, professional report (complete with Introduction, Key Findings, Conclusion, and Sources).
  - Critic Chain: Reviews the drafted report, providing a score, strengths, and areas to improve.
- **Dual Interfaces: Comes with a polished Streamlit web application (`app.py`) and a terminal-based script (`pipeline.py`).
- **Exportable Reports:** Download the final Markdown (`.md`) research reports directly from the web UI.

Tech Stack

- **Framework:** [LangChain](https://www.langchain.com/)
- **LLM:** [Google Gemini](https://ai.google.dev/) (`gemini-2.5-flash-lite`)
- **Web Search:** [Tavily API](https://tavily.com/)
- **Web Scraping:** BeautifulSoup & Requests
- **Frontend / UI:** [Streamlit](https://streamlit.io/)

Getting Started

Prerequisites

You will need API keys for the services used by the agents:
1. Google Gemini API Key**
2. Tavily API Key**

Installation

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd Research-Tool
Set up a virtual environment (recommended):

Bash
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
Install dependencies:

Bash
pip install -r req.txt
Configure Environment Variables:
Create a .env file in the root directory and add your API keys:

Code snippet
GOOGLE_API_KEY=your_gemini_api_key_here
TAVILY_API_KEY=your_tavily_api_key_here
Usage
Option 1: Web Interface (Streamlit)
To launch the interactive dashboard, run:

Bash
streamlit run app.py
This will open a browser window where you can input a research topic, watch the agents work through the pipeline in real-time, and download the final drafted report.

Option 2: Command Line Interface
To run the research pipeline directly from your terminal, execute:

Bash
python pipeline.py
You will be prompted to enter a research topic. The terminal will print out the outputs of each step, from search results to the final critic feedback.

Project Structure
app.py: Streamlit frontend application.

pipeline.py: CLI script to run the step-by-step research process in the terminal.

agents.py: Contains the LangChain agent definitions (Search, Reader) and prompt templates/chains (Writer, Critic).

tools.py: Custom LangChain tools for executing web searches (web_search) and HTML scraping (scrape_url).

req.txt: Project dependencies.

.env / .gitignore: Environment variable management and git exclusions.
