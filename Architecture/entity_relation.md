# Entity Relation（實體關聯）

Version: v1

Purpose:
Define the canonical entity relationships for the AI PM OS（AI 專案管理作業系統）.

---

# Core Philosophy（核心哲學）

The AI PM OS is relationship-driven.

AI should understand:

- where data comes from
- what data is related
- what data affects other data
- what operational context exists

The system is not document-oriented only.

The system is operational-context-oriented.

---

# Core Entity Structure（核心實體結構）

Customer（客戶）
  ↓
Project（專案）
  ↓
Meeting（會議）
  ↓
Task（任務）
  ↓
Risk（風險）
  ↓
Decision（決策）
  ↓
Knowledge（知識）

---

# Entity Relationship Rules（實體關聯規則）

## Customer（客戶）

Customer may contain:

- multiple projects
- multiple meetings
- multiple risks
- multiple decisions

---

## Project（專案）

Project belongs to:

- one customer

Project may contain:

- multiple meetings
- multiple tasks
- multiple risks
- multiple decisions
- multiple knowledge entries

---

## Meeting（會議）

Meeting belongs to:

- one project
- one customer

Meeting may generate:

- multiple tasks
- multiple risks
- multiple decisions
- multiple knowledge entries

Meeting is considered:

- an operational event
- a context source
- a workflow trigger

Meeting is NOT long-term knowledge itself.

---

## Task（任務）

Task may belong to:

- one meeting
- one project
- one customer

Task represents:

- executable work
- operational tracking
- workflow execution

Task must:

- preserve traceability
- preserve source context
- support PM tracking

---

## Risk（風險）

Risk may belong to:

- one meeting
- one project
- one customer

Risk represents:

- operational uncertainty
- technical risk
- schedule risk
- PM risk

Risk must support:

- mitigation tracking
- escalation tracking
- historical analysis

---

## Decision（決策）

Decision may belong to:

- one meeting
- one project
- one customer

Decision represents:

- important operational choices
- engineering decisions
- PM decisions
- customer agreements

Decision must preserve:

- why the decision happened
- what constraints existed
- what tradeoffs existed

---

## Knowledge（知識）

Knowledge may originate from:

- meeting analysis
- failure lessons
- SOP
- PM workflow
- engineering experience

Knowledge represents:

- reusable long-term intelligence
- reusable workflow knowledge
- reusable engineering knowledge

Knowledge must:

- avoid raw meeting duplication
- preserve semantic structure
- support retrieval

---

# AI Relationship Rules（AI 關聯規則）

AI must:

- preserve relationship context
- preserve source traceability
- preserve project continuity
- preserve customer continuity

AI should avoid:

- isolated data generation
- orphan tasks
- orphan risks
- duplicate knowledge
- mixed responsibilities

---

# Operational Rules（營運規則）

All operational entities should:

- preserve source context
- support long-term retrieval
- support AI workflows
- support PM tracking
- support future AI agents

---

# Future Expansion（未來擴展）

Future supported entities may include:

- SOP
- Engineering Change
- Incident
- Workflow
- AI Agent Memory
- Automation Execution
- Validation Result

Future expansion should:

- preserve canonical relationships
- avoid duplicated entity meaning
- avoid semantic conflicts
