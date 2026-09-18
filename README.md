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

## The Business Problem

Retail and footwear operations depend on coordination across four functions that rarely talk to each other in real time: demand forecasting, supplier management, inventory allocation, and production/distribution flow. In most mid-size retail organizations, this coordination happens manually — through spreadsheets, email threads, and whoever happens to answer a Slack message first. That creates concrete, costly problems:

- **Slow reaction to disruptions.** When a supplier pushes back a shipment or a demand forecast shifts, someone has to notice it, figure out who else it affects (inventory? production flow? other suppliers?), and manually loop them in. That lag translates directly into stockouts, excess inventory, or missed sales windows.
- **Fragmented, inconsistent answers.** Ask the inventory team and the supply chain team the same operational question and you may get two different answers, because each is working from its own view of the data with no shared source of truth.
- **No accessible entry point for non-technical stakeholders.** A store manager or business analyst who wants to know "what does this forecast change mean for us?" has no way to ask that directly — they have to know which spreadsheet to open or which specialist to email, and then wait.
- **Reactive instead of proactive operations.** Without a system watching for cross-functional impact, issues typically surface only after they've already caused a problem (a stockout, a missed shipment) rather than being flagged the moment the triggering event occurs.

The business cost of this isn't abstract: it shows up as lost sales from stockouts, working capital tied up in excess inventory, and slower decision cycles that compound during periods of volatility (holiday demand spikes, supplier disruptions, etc.).

**This project prototypes a different operating model:** instead of routing questions to people, route them to a coordinated team of AI agents — each grounded in the real data of one operational domain — that can answer instantly, reason across domains when needed, and proactively escalate what matters. It replaces "who do I ask?" with "just ask."
