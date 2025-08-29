# TDS-BONUSPROJECT-LLMAGENT
LLM Agent GyaanSetu — Browser-Based Multi-Tool Reasoning This project is a proof-of-concept (POC) for building a browser-based LLM agent that can combine natural language reasoning with external tools like search engines, pipelined APIs, and even live JavaScript execution.

Features
✅ Multi-Provider Model Picker

Choose between AI Pipe Proxy API (default), OpenAI GPT, Gemini, Claude, and others.
Dynamic dropdown for switching providers & models.
✅ Reasoning Loop Agent

Takes user input, queries the LLM, and loops with tool calls until the task is done.
Uses OpenAI-style tool/function calls for tool invocation.
✅ Supported Tools

🔎 Google Search Snippets – Fetch relevant web info.
🔗 AI Pipe Proxy API – Flexible AI workflows & pipelines.
⚡ JavaScript Sandbox – Execute JS code securely inside the browser.
✅ Robust UI/UX

Bootstrap-based clean design.
Streaming-style chat window with file upload.
Graceful error handling via bootstrap alerts.
Performance monitor & tool action logging for debugging.
📋 Project Overview
Goal
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

API keys for:

AI Pipe proxy API (recommended)
Optional: OpenAI, Gemini, or other providers.
Setup
Clone this repo:

git clone https://github.com/23f1000805/tds-bonus-project-LLM-Agent.git
cd tds-bonus-project-LLM-Agent
Open index.html in your browser. (No backend server required — everything runs client-side!)

Configure your API key in the Settings Panel inside the app.

🎨 UI & Code Requirements
Model Picker: Dropdown built with bootstrap-llm-provider.
Agent Loop: JavaScript event-driven loop for LLM ↔ Tool calls.
Error UI: All errors shown via bootstrap-alert.
Minimalism First: Codebase is intentionally simple, hackable, and extendable.
📖 Example Conversation
User: Interview me to create a blog post. Agent: Sure! What’s the post about?

User: About IBM. Agent: Let me search for IBM. → calls search("IBM")

Agent: IBM is a global tech company founded in 1911...

User: Next step, please. Agent: Let’s draft an outline for your blog post...

🧪 Deliverable
A browser JS app with:

LLM chat window
Google Search snippets
AI Pipe proxy integration
JS code execution sandbox
Uses OpenAI-style function calling.

Handles errors gracefully.

Easy to extend for more tools.
