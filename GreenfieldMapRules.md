# The purpose of this file is to make the file A1p0s0f1.md using the A1p0s0f0.md

## Title: **SCIS Greenfield Map Rules**

**Phase:** P0
**Applies to:** All New (Greenfield) Programs
**Status:** Authoritative Generation Rules

---

## 1. Purpose of This File

This file defines the **only allowed rules** for generating a **Program File Map** (`A#p0s0f1`) for a new SCIS program.

It exists to ensure that:

* File structures are deterministic
* No logic, components, or implementation details are guessed
* Large or complex programs remain expandable
* Multiple programs can coexist safely in the same repository
* LLMs can generate file maps without exceeding context limits

This file is read **before** any file map is created.

---

## 2. Required Inputs

An LLM generating a Program File Map **must have access to**:

1. `A0p0s0f0` — SCIS Global Orientation (Greenfield context)
2. `A1p0s0f0.md` — *SCIS Greenfield Start* (program-specific intent)
3. This file (`A0p0s0f1.md`)

If any of these are missing, file-map generation must stop.

---

## 3. Output File Definition

The output of this process is:

**File:** `A#p0s0f1.md`
**Name:** Program File Map
**Purpose:**
Defines *only* the files, phases, and sections that will exist for the program.

It must **not** define:

* Components
* Non-components
* Logic
* APIs
* Databases
* UI details
* Algorithms
* Dependencies

---

## 4. Core Principles (Non-Negotiable)

### 4.1 Structure Before Meaning

The file map declares **where things will live**, not **what they do internally**.

### 4.2 Expandability Is Mandatory

File maps must:

* Assume future features
* Allow new phases, sections, or programs
* Avoid tight coupling or premature specialization

### 4.3 Phase Discipline

Only **P0–P7 and P99** may be referenced.

At greenfield time:

* P0 is mandatory
* P1–P3 are common
* P4–P7 are optional placeholders
* P99 must be reserved if long-lived

---

## 5. Program Scope Rules

When generating a file map, the LLM must decide **only one thing**:

> Is this program likely to grow beyond a small, single-purpose tool?

If **yes**, the file map must:

* Include multiple sections
* Reserve space for UI, APIs, DBs, or tools even if unused
* Prefer generic section purposes

If **no**, the file map may be minimal but **must still follow SCIS numbering rules**.

---

## 6. Mandatory Files in Every Program File Map

Every `A#p0s0f1.md` **must include**:

### P0 — Program Definition

* Entry summaries
* File map itself
* Program-specific rules
* High-level indexes

### P1 — Declarations

* Component maps (placeholders)
* Non-component maps (placeholders)
* NCCF files (empty or templated)
* Dependency maps

### P2–P4 — Implementation Zones (Reserved)

* Code sections
* Supporting utilities
* Optional UI / API / services

### P5 — Testing (Reserved)

* Tests
* Validation
* Test results

### P6 — Debug & Logs (Reserved)

### P7 — Artifacts / Assets (Optional)

---

## 7. Section Usage Rules

Sections (`s0–s9`) must follow these semantics:

| Section | Meaning                            |
| ------- | ---------------------------------- |
| s0      | Maps, indexes, summaries           |
| s1      | Registries, schemas, MEMs          |
| s2–s4   | Code (components & non-components) |
| s5      | Tests                              |
| s6      | Debug / logs                       |
| s7–s9   | Assets, builds, optional resources |

No section may be repurposed.

---

## 8. File Naming Rules

* All files **must** follow:
  `A#p#s#f#.<ext>`
* No descriptive filenames
* Meaning is conveyed **only** via:

  * File map
  * Headers
  * Maps

File numbering (`f#`) should:

* Leave gaps
* Allow insertion
* Avoid renumbering later

---

## 9. Logic Exclusion Rule

The file map **must not**:

* Describe logic flows
* Name algorithms
* Reference operators or data transformations

Logic will be handled later by:

* NCCF files
* Optional Logic Determinalization files
* Component-level design

---

## 10. Multi-Program Safety Rule

If more than one program may exist in the repository:

* Each program **must** have its own `A#` namespace
* Shared resources belong in `A0`
* Program file maps must not reference other programs directly

Inter-program relationships are handled later via dependency maps.

---

## 11. Human + LLM Readability Requirement

The file map must:

* Be readable by a human unfamiliar with SCIS
* Be parsable by an LLM without additional explanation
* Contain one-sentence descriptions per file

No prose essays. No speculation.

---

## 12. Validation Checklist (Must Pass)

Before accepting a file map, verify:

* [ ] All phases are valid
* [ ] No components are defined
* [ ] No logic is implied
* [ ] Expandability is preserved
* [ ] SCIS naming rules are followed
* [ ] A0 vs A# boundaries are respected

If any check fails, the file map must be regenerated.

---

## End of File
