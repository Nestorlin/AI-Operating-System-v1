# Task Schema（任務資料契約）

Version: v1

Purpose:
Define the canonical task entity structure for the AI PM OS（AI 專案管理作業系統）.

---

# Entity（實體）

task

---

# Description（描述）

Task represents executable operational work items.

Task is the core execution entity in the AI PM OS.

---

# Rules（規則）

- One task = one responsibility
- Task must be traceable
- Task must support AI retrieval
- Task must support PM tracking
- Task must preserve source context

---

# Fields（欄位）

## task_id

Type: uuid

Description:
Unique task identifier.

Required:
Yes

Example:

```yaml
task_id: task_2026_001
```

---

## title

Type: string

Description:
Short task title.

Required:
Yes

Example:

```yaml
title: Update Flexiv proposal
```

---

## description

Type: text

Description:
Detailed task description.

Required:
No

---

## status

Type: enum

Allowed Values:

- todo
- in_progress
- blocked
- review
- done

Description:
Current task status.

Required:
Yes

Example:

```yaml
status: todo
```

---

## priority

Type: enum

Allowed Values:

- low
- medium
- high
- critical

Description:
Task priority level.

Required:
Yes

Example:

```yaml
priority: high
```

---

## owner

Type: relation

Relation:
people

Description:
Task owner.

Required:
No

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

## due_date

Type: datetime

Description:
Task due date.

Required:
No

---

## created_at

Type: datetime

Description:
Task creation time.

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

- Prefer short semantic task titles
- Preserve source meeting relation
- Preserve project relation
- Avoid mixed responsibilities
- Avoid giant task descriptions

---

# AI Rules（AI 規則）

AI must:

- Generate clear actionable tasks
- Avoid ambiguous wording
- Preserve customer context
- Preserve engineering constraints
- Preserve project traceability

---

# Naming Convention（命名規則）

Preferred:

```text
update_flexiv_proposal
```

Avoid:

```text
task1
misc_work
update
```

---

# Related Entities（相關實體）

- meeting
- project
- customer
- risk
- decision

