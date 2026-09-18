# SmartShoe Operations Agent — Multi-Agent AI for Supply Chain Coordination

A generative multi-agent AI system, built on [StackAI](https://www.stackai.com/), that gives **SmartShoe** — a synthetic retail/footwear company used as the business case — a single conversational interface to its supply chain, inventory, and operations data. Instead of stakeholders chasing down five different systems or teams to answer one operational question, they ask a chatbot.

**Try it live:** [SmartShoe Operations Chatbot](https://www.stackai.com/chat/69151ac5bef1a6ee72a6aba6-41ptbJ3YNgVYWhJ4NR0toG)

## The Business Problem

Retail and footwear operations sit at the intersection of demand forecasting, supplier management, inventory allocation, and production flow — domains that are usually owned by different teams, tracked in different spreadsheets, and reconciled manually. That fragmentation creates:

- **Slow response to disruptions** — a supplier delay or a forecast swing has to be manually routed to the right person before anyone can act on it.
- **Siloed knowledge** — each function (inventory, supply chain, demand signals) holds its own data with no shared view of how a change in one area ripples into the others.
- **No single point of contact** — a non-technical stakeholder can't just "ask" the business a question; they have to know who owns which spreadsheet.

This project prototypes a fix: a coordinated team of AI agents, each an expert in one operational domain, that can be queried like a single knowledgeable colleague.

## How It Works

A user message (e.g. *"Our main supplier just pushed back a shipment by two weeks — what's the impact?"*) is picked up by a routing agent, fanned out to whichever specialist agents are relevant, synthesized into one coherent answer, and returned as a chat response (and, where warranted, an email alert to stakeholders).

```mermaid
flowchart LR
    U[User Message] --> R[SmartShoe Coordination<br/>Router]
    R --> A1[Signal Stabilizer]
    R --> A2[Supply Chain Coordinator]
    R --> A3[Inventory Manager]
    R --> A4[Flow Equalizer]
    A1 --> O[Operations Orchestrator]
    A2 --> O
    A3 --> O
    A4 --> O
    O --> H[Information Hub<br/>Central Intelligence]
    O --> E[Email Alert<br/>Gmail]
    H --> OUT[Chat Response to User]
    E --> OUT
