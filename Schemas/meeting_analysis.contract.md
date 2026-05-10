# Meeting Analysis Contract（會議分析輸出契約）

Version: v1

Purpose:
Define the canonical AI output structure for meeting analysis workflows in the AI PM OS（AI 專案管理作業系統）.

---

# Core Philosophy（核心哲學）

AI outputs must be:

- structured
- stable
- automation-compatible
- retrieval-friendly
- schema-consistent

AI outputs are considered:

- operational system data
- workflow execution data
- PM tracking data

AI outputs are NOT free-form chat responses.

---

# Canonical Output Structure（正式輸出結構）

```json
{
  "summary": "",
  "tasks": [],
  "risks": [],
  "decisions": [],
  "knowledge": []
}
```

---

# Output Rules（輸出規則）

AI must always output:

- valid JSON
- canonical field names
- stable field structure
- array-based collections

AI must NOT output:

- markdown
- explanation text
- natural conversation
- dynamic field names

---

# Field Definitions（欄位定義）

## summary

Type:
string

Description:
Short semantic summary of the meeting.

Rules:

- concise
- operationally useful
- avoid giant paragraphs

Example:

```json
{
  "summary": "Customer discussed Flexiv deployment for smart mall guidance."
}
```

---

## tasks

Type:
array

Description:
Executable operational tasks extracted from the meeting.

Structure:

```json
{
  "title": "",
  "description": "",
  "priority": "",
  "status": "todo"
}
```

Rules:

- actionable
- traceable
- avoid ambiguity

---

## risks

Type:
array

Description:
Operational or engineering risks identified from the meeting.

Structure:

```json
{
  "title": "",
  "severity": "",
  "impact": "",
  "mitigation": ""
}
```

Rules:

- preserve engineering risk
- preserve PM risk
- preserve customer risk

---

## decisions

Type:
array

Description:
Important operational decisions extracted from the meeting.

Structure:

```json
{
  "title": "",
  "reason": "",
  "constraint": ""
}
```

Rules:

- preserve why decisions happened
- preserve constraints
- preserve tradeoffs

---

## knowledge

Type:
array

Description:
Long-term reusable knowledge extracted from the meeting.

Structure:

```json
{
  "title": "",
  "summary": "",
  "tags": []
}
```

Rules:

- avoid raw meeting duplication
- preserve reusable knowledge
- preserve semantic clarity

---

# AI Rules（AI 規則）

AI must:

- preserve source context
- preserve engineering meaning
- preserve project continuity
- preserve operational traceability

AI should avoid:

- hallucinated tasks
- duplicate risks
- duplicated knowledge
- missing relationships

---

# Naming Rules（命名規則）

AI must always use:

```json
tasks
risks
decisions
knowledge
```

AI must NOT use:

```json
todo
action_items
issues
notes
memo
```

---

# Validation Rules（驗證規則）

Before output:

AI must validate:

- JSON format validity
- required field existence
- array structure validity
- canonical naming compliance

---

# Future Expansion（未來擴展）

Future fields may include:

- schedule
- dependencies
- workflow_actions
- ai_agent_actions
- retrieval_context

Future expansion must:

- preserve backward compatibility
- preserve canonical naming
- preserve schema stability
