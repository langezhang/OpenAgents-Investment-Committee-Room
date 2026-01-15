<img width="336" height="35" alt="image" src="https://github.com/user-attachments/assets/521f984a-f14b-4975-8545-25840d81ba73" /># Investment Committee Room

A multi-agent investment committee simulation featuring AI agents with distinct financial roles and analytical perspectives.

## 🧠 Overview

This demo showcases a collaborative financial decision-making simulation using OpenAgents. Three AI agents — Analyst, Portfolio Manager, and Risk Manager — coordinate via a shared messaging workspace to analyze investment opportunities. Each agent embodies a unique perspective, strategy, and communication style.

This setup demonstrates persona-driven collaboration on complex investment decisions using real-time structured messaging.

## 👥 Agents

| Agent               | Role                | Persona Highlights |
|---------------------|---------------------|---------------------|
| `analyst`           | Analyst             | Data-obsessed, KPI-driven, challenges assumptions with numbers |
| `portfolio manager` | Portfolio Manager   | Returns-focused allocator, prioritizes disciplined capital deployment |
| `risk manager`      | Risk Manager        | Scenario-first thinker, protects downside with pragmatic assessments |

## 💡 Features Demonstrated

- Multi-agent financial collaboration in real-time
- Role-specific communication behavior and tone
- Financial modeling critique, risk scenarios, and portfolio logic
- Messaging mod (`openagents.mods.workspace.messaging`) powering shared discussions
- Strict persona rules and response limits
- Agent-to-human messaging only (agents ignore messages from each other)

## ⚙️ Quick Start

### 1. Start the Network

```bash
conda activate openagents
openagents network start network.yaml
```
### 2. Launch the Agents
In separate terminals:
```bash
openagents agent start agents/analyst.yaml
openagents agent start agents/portfolio_manager.yaml
openagents agent start agents/risk_manager.yaml
```
### 3. Connect via Studio or CLI
Using Studio:
```bash
openagents studio -s
# Connect to localhost:8700
```

### 4. Start the Discussion
Post a human message to the channel (e.g., investment-room):

"What do we think of investing in a Series B SaaS company growing 3x YoY but with negative gross margins?"
Watch the Analyst lead with data analysis, Portfolio Manager assess position fit, and Risk Manager evaluate downside. 🚀

## 📊 Example Prompts
- “They’re growing but burning too much—how fragile is the runway?”
- “This exposure seems concentrated. What’s our sector weight post-investment?”
- “If CAC rises 25%, what’s the IRR drop based on the model?”
- “Does this fit our diversification goals across the rest of the book?”
## 🔧 Configuration
- Network Port: 8700 (gRPC)
- Transport: gRPC messaging
- Messaging Mod: openagents.mods.workspace.messaging
- All agents configured to react to all messages sent by a human
- Agent logic defined using CollaboratorAgent with DeepSeek models
## 📌 Rules and Constraints
- ⏱ Messages are capped under 50 words
- 💬 Agents use send_channel_message only (no reply)
- 🔒 No response to other agent messages; only humans are allowed interlocutors
- 🧠 Each agent immediately calls the finish tool when the sender is another agent
## 🧪 Use Cases
This demo is useful for simulating:

- Investment committee meetings with structured debates
- AI agents roleplaying distinct finance decision personas
- Evaluating tradeoffs, assumptions, and risks on startup or fund investments
- Teaching structured decision-making in finance contexts
