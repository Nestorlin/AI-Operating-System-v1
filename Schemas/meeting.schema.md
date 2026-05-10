# Meeting Schema（會議資料契約）

Version: v1

Purpose:
Define the canonical meeting entity structure for the AI PM OS（AI 專案管理作業系統）.

---

# Entity（實體）

meeting

---

# Description（描述）

Meeting represents:

- operational events
- customer discussions
- PM discussions
- engineering reviews
- project coordination events

Meeting is the primary operational context source.

Meeting may generate:

- tasks
- risks
- decisions
- knowledge

Meeting is NOT long-term knowledge itself.

---

# Rules（規則）

- One meeting = one operational event
- Meetings must preserve source context
- Meetings must support traceability
- Meetings must support AI analysis
- Meetings must preserve project continuity

---

# Fields（欄位）

## meeting_id

Type: uuid

Description:
Unique meeting identifier.

Required:
Yes

Example:

```yaml
meeting_id: meeting_2026_001
```

---

## title

Type: string

Description:
Meeting title.

Required:
Yes

Example:

```yaml
title: Flexiv Smart Mall Deployment Discussion
```

---

## customer

Type: relation

Relation:
customer

Description:
Related customer.

Required:
No

---

## related_project

Type: relation

Relation:
project

Description:
Related project.

Required:
No

---

## meeting_date

Type: datetime

Description:
Meeting date and time.

Required:
Yes

---

## participants

Type: array

Description:
Meeting participants.

Required:
No

Example:

```yaml
participants:
  - Tony
  - Customer PM
  - Engineering Team
```

---

## raw_source

Type: file_reference

Description:
Original meeting source.

Supported:

- audio
- transcript
- pdf
- ppt
- notes

Required:
No

---

## summary

Type: text

Description:
AI-generated meeting summary.

Required:
No

---

## extracted_tasks

Type: relation_array

Relation:
task

Description:
Tasks generated from this meeting.

Required:
No

---

## extracted_risks

Type: relation_array

Relation:
risk

Description:
Risks generated from this meeting.

Required:
No

---

## extracted_decisions

Type: relation_array

Relation:
decision

Description:
Decisions generated from this meeting.

Required:
No

---

## extracted_knowledge

Type: relation_array

Relation:
knowledge

Description:
Knowledge generated from this meeting.

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
  - robotics
```

---

## created_at

Type: datetime

Description:
Meeting creation time.

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

- Preserve meeting context
- Preserve project relation
- Preserve customer relation
- Preserve semantic continuity
- Avoid giant mixed-topic meetings

---

# AI Rules（AI 規則）

AI must:

- preserve operational meaning
- preserve customer requirements
- preserve engineering constraints
- preserve decision history
- preserve PM continuity

AI should avoid:

- hallucinated meeting summaries
- duplicated tasks
- duplicated risks
- duplicated knowledge

---

# Naming Convention（命名規則）

Preferred:

```text
meeting_2026_05_10_flexiv_smart_mall
```

Avoid:

```text
meeting1
customer_meeting
discussion_final
```

---

# Related Entities（相關實體）

- customer
- project
- task
- risk
- decision
- knowledge
