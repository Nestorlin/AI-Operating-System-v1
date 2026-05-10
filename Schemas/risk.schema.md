# Risk Schema（風險資料契約）

Version: v1

Purpose:
Define the canonical risk entity structure for the AI PM OS（AI 專案管理作業系統）.

---

# Entity（實體）

risk

---

# Description（描述）

Risk represents:

- operational uncertainty
- engineering risk
- PM risk
- schedule risk
- customer risk
- workflow risk

Risk is a core PM entity.

Risk must support:

- tracking
- escalation
- mitigation
- historical analysis

---

# Rules（規則）

- One risk = one operational concern
- Risks must preserve source context
- Risks must support PM tracking
- Risks must support escalation
- Risks must preserve project continuity

---

# Fields（欄位）

## risk_id

Type: uuid

Description:
Unique risk identifier.

Required:
Yes

Example:

```yaml
risk_id: risk_2026_001
```

---

## title

Type: string

Description:
Short risk title.

Required:
Yes

Example:

```yaml
title: Flexiv delivery schedule delay
```

---

## description

Type: text

Description:
Detailed risk description.

Required:
No

---

## severity

Type: enum

Allowed Values:

- low
- medium
- high
- critical

Description:
Risk severity level.

Required:
Yes

Example:

```yaml
severity: high
```

---

## impact

Type: text

Description:
Operational or engineering impact.

Required:
No

---

## mitigation

Type: text

Description:
Mitigation strategy.

Required:
No

---

## status

Type: enum

Allowed Values:

- open
- monitoring
- mitigated
- resolved

Description:
Current risk status.

Required:
Yes

Example:

```yaml
status: open
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

## owner

Type: relation

Relation:
people

Description:
Risk owner.

Required:
No

---

## escalation_required

Type: boolean

Description:
Whether escalation is required.

Required:
No

Example:

```yaml
escalation_required: true
```

---

## created_at

Type: datetime

Description:
Risk creation time.

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

- Preserve source meeting relation
- Preserve project continuity
- Preserve operational context
- Preserve mitigation history
- Preserve escalation history

---

# AI Rules（AI 規則）

AI must:

- identify operational risks
- identify engineering risks
- identify schedule risks
- identify dependency risks
- preserve PM context

AI should avoid:

- vague risks
- duplicated risks
- missing mitigation suggestions
- missing escalation indicators

---

# Naming Convention（命名規則）

Preferred:

```text
flexiv_delivery_schedule_delay
```

Avoid:

```text
risk1
problem
issue
```

---

# Related Entities（相關實體）

- meeting
- project
- customer
- task
- decision
