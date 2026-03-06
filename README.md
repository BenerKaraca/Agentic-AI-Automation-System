# Agentic-AI-Automation-System
Multi-Agent AI Assistant (n8n & LangChain)
Welcome to the Vaev project! This is a highly capable, autonomous personal assistant built entirely using n8n. Operating primarily through Telegram, Vaev utilizes LangChain and OpenAI's GPT-4 models to orchestrate multiple specialized AI Agents.

Instead of relying on a single monolithic prompt, this system routes natural language requests to the appropriate "Sub-Agent" tool, executes complex tasks (like managing emails, parsing invoices, or scheduling), asks for human confirmation via interactive Telegram buttons, and integrates seamlessly with Google Workspace and Zapier.

✨ System Architecture & Flow
User Input: The user sends a text message, image, or document via Telegram.

Orchestrator Agent: The "Agentic Part" acts as the brain. It analyzes the user's intent and routes the payload to one of the 5 specialized sub-workflows.

Task Execution: The specific Agent processes the data using OpenAI (vision, document parsing, or text generation) and prepares the action.

Human-in-the-loop (Approval): Before executing destructive or final actions (like appending to a database or posting online), the system sends an interactive message to Telegram ([Yes] / [No]).

Finalization: Upon approval, the data is pushed to endpoints like Google Sheets, Google Calendar, Gmail, or Zapier.

🧠 The Agents
1. 🎛️ Orchestrator Agent (Main Router)
The central nervous system of Vaev. Powered by GPT-4 mini and LangChain memory, it evaluates incoming Telegram messages. It never performs the tasks directly; instead, it intelligently decides whether to trigger the Calendar, Social Media, Gmail, Document, or Image processing tool based on context.

2. 📅 Calendar Agent
Manages schedule and time efficiently.

Retrieve: Understands queries like "Show me this week's program" and fetches relevant events from Google Calendar.

Create: Creates new calendar events with accurate time mapping, default durations, and formatted descriptions.

3. 📱 Social Media Agent
A specialized marketing agent with a defined corporate tone ("Socia").

Image Analysis: Uses GPT-4o Vision to understand uploaded photos and cross-references them with today's Google Calendar events to write highly contextual, natural-sounding captions.

Video Handling & Zapier Integration: When video links are submitted, the agent logs the required metadata and links into Google Sheets. A Zapier automation then detects this new row and handles the actual publishing to social media platforms.

Storage: Updates history documents in Google Drive and logs all generated content.

4. 📧 Gmail Agent
A complete email management tool right inside Telegram.

Retrieve: Can fetch recent unread emails or filter them without needing strict search operators from the user.

Send: Drafts and sends emails automatically based on user prompts.

5. 📄 Document Processing Agent
An intelligent data extraction tool for PDFs, DOCX files, and other documents.

Automatically parses structured data from uploaded documents (like invoices or receipts).

Extracts granular details like Invoice Number, Date, Billing Info, Line Items, and Total Prices.

Waits for user approval on Telegram before appending the extracted JSON data row-by-row into a Google Sheet database.

6. 🖼️ Image Processing Agent
Similar to the Document Agent, but built for visual data.

Uses GPT-4o Vision to extract line items, taxes, and pricing directly from photos of receipts or physical invoices.

Formats the output into structured JSON and logs it into Google Sheets upon user approval.

🛠️ Tech Stack & Integrations
Core Automation: n8n (Node-based Workflow Automation)

AI & LLMs: OpenAI (GPT-4o, GPT-4 mini, GPT-4o Vision), LangChain (Agents, Tools, Memory)

Interface: Telegram Bot API

Workspace & DB: Google Sheets, Google Docs, Google Drive, Gmail API, Google Calendar API

External Integrations: Zapier (for Social Media Video Publishing)

🔒 Security Notice & Source Code
Due to security reasons, sensitive internal data flows, and active API credentials, the raw JSON workflow files for this project are not publicly available in this repository. The system relies on deeply integrated personal and enterprise nodes. If you are a recruiter, developer, or enthusiast interested in seeing how the LangChain agents are configured, or if you'd like a live demonstration of the routing and approval mechanics, please feel free to reach out to me directly! I would be more than happy to walk you through the architecture in a secure environment.

Developed by Bener Karaca
