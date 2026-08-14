````md
# 🚀 AI Engineer — 3-Month Roadmap

## 🎯 Goal

Become a confident **Intermediate AI Engineer in 3 months** by learning the core AI engineering skills and applying each skill to real problems inside **ProPhone**.

**Time:** 4 hrs/day  
**Learning:** 20%  
**Building:** 80%  
**Approach:** Learn → Build → Integrate → Evaluate → Improve

The goal is **not** to become a ProPhone specialist.

ProPhone is the real-world environment where the AI skills are practiced.

---

# 🧠 MONTH 1 — MACHINE LEARNING + AI DATA

## Learn

- Python for AI
- NumPy
- Pandas
- Data cleaning
- Feature engineering
- Supervised learning
- Classification
- Regression
- Train / validation / test
- Cross-validation
- Overfitting
- Precision / Recall / F1
- ROC-AUC / PR-AUC
- Feature importance
- Model serialization
- FastAPI
- PostgreSQL for ML data

## Build

Create:

`ai-services/lead-intelligence/`

Use ProPhone data:

`Lead + LeadActivity + Campaign + CampaignRecipient`

Build a real ML pipeline:

`PostgreSQL → Dataset → Features → Training → Evaluation → Model → FastAPI → ProPhone`

The model should analyze:

- Lead information
- Lead source
- Current stage
- Activity history
- Email engagement
- Call activity
- Campaign history
- Time since last activity
- Previous outcomes

Predict:

`Conversion Probability`

`Lead Priority`

`Recommended Next Action`

Do not only create a `leadScore`.

The important part is learning how to transform messy business data into useful ML features and evaluate whether the model actually works.

## ProPhone Implementation

Add:

**AI Lead Insights**

Example:

```text
Lead: ABC Towing

Conversion Probability: 81%

Priority: HIGH

Important Signals:
- High email engagement
- Recent activity
- Similar leads converted successfully

Recommended Action:
Call today
````

## Experience You Gain

By the end of Month 1 you should understand:

`Data → Features → Model → Evaluation → Prediction → API → Product`

---

# 🤖 MONTH 2 — LLM ENGINEERING + RAG + AI APPLICATIONS

## Learn

* LLM fundamentals
* Tokens
* Context windows
* Prompt engineering
* System / user messages
* Structured outputs
* JSON schemas
* Function calling
* Tool calling
* Embeddings
* Vector databases
* RAG
* Chunking
* Retrieval
* Reranking
* RAG evaluation
* LLM evaluation
* Streaming
* Token/cost tracking
* Hallucination handling
* Prompt injection basics

Use:

`Python + FastAPI + PostgreSQL + pgvector + LLM API`

## Build

Create:

`ai-services/crm-ai/`

Build a real **ProPhone AI Knowledge Assistant**.

Pipeline:

`ProPhone Data → Chunking → Embeddings → pgvector → Retrieval → LLM → Structured Answer`

The AI should understand:

* Lead history
* Lead notes
* Activities
* Campaign history
* Email history
* Call information
* CRM documentation

Users should be able to ask:

```text
"Why is this lead important?"

"What happened with this lead?"

"Summarize this lead."

"Show me similar leads."

"Why did this lead stop progressing?"

"What should I know before calling this customer?"
```

## Learn Through Implementation

### RAG

Store useful CRM knowledge in `pgvector`.

Learn:

`Embedding → Similarity Search → Retrieval → Context → LLM`

### Structured Output

Instead of returning random text:

```json
{
  "summary": "...",
  "priority": "high",
  "risks": [],
  "recommended_action": "call"
}
```

### Tool Calling

Give the LLM controlled tools such as:

```text
getLead()
getActivities()
getEmailHistory()
getCampaignHistory()
searchSimilarLeads()
```

The model decides which information it needs.

## ProPhone Implementation

Add:

**Ask ProPhone AI**

and:

**AI Lead Summary**

Example:

```text
User:
"Prepare me for this call."

AI:
Customer: ABC Towing

Current Stage: Qualified

Summary:
...

Important History:
...

Previous Communication:
...

Potential Concerns:
...

Recommended Talking Points:
...

Recommended Next Action:
Call today
```

## Experience You Gain

By the end of Month 2 you should understand:

`LLM → Tools → RAG → Retrieval → Structured Output → AI Application`

You should be able to build an LLM application from scratch without depending entirely on an AI framework.

---

# 🧠 MONTH 3 — AI AGENTS + AUTOMATION + PRODUCTION

## Learn

* AI agent architecture
* Agent state
* Tool orchestration
* Multi-step workflows
* Planning
* Memory
* Human-in-the-loop
* Guardrails
* Agent evaluation
* AI security
* Async Python
* Redis
* Background jobs
* Queues
* Docker
* Logging
* Monitoring
* Error handling
* AI cost optimization
* n8n
* Dify
* Production AI architecture

## Build

Create:

`ai-services/sales-copilot/`

Combine Month 1 and Month 2.

Architecture:

```text
Lead
 ↓
ML Intelligence
 ↓
