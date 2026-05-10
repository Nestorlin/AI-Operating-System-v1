# Current System Problems（目前系統問題）

Version: v1

Purpose:
Document the current architectural problems, semantic drift, and operational risks identified during the AI PM OS（AI 專案管理作業系統） audit phase.

This document serves as:

- migration baseline
- architecture refactor reference
- normalization reference
- future governance reference

---

# Core Observation（核心觀察）

The current system evolved from:

- workflow-first thinking
- operational convenience
- rapid AI experimentation

The system is now transitioning into:

- data-driven architecture
- canonical schema architecture
- AI operational intelligence system

---

# Current Major Problems（目前主要問題）

---

# 1. Semantic Drift（語意漂移）

Multiple semantic meanings exist for the same operational entity.

Examples:

| Current Naming | Canonical Naming |
|---|---|
| TODO | task |
| TODOs | task |
| Next Action | task |
| Next Week Plan | future_task |

Risk:

- AI confusion
- retrieval inconsistency
- workflow instability
- duplicated operational logic

---

# 2. Missing Project Layer（缺少專案層）

Current architecture is:

```text
Customer
↓
Meeting
↓
Task
```

Missing:

```text
Project
```

Risk:

- mixed project context
- customer-level semantic pollution
- task overlap
- PM traceability degradation

Impact:

Future PM scalability will become difficult without a dedicated project entity.

---

# 3. Mixed Entity Responsibility（實體責任混亂）

Operational entities are mixed inside databases.

Examples:

Meeting Database currently contains:

- meeting data
- task-like fields
- risk-like fields
- next action logic

Risk:

- semantic conflict
- unclear ownership
- AI extraction instability

---

# 4. Duplicate Status Fields（重複狀態欄位）

Some databases contain duplicated status meanings.

Examples:

- Status
- 狀態

Risk:

- AI ambiguity
- workflow inconsistency
- reporting instability

---

# 5. Notes Pollution Risk（備註污染風險）

Notes fields may become:

- mixed temporary notes
- SOP
- operational history
- knowledge dumping

Risk:

- retrieval pollution
- semantic noise
- AI context degradation

Notes should remain:

- lightweight
- temporary
- operational-only

---

# 6. TODO-Centric Architecture（TODO 中心架構）

Current system uses:

```text
TODO
```

instead of:

```text
task
```

Risk:

- poor PM scalability
- workflow ambiguity
- operational inconsistency

Canonical architecture should use:

```text
task
```

as the operational execution entity.

---

# 7. Weak Relationship Structure（關聯結構不足）

Current databases contain limited formal relationships.

Future architecture requires:

- customer ↔ project
- project ↔ meeting
- meeting ↔ task
- meeting ↔ risk
- meeting ↔ decision
- meeting ↔ knowledge

Risk:

- weak traceability
- weak AI reasoning continuity
- weak retrieval quality

---

# 8. AI Output Drift Risk（AI輸出漂移風險）

Current workflows rely on flexible AI outputs.

Risk examples:

```json
tasks
todo
action_items
```

Risk:

- workflow failures
- parser instability
- database inconsistency

Solution direction:

- canonical AI output contracts
- normalization layer
- schema validation

---

# Current System Strengths（目前系統優勢）

Despite current issues, the system already demonstrates:

- event-driven architecture
- AI workflow integration
- operational traceability awareness
- PM-oriented thinking
- relational operational structure
- semantic routing concepts

The system foundation is strong enough for normalization and future AI expansion.

---

# Current Refactor Strategy（目前重構策略）

Current strategy is:

```text
Audit
→
Canonical Schema Freeze
→
Normalization
→
Migration
→
Workflow Alignment
→
Retrieval
→
AI Agent Expansion
```

Avoid:

- direct large-scale refactor
- immediate database deletion
- uncontrolled schema changes
- workflow-first redesign

---

# Long-term Direction（長期方向）

The AI PM OS is evolving toward:

- AI-native operational system
- operational intelligence platform
- organizational memory system
- AI retrieval architecture
- AI PM operating system
