# **Greenfield Component Map Maker**

**SCIS v4.x — Program-Local Generation Contract**

---

## 1. Purpose

This document defines the **only authorized process** for generating **Component Maps** and **Non-Component Maps** for a new (greenfield) SCIS program.

It ensures that:

* Components are identified *before* logic or code
* Program structure is deterministic and portable
* Large systems remain composable and evolvable
* LLMs do not infer or hallucinate structure

---

## 2. Scope

This file applies to:

* New programs only (A1+)
* Phase P0 only
* Pre-implementation planning

It does **not**:

* Define logic
* Define dependencies
* Define algorithms
* Define file contents

---

## 3. Allowed Inputs (Strict)

The LLM may read **only** the following files:

1. **`A1p0s0f0.md`**
   *Greenfield Start — Program intent, goals, constraints, users*

2. **`A1p0s0f1.md`**
   *Program File Map — phases, sections, code-bearing locations*

3. **This file**
   *Greenfield Component Map Maker*

❌ **Forbidden Inputs**

* Any A0 files
* Any schemas
* Any registries
* Any dependency maps
* Any future-phase files
* Any code

---

## 4. Output Files

For **each section that contains code**, generate:

### Mandatory

* **One Section Component Map**

  * `A1p0s#f#.toon`

### Optional (only if needed)

* **One Section Non-Component Map**

  * `A1p0s#f#.toon`

No maps are generated for non-code sections.

---

## 5. Section Awareness Rule (Critical)

1. Read the **Program File Map**
2. Identify sections explicitly marked as **code-bearing**
3. For each such section:

   * Generate exactly **one Component Map**
   * Optionally generate one Non-Component Map
4. Do not combine sections
5. Do not split a section across maps

Each section is autonomous.

---

## 6. Definition of a Component (Greenfield)

A **component** is a *stable unit of responsibility* that:

* Has a long lifetime
* Represents a conceptual role
* Will likely evolve internally
* May own logic later

### Valid Components

* Services
* Controllers
* Managers
* Engines
* Handlers
* UI modules
* API endpoints (as units)

### Invalid Components

* Helper functions
* Algorithms
* Data structures
* Validation rules
* Config files
* Error handling
* Glue code

> **Rule:** If it sounds like logic, it is not a component.

---

## 7. Component Entry Requirements

Each component entry must include:

* **Component ID**
  `CA1p0s#f#.#` (stable, permanent)

* **Title**
  Human-readable name

* **Purpose**
  One sentence, *no logic*

* **Phase Declared**
  Always `P0`

* **Owning Section**
  `s#`

### Explicitly Forbidden in Component Maps

* Dependencies
* Inputs/outputs
* Logic
* Algorithms
* Data flow
* Error handling

---

## 8. Non-Component Rules

Non-Components include:

* Constants
* Types
* Helpers
* Schemas
* Templates
* Config
* Static data

They:

* Receive IDs (`NCA1p0s#f#.#`)
* Are section-scoped
* Do not get NCCFs
* Are not executable units

If unsure → **Non-Component**

---

## 9. Granularity Rules

* Prefer **fewer, larger components**
* Components may internally grow later
* Never pre-optimize
* Never mirror files or folders

> SCIS components are conceptual, not structural.

---

## 10. ID Rules

* IDs are immutable
* IDs are never reused
* Gaps are allowed
* Deleted components keep their IDs reserved

IDs exist for traceability, not aesthetics.

---

## 11. Validation Checklist

Before accepting a Component Map, verify:

* [ ] Every code section has exactly one Component Map
* [ ] No logic or behavior described
* [ ] No dependencies listed
* [ ] All components have stable IDs
* [ ] All entries are section-scoped
* [ ] Non-Components separated where appropriate

---

## 12. What Comes Next

Once **all Section Component Maps** are complete:

➡ Proceed to **Greenfield NCCF Maker**

That is the **first moment** when:

* Inputs
* Outputs
* Dependencies
* Constraints
* MCP integrations

are allowed to appear.

---

## 13. Design Rationale (For Humans & LLMs)

This separation ensures:

* Deterministic planning
* Safer LLM execution
* Easier upgrades
* Controlled evolution
* Massive context reduction

SCIS builds **structure first**, **logic later**, **code last**.


