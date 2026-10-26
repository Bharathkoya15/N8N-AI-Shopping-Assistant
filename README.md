# 🛍️ AI Shopping & Styling Assistant on Telegram (n8n Workflow)

It is an AI-powered Telegram bot built with **n8n**. She acts as a personal fashion stylist and live Amazon India shopping assistant—offering tailored outfit recommendations and scraping real-time product data directly inside Telegram.

## ✨ Features

* **Live Amazon India Product Search:** Extracts user search queries (e.g., *"white sneakers under 3000"*), dynamically constructs Amazon.in search URLs, and fetches live product listings via ScraperAPI.
* **Clean Product Cards:** Parses HTML search results (`div.s-search-results`) to return the top 5 products complete with product name, price (₹), rating, and direct view links.
* **Interactive Styling Consultant:** Asks clarifying questions about occasion, preferred style (traditional, western, fusion), color, and weather before delivering complete outfit combinations (top, bottom, footwear, accessories, and styling hacks).

## 🛠️ Tech Stack & Nodes

* **n8n** (Workflow Automation)
* **Telegram Trigger & Send Text Message Nodes** (User interface)
* **n8n AI Agent (LangChain)** (Intent routing & conversation management)
* **Google Gemini Chat Model** (`models/gemini-3.1-flash-lite`)
* **HTTP Request Tool + ScraperAPI** (Live HTML scraping & CSS selector filtering)

## 🚀 Setup Instructions

1. **Import the Workflow:**
   * Download `Telegram Part 1.json` and import it directly into your n8n workspace.
2. **Configure Telegram Credentials:**
   * Create a bot via `@BotFather` on Telegram to get your API token.
   * Add your credentials to both the **Telegram Trigger** and **Send a text message** nodes[cite: 1].
3. **Configure Google Gemini:**
   * Add your Google Gemini API key to the **Google Gemini Chat Model** node[cite: 1].
4. **Add Your ScraperAPI Key:**
   * Open the **HTTP Request** tool node[cite: 1].
   * Under **Query Parameters**, paste your ScraperAPI key into the `api_key` value field[cite: 1].
5. **Activate:**
   * Toggle the workflow to **Active** and send a message to your Telegram bot![cite: 1]

## 💬 Example Prompts

* **Product Search:** *"Show me running shoes under 2000"* or *"I want sneakers under ₹3000"*[cite: 1]
* **Styling Advice:** *"How to style a blue kurti?"* or *"Outfit ideas for a wedding"*[cite: 1]
