# AI Engineer — 3-Month Roadmap

A hands-on plan to become a confident **intermediate AI engineer in 3 months**, by learning core AI engineering skills and applying every one of them to real features inside **ProPhone**.

| | |
|---|---|
| **Time commitment** | 4 hrs/day |
| **Split** | 20% learning · 80% building |
| **Method** | Learn → Build → Integrate → Evaluate → Improve |
| **Practice ground** | ProPhone (real CRM, real data) |

> The goal is **not** to become a ProPhone specialist. ProPhone is simply the real-world environment where every AI skill gets practiced on live data and real product decisions.

## Table of Contents

- [Month 1 — Machine Learning + AI Data](#month-1--machine-learning--ai-data)
- [Month 2 — LLM Engineering + RAG + AI Applications](#month-2--llm-engineering--rag--ai-applications)
- [Month 3 — AI Agents + Automation + Production](#month-3--ai-agents--automation--production)
- [Final 3-Month Skill Map](#final-3-month-skill-map)
- [Final Technical Skills](#final-technical-skills)
- [Daily 4-Hour System](#daily-4-hour-system)
- [After 3 Months](#after-3-months)

---

## Month 1 — Machine Learning + AI Data

### Learn
- Python for AI, NumPy, Pandas, data cleaning, feature engineering
- Supervised learning — classification & regression
- Train / validation / test splits, cross-validation, overfitting
- Precision, recall, F1, ROC-AUC, PR-AUC
- Feature importance and model serialization
- FastAPI and PostgreSQL for ML data

### Build

Create `ai-services/lead-intelligence/` using real ProPhone data: **Lead + LeadActivity + Campaign + CampaignRecipient**.

```
PostgreSQL → Dataset → Features → Training → Evaluation → Model → FastAPI → ProPhone
```

The model should analyze:
- Lead information, lead source, current stage
- Activity history, email engagement, call activity
- Campaign history and time since last activity
- Previous outcomes

**Predict:**
- Conversion Probability
- Lead Priority
- Recommended Next Action

Don't stop at a single `leadScore` — the real goal is learning how to turn messy business data into useful ML features and prove the model actually works.

### ProPhone Implementation — AI Lead Insights

```
Lead: ABC Towing

Conversion Probability: 81%
Priority: HIGH

Important Signals:
- High email engagement
- Recent activity
- Similar leads converted successfully

Recommended Action: Call today
```

### Experience Gained

```
Data → Features → Model → Evaluation → Prediction → API → Product
```

---

## Month 2 — LLM Engineering + RAG + AI Applications

### Learn
- LLM fundamentals — tokens, context windows, prompt engineering
- System / user messages, structured outputs, JSON schemas
- Function calling and tool calling
- Embeddings, vector databases, and RAG
- Chunking, retrieval, reranking, RAG & LLM evaluation
- Streaming, token/cost tracking, hallucination handling, prompt injection basics

**Stack:** Python + FastAPI + PostgreSQL + pgvector + LLM API

### Build

Create `ai-services/crm-ai/` — a real **ProPhone AI Knowledge Assistant**.

```
ProPhone Data → Chunking → Embeddings → pgvector → Retrieval → LLM → Structured Answer
```

The AI should understand:
- Lead history, notes, and activities
- Campaign and email history, call information
- CRM documentation

Users should be able to ask:
- "Why is this lead important?"
- "What happened with this lead?"
- "Summarize this lead."
- "Show me similar leads."
- "Why did this lead stop progressing?"
- "What should I know before calling this customer?"

### Learn Through Implementation

**RAG** — store useful CRM knowledge in pgvector:

```
Embedding → Similarity Search → Retrieval → Context → LLM
```

**Structured Output** — instead of free-form text, return structured JSON:

```json
{
  "summary": "...",
  "priority": "high",
  "risks": [],
  "recommended_action": "call"
}
```

**Tool Calling** — give the LLM controlled tools; the model decides what it needs:

```
getLead()
getActivities()
getEmailHistory()
getCampaignHistory()
searchSimilarLeads()
```

### ProPhone Implementation — Ask ProPhone AI / AI Lead Summary

```
User: "Prepare me for this call."

AI:
Customer: ABC Towing
Current Stage: Qualified

Summary: ...
Important History: ...
Previous Communication: ...
Potential Concerns: ...
Recommended Talking Points: ...

Recommended Next Action: Call today
```

### Experience Gained

```
LLM → Tools → RAG → Retrieval → Structured Output → AI Application
```

By the end of Month 2 you should be able to build an LLM application from scratch without depending entirely on a framework.

---

## Month 3 — AI Agents + Automation + Production

### Learn
- Agent architecture — state, tool orchestration, multi-step workflows, planning, memory
- Human-in-the-loop, guardrails, agent evaluation, AI security
- Async Python, Redis, background jobs, queues, Docker
- Logging, monitoring, error handling, AI cost optimization
- n8n, Dify, and production AI architecture

### Build

Create `ai-services/sales-copilot/`, combining Month 1 and Month 2 into one system.

```
Lead
 → ML Intelligence
 → CRM Knowledge
 → LLM
 → Tools
 → Agent
 → Recommendation
 → Human Approval
 → Action
 → Outcome
```

Give the agent controlled tools:

```
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

The agent should answer: **"What should I do with this lead?"**

```
🔥 HIGH PRIORITY

Conversion Probability: 82%
Current Stage: CONTACTED

Analysis:
The lead opened the last 2 emails and clicked the pricing link.

Risk:
No salesperson activity for 4 days.

Recommended Action: Call today.
Suggested Call Script: ...
Suggested Follow-up Email: ...

[Approve]  [Edit]  [Reject]
```

### Automation

Use **n8n** for real workflows:

```
New Lead → AI Analysis → High Priority? → Notify Salesperson
```

```
Email Click → AI Re-analysis → Update Recommendation → Create Sales Task
```

Use **Dify** where it speeds up rapid AI workflow prototyping. Learn *why and when* to reach for a custom Python AI service vs. Dify vs. n8n — don't default to automation tools for everything.

### Production Engineering

- Docker & environment configuration
- API authentication
- Async processing & Redis
- Logging, error handling, retry handling, rate limiting
- Cost tracking, latency tracking, AI evaluation, model/prompt versioning

### ProPhone Implementation — AI Sales Copilot

```
Today's AI Sales Plan

🔥 8 High Priority Leads
📞 5 Recommended Calls
✉️ 3 Recommended Follow-ups
⚠️ 2 Leads At Risk

[Generate Today's Plan]
```

Important actions remain human-approved until the system is proven reliable.

### Experience Gained

```
ML + LLM + RAG + Tools + Agents + Automation + APIs + Production
```

---

## Final 3-Month Skill Map

| Month 1 | Month 2 | Month 3 |
|---|---|---|
| **Machine Learning** | **LLM Engineering** | **AI Engineering** |
| Data · Features · Models · Evaluation · Prediction · APIs | LLMs · Embeddings · RAG · pgvector · Tools · Structured Output | Agents · Automation · n8n · Dify · Redis · Async · Production |
| → Real ProPhone ML Feature | → Real ProPhone AI Assistant | → Real ProPhone AI Sales Copilot |

---

## Final Technical Skills

| Category | Skills |
|---|---|
| **Machine Learning** | Python · NumPy · Pandas · Scikit-learn · Feature Engineering · Model Evaluation |
| **Deep Learning** | PyTorch · Neural Networks · Embeddings · Transformers |
| **LLM Engineering** | LLMs · Prompting · Structured Output · Function Calling · Tool Calling |
| **RAG** | Embeddings · pgvector · Chunking · Retrieval · Reranking · RAG Evaluation |
| **AI Agents** | Agents · State · Tools · Memory · Workflows · Guardrails · Human-in-the-Loop |
| **Backend** | FastAPI · PostgreSQL · Redis · Async Python · REST APIs |
| **Production** | Docker · Logging · Monitoring · Cost Tracking · Rate Limiting · Security |
| **Automation** | n8n · Dify · Webhooks · Event-Driven Workflows |
| **Existing Engineering** | Node.js · React · Git · System Design |

---

## Daily 4-Hour System

```
1 hour  → Learn the concept
3 hours → Implement it in ProPhone
```

```
Every feature:
Learn → Build locally → Test → Integrate with ProPhone → Evaluate → Improve → Document
```

Don't spend the whole month watching courses, and don't let AI generate the entire project without understanding it. Use AI coding tools to move faster — but always be able to answer:

- *Why it works*
- *How it works*
- *What can fail*
- *How to evaluate it*
- *How to improve it*

---

## After 3 Months

You should be able to confidently build:

- ML Models
- LLM Applications
- RAG Systems
- AI APIs
- AI Agents
- Tool-Calling Systems
- AI Automation
- Production AI Services

And you'll have one strong real-world portfolio story:

> "I built and integrated an AI system into a production CRM that uses machine learning, LLMs, RAG, tool calling, agents, and workflow automation to analyze leads, understand CRM data, recommend sales actions, and assist salespeople."

**Not simply "I learned AI." — You become an engineer who can build and ship AI systems.**
