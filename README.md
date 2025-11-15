🚀 AI Browser Agent – Web Automation on Autopilot
Build Intelligent Browser Agents Using Browser-Use + Gemini + Docker + Web-UI

This project demonstrates how to build AI-powered browser automation agents that can browse websites, search Google, fill forms, extract data, and complete multi-step workflows—entirely through natural language.

Unlike traditional Selenium scripts that break when websites change, AI Browser Agents use:

LLM reasoning (Google Gemini)

DOM understanding

Computer vision

Autonomous planning

to complete tasks the way a human would.
🌟 Features

✔ AI-powered browser automation
✔ Natural-language task execution
✔ Google Gemini integration
✔ Web scraping
✔ Form filling
✔ Multi-step research workflows
✔ Full execution history (JSON)
✔ Automatic screenshots + session replay
✔ Docker-based Web UI
✔ Zero manual selectors (no XPath, no CSS selectors required)

🧠 How It Works

AI Browser Agents follow a perceive → reason → act loop:

👀 Perception

The agent “sees” the page via DOM + screenshots.

🧠 Reasoning

Gemini decides what to click, type, search, or extract.

✋ Actuation

Playwright performs real clicks, typing, scrolling—like a human.

This makes the automation robust and self-healing.

📦 Installation

Install Playwright + Browser-Use:

pip install playwright && playwright install chromium --with-deps
pip install browser-use


Clone the project:

git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

🔑 Environment Setup

Create a .env file:

touch .env


Add your Gemini API key:

GEMINI_API_KEY=your_key_here

🧪 Examples
1️⃣ Basic Search Automation
import asyncio
from dotenv import load_dotenv
from browser_use import Agent, ChatGoogleGenerativeAI

load_dotenv()

async def main():
    llm = ChatGoogleGenerativeAI(model="gemini-pro")
    task = "Search Google for 'what is browser automation' and show top 3 results."
    agent = Agent(task=task, llm=llm)
    await agent.run()

asyncio.run(main())

2️⃣ Form Filling Example
import asyncio
from dotenv import load_dotenv
from browser_use import Agent, ChatGoogleGenerativeAI

load_dotenv()

async def main():
    llm = ChatGoogleGenerativeAI(model="gemini-pro")
    task = """
    Go to https://httpbin.org/forms/post and fill:
    - Name: John Doe
    - Phone: 555-123-4567
    - Email: john@example.com
    - Size: Medium
    - Topping: cheese
    Submit and return response.
    """
    agent = Agent(task=task, llm=llm)
    await agent.run()

asyncio.run(main())

3️⃣ Data Extraction from Website
import asyncio
from dotenv import load_dotenv
from browser_use import Agent, ChatGoogleGenerativeAI

load_dotenv()

async def main():
    llm = ChatGoogleGenerativeAI(model="gemini-pro")
    task = """
    Go to https://quotes.toscrape.com/
    Extract first 5 quotes, authors, and tags.
    """
    agent = Agent(task=task, llm=llm)
    await agent.run()

asyncio.run(main())

4️⃣ Multi-Step Research Agent
import asyncio
from dotenv import load_dotenv
from browser_use import Agent, ChatGoogleGenerativeAI

load_dotenv()

async def main():
    llm = ChatGoogleGenerativeAI(model="gemini-pro")
    task = """
    Search the best Python scraping libraries 2025.
    Open a reliable article.
    Extract top 3 libraries.
    Visit each library's official site/GitHub.
    Extract:
      - Name
      - Description
      - Features
      - GitHub stars (if available)
    Return comparison summary.
    """
    agent = Agent(task=task, llm=llm)
    await agent.run()

asyncio.run(main())

🕹 Using the Web UI (Recommended)
Clone Web-UI:
git clone https://github.com/browser-use/web-ui.git
cd web-ui

Copy environment file:
cp .env.example .env


Add your Gemini key.

Build Docker Image:
docker build -t browser-use-webui .

Run the Container:
docker run -d --rm \
  -p 7788:7788 \
  -p 6080:6080 \
  --env-file .env \
  --name browser-use-container \
  browser-use-webui


Open the Web UI:

👉 http://localhost:7788

Paste any natural-language task and run the agent.

📁 Output Features

history = await agent.run()

You get:

Visited URLs

Screenshots

Extracted text

Actions list

Error logs

Final result

Full JSON history

Screen recording (GIF) in Web-UI

Perfect for debugging or showcasing.

🎥 GIF Demo (Add Your GIF Here)
<Insert your session recording GIF>

📄 Project Structure
ai-browser-agent/
│── examples/
│──   ├── basic_search.py
│──   ├── form_fill.py
│──   ├── data_extract.py
│──   └── multi_step_research.py
│── README.md
│── .env
│── requirements.txt
│── docker/
│── web-ui/

🌐 Use Cases

✔ Job application automation
✔ Scraping multiple sites
✔ Lead generation
✔ Form submissions
✔ Research workflows
✔ Competitor analysis
✔ eCommerce monitoring
✔ Flight + hotel search automation
