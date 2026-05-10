# Knowledge Schema（知識資料契約）

Version: v1

Purpose:
Define the canonical knowledge entity structure for the AI PM OS（AI 專案管理作業系統）.

---

# Entity（實體）

knowledge

---

# Description（描述）

Knowledge represents:

- reusable operational intelligence
- reusable engineering knowledge
- reusable workflow knowledge
- lessons learned
- best practices
- long-term AI memory

Knowledge is derived from:

- meetings
- projects
- failures
- SOP
- operational experience
- engineering experience

Knowledge is NOT raw operational events.

Knowledge is refined semantic intelligence.

---

# Rules（規則）

- One knowledge entry = one semantic topic
- Knowledge must be reusable
- Knowledge must preserve operational meaning
- Knowledge must support retrieval
- Knowledge must preserve long-term maintainability

---

# Fields（欄位）

## knowledge_id

Type: uuid

Description:
Unique knowledge identifier.

Required:
Yes

Example:

```yaml
knowledge_id: knowledge_2026_001
```

---

## title

Type: string

Description:
Knowledge title.

Required:
Yes

Example:

```yaml
title: Flexiv Smart Mall Deployment Best Practice
```

---

## summary

Type: text

Description:
Short semantic summary.

Required:
Yes

---

## category

Type: enum

Allowed Values:

- engineering
- workflow
- PM
- deployment
- AI
- automation
- failure_lesson
- SOP

Description:
Knowledge category.

Required:
Yes

Example:

```yaml
category: deployment
```

---

## lessons_learned

Type: text

Description:
Operational or engineering lessons learned.

Required:
No

---

## best_practice

Type: text

Description:
Recommended best practice.

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

## related_risks

Type: relation_array

Relation:
risk

Description:
Related operational risks.

Required:
No

---

## related_decisions

Type: relation_array

Relation:
decision

Description:
Related operational decisions.

Required:
No

---

## tags

Type: array

Description:
Semantic tags.

Required:
No

Example:

```yaml
tags:
  - flexiv
  - smart_mall
  - deployment
```

---

## created_at

Type: datetime

Description:
Knowledge creation time.

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

- One topic per knowledge entry
- Preserve semantic clarity
- Preserve operational meaning
- Preserve engineering meaning
- Avoid mixed-topic knowledge

---

# AI Rules（AI 規則）

AI must:

- extract reusable knowledge
- preserve engineering meaning
- preserve PM meaning
- preserve operational context
- preserve lessons learned

AI should avoid:

- raw meeting duplication
- giant mixed-topic knowledge
- duplicated knowledge
- vague summaries

---

# Naming Convention（命名規則）

Preferred:

```text
flexiv_smart_mall_deployment_best_practice
```

Avoid:

```text
note1
knowledge_final
meeting_summary
```

---

# Related Entities（相關實體）

- meeting
- project
- customer
- risk
- decision
