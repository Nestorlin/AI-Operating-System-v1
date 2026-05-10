# Database Mapping（資料庫映射）

Version: v1

Purpose:
Define the canonical database mapping between Notion databases and AI PM OS entities.

---

# Core Philosophy（核心哲學）

The AI PM OS requires:

- stable database meaning
- canonical entity alignment
- retrieval consistency
- workflow consistency
- operational traceability

Each database should:

- have one primary responsibility
- map to one canonical entity
- avoid semantic duplication

---

# Database Mapping Table（資料庫映射表）

| Notion Database | Canonical Entity（正式實體） | Purpose（用途） |
|---|---|---|
| Meeting Database | meeting | Structured operational meetings |
| TODO Database | task | Operational task tracking |
| Tasks | task | Operational task tracking |
| Customer Database | customer | Customer management |
| Projects | project | Project management |
| Notes | raw_note | Temporary raw notes |
| Docs | knowledge | Long-term knowledge and SOP |
| Weekly Report Database | weekly_report | Weekly operational reporting |

---

# Canonical Rules（正式規則）

## Rule 1

TODO Database and Tasks are considered:

```text
task
```

Canonical entity.

Future systems should gradually unify them.

---

## Rule 2

Notes are NOT knowledge.

Notes represent:

- temporary capture
- raw information
- unstructured drafts

Notes should not become long-term retrieval sources directly.

---

## Rule 3

Meeting Database is the operational event source.

Meetings may generate:

- tasks
- risks
- decisions
- knowledge

Meetings themselves are NOT long-term knowledge.

---

## Rule 4

Docs database represents:

```text
knowledge
```

Long-term reusable operational intelligence.

Examples:

- SOP
- engineering lessons
- workflow standards
- architecture decisions

---

## Rule 5

Weekly Report Database represents:

```text
weekly_report
```

Operational aggregation outputs.

Weekly reports should derive from:

- meetings
- tasks
- risks
- project updates

---

# Future Migration Rules（未來遷移規則）

Future architecture should gradually:

- reduce duplicated databases
- reduce semantic overlap
- normalize naming
- normalize relationships

Avoid:

- duplicated entities
- mixed operational meanings
- temporary database sprawl

---

# AI Rules（AI 規則）

AI must:

- use canonical entity naming
- preserve database meaning
- preserve operational context
- avoid semantic conflicts

AI should avoid:

- generating duplicated entities
- mixing notes with knowledge
- mixing tasks with decisions

---

# Future Expansion（未來擴展）

Future databases may include:

- risk_db
- decision_db
- ai_agent_memory
- workflow_execution_log
- validation_result

Future expansion must:

- preserve canonical mapping
- preserve naming consistency
- preserve retrieval quality
