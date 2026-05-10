# Decision Schema（決策資料契約）

Version: v1

Purpose:
Define the canonical decision entity structure for the AI PM OS（AI 專案管理作業系統）.

---

# Entity（實體）

decision

---

# Description（描述）

Decision represents:

- operational decisions
- engineering decisions
- PM decisions
- customer agreements
- workflow decisions

Decision preserves:

- why a decision happened
- what constraints existed
- what tradeoffs existed
- what assumptions existed

Decision is critical for:

- long-term operational memory
- AI reasoning continuity
- PM traceability
- engineering history

---

# Rules（規則）

- One decision = one major operational choice
- Decisions must preserve reasoning context
- Decisions must preserve constraints
- Decisions must preserve tradeoffs
- Decisions must support traceability

---

# Fields（欄位）

## decision_id

Type: uuid

Description:
Unique decision identifier.

Required:
Yes

Example:

```yaml
decision_id: decision_2026_001
```

---

## title

Type: string

Description:
Short decision title.

Required:
Yes

Example:

```yaml
title: Use single-arm Flexiv deployment
```

---

## description

Type: text

Description:
Detailed decision description.

Required:
No

---

## reason

Type: text

Description:
Why this decision was made.

Required:
Yes

Example:

```yaml
reason: Budget limitation and deployment simplicity
```

---

## constraint

Type: text

Description:
Operational or engineering constraints.

Required:
No

Example:

```yaml
constraint: Customer budget limitation
```

---

## tradeoff

Type: text

Description:
Tradeoffs introduced by this decision.

Required:
No

Example:

```yaml
tradeoff: Reduced interaction capability
```

---

## status

Type: enum

Allowed Values:

- proposed
- approved
- rejected
- deprecated

Description:
Decision status.

Required:
Yes

Example:

```yaml
status: approved
```

---

## source_meeting

Type: relation

Relation:
meeting

Description:
Source meeting reference.

Required:
No

---

## related_project

Type: relation

Relation:
project

Description:
Related project reference.

Required:
No

---

## related_customer

Type: relation

Relation:
customer

Description:
Related customer reference.

Required:
No

---

## created_at

Type: datetime

Description:
Decision creation time.

Required:
Yes

---

## updated_at

Type: datetime

Description:
Last update time.

Required:
Yes

---

# Retrieval Rules（檢索規則）

- Preserve decision reasoning
- Preserve operational context
- Preserve engineering constraints
- Preserve tradeoff history
- Preserve PM continuity

---

# AI Rules（AI 規則）

AI must:

- preserve why decisions happened
- preserve engineering reasoning
- preserve PM reasoning
- preserve customer constraints
- preserve operational continuity

AI should avoid:

- missing reasons
- vague decisions
- duplicated decisions
- missing constraints
- missing tradeoffs

---

# Naming Convention（命名規則）

Preferred:

```text
single_arm_flexiv_deployment
```

Avoid:

```text
decision1
customer_choice
final_option
```

---

# Related Entities（相關實體）

- meeting
- project
- customer
- task
- risk
- knowledge
