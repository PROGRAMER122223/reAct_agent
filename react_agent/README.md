# 🧑‍💼 Customer Service Agent (LangGraph + LangChain Tools)

This project demonstrates how to build a **customer service agent** using [LangGraph](https://python.langchain.com/docs/langgraph) and [LangChain tools](https://python.langchain.com/docs/modules/tools).  
The agent can:
- Retrieve customer details by email
- Fetch all orders placed by a customer
- Answer user queries by invoking the appropriate tool

---

## 📂 Project Structure

- `utils.py` → contains `get_llm()` which initializes the LLM (e.g., VertexAI, OpenAI, etc.)
- `customers` → dictionary of customer records
- `orders` → dictionary of order records
- `get_customer` → tool to fetch customer details
- `get_orders_by_customer` → tool to fetch customer orders
- `customer_service_agent` → React-style agent that uses the tools

---
##  Install dependencies
uv add langchain langgraph
uv add "langchain[google-vertexai]"
uv pip install pyppeteer

##  Agent Definition
The agent uses the ReAct paradigm:- Decides which tool to call based on the user’s query.
- Calls the tool.
- Returns a natural language answer to the user.

📌 Notes- Ensure your customers and orders dictionaries are defined before running the agent.
- Keep sensitive data (like API keys) in a .env file and add .env to .gitignore.
- This example uses create_react_agent from langgraph.prebuilt.

