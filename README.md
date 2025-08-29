https://tds-bonusproject-llmagent.onrender.com/
**LLM Agent GyaanSetu — Browser-Based Multi-Tool Reasoning**
This project is a proof-of-concept (POC) for building a browser-based LLM agent that can combine natural language reasoning with external tools like search engines, pipelined APIs, and even live JavaScript execution.

Modern LLM agents aren’t limited to text — they dynamically integrate multiple tools and loop until tasks are solved. This app demonstrates that idea with a minimal, hackable UI + JavaScript agent core.
____________________________________________________________
🚀** Features**
✅ Multi-Provider Model Picker
____________________________________________________________
Choose between AI Pipe Proxy API (default), OpenAI GPT, Gemini, Claude, and others.
Dynamic dropdown for switching providers & models.
✅ Reasoning Loop Agent
____________________________________________________________
Takes user input, queries the LLM, and loops with tool calls until the task is done.
Uses OpenAI-style tool/function calls for tool invocation.
✅ Supported Tools
___________________________________________________________
🔎 **Google Search Snippets – Fetch relevant web info.**
🔗 AI Pipe Proxy API – Flexible AI workflows & pipelines.
⚡ JavaScript Sandbox – Execute JS code securely inside the browser.
✅ Robust UI/UX

Bootstrap-based clean design.
Streaming-style chat window with file upload.
Graceful error handling via bootstrap alerts.
Performance monitor & tool action logging for debugging.
________________________________________________________
📋** Project Overview**
**Goal**
Build a minimal JavaScript-based agent that can:

Accept user input in the browser.
Query an LLM for reasoning.
Dynamically trigger tool calls (search, AI workflows, code execution).
Loop until the LLM decides no more tools are needed.
Agent Logic (Conceptual)
def loop(llm):
    msg = [user_input()]
    while True:
        output, tool_calls = llm(msg, tools)
        print("Agent: ", output)
        if tool_calls:
            msg += [handle_tool_call(tc) for tc in tool_calls]
        else:
            msg.append(user_input())
JavaScript Implementation
This POC reimplements the above loop in browser JavaScript, connected to provider APIs.

🛠️ Getting Started
Prerequisites
A modern browser (Chrome/Edge/Firefox).

**API keys for:**

AI Pipe proxy API (recommended)
Optional: OpenAI, Gemini, or other providers.

Open index.html in your browser. (No backend server required — everything runs client-side!)

Configure your API key in the Settings Panel inside the app.

🎨 **UI & Code Requirements**
Model Picker: Dropdown built with bootstrap-llm-provider.
Agent Loop: JavaScript event-driven loop for LLM ↔ Tool calls.
Error UI: All errors shown via bootstrap-alert.
Minimalism First: Codebase is intentionally simple, hackable, and extendable.
📖 **Example Conversation**
User: Interview me to create a blog post. Agent: Sure! What’s the post about?

User: About IBM. Agent: Let me search for IBM. → calls search("IBM")

Agent: IBM is a global tech company founded in 1911...

User: Next step, please. Agent: Let’s draft an outline for your blog post...
_____________________________________________________________
🧪 **Deliverable**
A browser JS app with:

LLM chat window
Google Search snippets
AI Pipe proxy integration
JS code execution sandbox
Uses OpenAI-style function calling.

Handles errors gracefully.

Easy to extend for more tools.
__________________________________________________________
**Project Structure**
├── **index.html**   # Frontend UI (chat + settings)
├── **agent.js**     # Core agent loop, providers, and tools
├── **styles.css **    # css file
└── **README.md **   # Documentation (this file)
__________________________________________________________
**Acknowledgements**
AI Pipe for proxy API workflows
OpenAI/Anthropic/Google for LLM providers
Bootstrap for UI components
🔮 Next Steps

Add conversation persistence with IndexedDB/localStorage.
Enable streaming token-by-token responses.
Expand tools: file parsing, charting, SQL, etc.