CRM Knowledge
 ↓
LLM
 ↓
Tools
 ↓
Agent
 ↓
Recommendation
 ↓
Human Approval
 ↓
Action
 ↓
Outcome
```

Give the agent controlled tools:

```text
getLead()
getActivities()
getLeadScore()
getEmailHistory()
getCampaignHistory()
generateEmail()
generateCallScript()
recommendNextAction()
createTask()
```

The agent should answer:

**"What should I do with this lead?"**

Example:

```text
🔥 HIGH PRIORITY

Conversion Probability: 82%

Current Stage: CONTACTED

Analysis:
The lead opened the last 2 emails
and clicked the pricing link.

Risk:
No salesperson activity for 4 days.

Recommended Action:
Call today.

Suggested Call Script:
...

Suggested Follow-up Email:
...

[Approve]
[Edit]
[Reject]
```

## Automation

Use **n8n** for real workflows:

```text
New Lead
 ↓
AI Analysis
 ↓
High Priority?
 ↓
Notify Salesperson
```

```text
Email Click
 ↓
AI Re-analysis
 ↓
Update Recommendation
 ↓
Create Sales Task
```

Use **Dify** where it makes sense for rapid AI workflow/prototype development.

Learn why and when to use:

`Custom Python AI Service vs Dify vs n8n`

Do not blindly use automation tools for everything.

## Production Engineering

Make the AI service production-ready:

* Docker
* Environment configuration
* API authentication
* Async processing
* Redis
* Logging
* Error handling
* Retry handling
* Rate limiting
* Cost tracking
* Latency tracking
* AI evaluation
* Model/prompt versioning

## ProPhone Implementation

Add:

**AI Sales Copilot**

The salesperson sees:

```text
Today's AI Sales Plan

🔥 8 High Priority Leads

📞 5 Recommended Calls
✉️ 3 Recommended Follow-ups
⚠️ 2 Leads At Risk

[Generate Today's Plan]
```

Important actions remain human-approved until the system is proven reliable.

## Experience You Gain

By the end of Month 3 you should understand:

`ML + LLM + RAG + Tools + Agents + Automation + APIs + Production`

You should be able to design and build an AI feature from:

`Business Problem → Data → AI Architecture → Model/LLM → Backend → Integration → Evaluation → Production`

---

# 🏆 FINAL 3-MONTH SKILL MAP

```text
MONTH 1
MACHINE LEARNING
        ↓
Data
Features
Models
Evaluation
Prediction
APIs
        ↓
REAL PROPHONE ML FEATURE


MONTH 2
LLM ENGINEERING
        ↓
LLMs
Embeddings
RAG
pgvector
Tools
Structured Output
Evaluation
        ↓
REAL PROPHONE AI ASSISTANT


MONTH 3
AI ENGINEERING
        ↓
Agents
Automation
n8n
Dify
Redis
Async
Production
Evaluation
Security
        ↓
REAL PROPHONE AI SALES COPILOT
```

---

# 🧩 FINAL TECHNICAL SKILLS

## Machine Learning

`Python · NumPy · Pandas · Scikit-learn · Feature Engineering · Model Evaluation`

## Deep Learning

`PyTorch · Neural Networks · Embeddings · Transformers`

## LLM Engineering

`LLMs · Prompting · Structured Output · Function Calling · Tool Calling`

## RAG

`Embeddings · pgvector · Chunking · Retrieval · Reranking · RAG Evaluation`

## AI Agents

`Agents · State · Tools · Memory · Workflows · Guardrails · Human-in-the-Loop`

## Backend

`FastAPI · PostgreSQL · Redis · Async Python · REST APIs`

## Production

`Docker · Logging · Monitoring · Cost Tracking · Rate Limiting · Security`

## Automation

`n8n · Dify · Webhooks · Event-Driven Workflows`

## Existing Engineering

`Node.js · React · Git · System Design`

---

# ⏱️ DAILY 4-HOUR SYSTEM

```text
1 Hour
Learn the concept

3 Hours
Implement it in ProPhone

Every feature:
Learn
 ↓
Build locally
 ↓
Test
 ↓
Integrate with ProPhone
 ↓
Evaluate
 ↓
Improve
 ↓
Document
```

Do not spend the entire month watching courses.

Do not let AI generate the entire project without understanding it.

Use AI coding tools to move faster, but you must understand:

`Why it works`

`How it works`

`What can fail`

`How to evaluate it`

`How to improve it`

---

# 🎯 AFTER 3 MONTHS

You should be able to confidently build:

```text
ML Models
LLM Applications
RAG Systems
AI APIs
AI Agents
Tool-Calling Systems
AI Automation
Production AI Services
```

And you should have one strong real-world portfolio story:

> **I built and integrated an AI system into a production CRM that uses machine learning, LLMs, RAG, tool calling, agents, and workflow automation to analyze leads, understand CRM data, recommend sales actions, and assist salespeople.**

That is the target.

**Not simply "I learned AI."**

**You become an engineer who can build and ship AI systems.**

```
```
