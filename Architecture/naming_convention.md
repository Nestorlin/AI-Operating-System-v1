# Naming Convention（命名規範）

Version: v1

Purpose:
Define canonical naming rules for the AI PM OS（AI 專案管理作業系統）.

---

# Core Philosophy（核心哲學）

The AI PM OS requires:

- stable naming
- semantic consistency
- retrieval-friendly naming
- AI-readable naming
- maintainable structure

Avoid:

- duplicate meaning
- synonym drift
- unclear entity names
- mixed naming styles

---

# Global Rules（全域規則）

## Rule 1

Use:

snake_case（底線命名）

Preferred:

```text
task_db
meeting_summary
risk_analysis
```

Avoid:

```text
TaskDB
meetingSummary
Risk-Analysis
```

---

## Rule 2

Use lowercase naming（小寫命名）

Preferred:

```text
task
project
customer
```

Avoid:

```text
Task
PROJECT
Customer
```

---

## Rule 3

One meaning = one canonical name

Avoid synonym duplication.

---

# Canonical Entity Names（正式實體名稱）

| Canonical Name | Avoid |
|---|---|
| task | todo, action_item |
| meeting | meeting_note, discussion |
| customer | client |
| project | case |
| risk | issue |
| decision | agreement |
| knowledge | memo, note |

---

# Database Naming Rules（資料庫命名規則）

Preferred:

```text
task_db
meeting_db
risk_db
knowledge_db
```

Avoid:

```text
TODO Database
Meeting Notes
Knowledge Final
```

---

# Workflow Naming Rules（工作流命名規則）

Structure:

```text
[source]_[process]_[output]_v[number]
```

Example:

```text
meeting_analysis_task_generation_v1
```

Avoid:

```text
new_workflow
test_workflow
final_final_workflow
```

---

# Prompt Naming Rules（提示詞命名規則）

Structure:

```text
[purpose]_prompt_v[number]
```

Example:

```text
meeting_analysis_prompt_v1
risk_analysis_prompt_v1
```

---

# Schema Naming Rules（資料契約命名規則）

Structure:

```text
[entity].schema.md
```

Example:

```text
task.schema.md
meeting.schema.md
risk.schema.md
```

---

# AI Output Rules（AI 輸出規則）

AI must always use:

- canonical entity names
- canonical field names
- canonical workflow names

AI should avoid:

- synonym generation
- dynamic field naming
- inconsistent structure

---

# Future Expansion Rules（未來擴展規則）

New entities must:

- avoid semantic duplication
- avoid naming conflicts
- preserve retrieval consistency
- preserve workflow clarity

---

# Naming Freeze Rules（命名凍結規則）

Once canonical naming is defined:

- avoid renaming entities frequently
- avoid multiple meanings
- avoid temporary naming
- avoid UI-oriented naming

Naming changes require:

- architecture review
- schema review
- workflow review
