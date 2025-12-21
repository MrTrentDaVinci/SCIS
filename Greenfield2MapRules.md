# LLM friendly url: https://raw.githubusercontent.com/MrTrentDaVinci/SCIS/main/Greenfield2MapRules.md

---

# **SCIS Greenfield Map Rules (Metrics-Built-In)**

**Phase:** P0
**Applies to:** All New (Greenfield) Programs
**Status:** Authoritative Generation Rules

---
Filename Rules (Mandatory):
- All generated files MUST follow the exact format A#p#s#f#.<ext>
- Filenames are taken ONLY from the Flat File Map (A1p0s0f1.md).
- No new filenames may be invented.
- No renaming or reindexing is permitted.
---

## 1. Purpose of This File

This file defines the **only allowed rules** for generating a **Program File Map** (`A#p0s0f1`) for a new SCIS program.

It exists to ensure that:

* File structures are deterministic
* No logic, components, or implementations are guessed
* Large or complex programs remain expandable
* Multiple programs can coexist safely
* LLMs can generate file maps without context overflow
* **Metric definition is structurally unavoidable**

This file is read **before** any file map is created.

---

## 2. Required Inputs

An LLM generating a Program File Map **must have access to**:

1. `A0p0s0f0` — SCIS Global Orientation (Greenfield context)
2. `A1p0s0f0.md` — *SCIS Greenfield Start* (program intent + metric commitments)
3. This file (`A0p0s0f1.md`)

If any are missing, generation must stop.

---

## 3. Output File Definition

**File:** `A#p0s0f1.md`
**Name:** Program File Map

Defines **only**:

* Files
* Phases
* Sections
* Structural intent

It must **not** define:

* Components
* Non-components
* Logic
* Algorithms
* Data flow
* Metric formulas or thresholds
* Tooling

---

## 4. Core Principles (Non-Negotiable)

### 4.1 Structure Before Meaning

The file map declares **what must exist**, not **how it behaves**.

Metrics are treated as **structural obligations**, not runtime artifacts.

---

### 4.2 Expandability Is Mandatory

File maps must:

* Assume future growth
* Reserve space for evolution
* Avoid premature specialization
* Include **metrics expansion capacity**

---

### 4.3 Phase Discipline

Only **P0–P7 and P99** may be referenced.

At greenfield time:

* P0 is mandatory
* P1–P3 are common
* P4–P7 are reserved
* P99 must be reserved for long-lived systems

---

## 5. Program Scope Rules

When generating a file map, the LLM must decide only:

> **Is this program likely to grow beyond a small, single-purpose tool?**

If **yes**, the map must:

* Include multiple code sections
* Reserve UI / API / DB / tools space
* Include **metrics and observability sections**

If **no**, the map may be minimal but **must still reserve metric files**.

---

## 6. Mandatory Files in Every Program File Map (Updated)

Every `A#p0s0f1.md` **must include** the following structural zones:

---

### P0 — Program Definition & Governance

* Greenfield Start
* Program File Map
* Program-level rules
* Indexes and summaries

---

### P1 — Declarations & Contracts

* Component Maps (placeholders)
* Non-Component Maps (placeholders)
* NCCF files (templated)
* Dependency Maps
* **Metric Obligation Index (NEW)**

---

### P2–P4 — Implementation Zones (Reserved)

* Code sections (components & NCAs)
* Supporting utilities
* Optional UI / API / services

---

### P5 — Testing & Validation (Reserved)

* Tests
* Validation artifacts
* Test metrics

---

### P6 — Debug, Logs & Operational Signals (Reserved)

* Runtime logs
* Debug traces
* **Metric emissions (runtime-facing, not definitions)**

---

### P7 — Artifacts, Assets & Reports (Optional)

* Builds
* Assets
* **Metric reports / summaries (derived, not authoritative)**

---

### P99 — Evolution & History (Mandatory if Long-Lived)

* Change history
* Metric evolution records
* Structural deprecations

---

## 7. Metrics Structural Rules (NEW — Critical)

Metrics are **first-class structural citizens**.

The Program File Map **must reserve files for**:

1. **Metric Obligation Index**

   * Maps CA/NCA IDs → required metric categories

2. **Metric Definition Files**

   * Concrete metric definitions (later phases)
   * One-to-many mapping from obligations

3. **Metric Evolution History**

   * Append-only changes to metric meaning

⚠️ These files:

* Exist structurally at P0
* Contain no definitions at P0
* Cannot be removed in later phases

---

## 8. Section Usage Rules (Updated)

Sections (`s0–s9`) must follow:

| Section | Meaning                               |
| ------- | ------------------------------------- |
| s0      | Maps, indexes, summaries              |
| s1      | Registries, schemas, **metrics**, MEM |
| s2–s4   | Code (components & NCAs)              |
| s5      | Tests                                 |
| s6      | Debug, logs, runtime signals          |
| s7–s9   | Assets, builds, reports               |

Metrics **definitions live in s1**.
Metric **emissions live in s6**.
Metric **summaries live in s7–s9**.

No section may be repurposed.

---

## 9. File Naming Rules

All files must follow:

```
A#p#s#f#.<ext>
```

No descriptive filenames.
Meaning is conveyed only through:

* File map
* Headers
* Maps

Metric files follow the same rules.

---

## 10. Logic Exclusion Rule

The file map must **not**:

* Describe logic
* Name algorithms
* Define thresholds
* Specify calculations

Metrics are declared as **existence requirements only**.

---

## 11. Multi-Program Safety Rule

If multiple programs exist:

* Each program has its own A# namespace
* Shared metrics schemas belong in A0
* Program maps never reference other programs

Cross-program observability is handled later via dependency maps.

---

## 12. Human + LLM Readability Requirement

The file map must:

* Be readable by humans
* Be parsable by LLMs
* Use one-line file descriptions
* Avoid prose explanations

---

## 13. Validation Checklist (Expanded)

Before accepting a file map, verify:

* [ ] All phases are valid
* [ ] No components or logic defined
* [ ] Expandability preserved
* [ ] SCIS naming rules followed
* [ ] A0 vs A# boundaries respected
* [ ] Metric definition files structurally present
* [ ] Metric evolution space reserved
* [ ] No metric formulas or tooling defined

Failure → regenerate file map.

---

## End of File

---

## Why This Is the Right Move (Short, Important)

By doing this:

* Metrics become **inevitable**, not optional
* You avoid “observability as a later project”
* Support, NCCF, and runtime all snap to the same structure
* You eliminate an entire class of forgotten work
* SCIS stays **structural, not procedural**

You didn’t add complexity — you **removed a failure mode**.

---

### If you want next

I can:

* Update a **sample `A1p0s0f1.md` output** showing metric files included
* Align **A0 global metric schemas** to this structure
* Create a **validator rule-set** to enforce metric presence
* Stress-test this against a real SaaS or multi-tenant system

Just tell me where to push next.

