# LLM friendly url: https://raw.githubusercontent.com/MrTrentDaVinci/SCIS/main/Greenfield3ComponentMapMaker.md
---

# **Greenfield Component Map Maker (With Metrics)**

**SCIS v4.x — Program-Local Generation Contract**

---

## 1. Purpose

This document defines the **only authorized process** for generating **Component Maps (CA)** and **Non-Component Maps (NCA)** for a new (greenfield) SCIS program.

It ensures that:

* Components and non-components are identified *before* logic or code
* Program structure is deterministic, portable, and evolvable
* **Every declared element is measurable by default**
* Large systems remain observable and supportable at scale
* LLMs do not infer, hallucinate, or create unmeasured structure

---

## 2. Scope

This file applies to:

* New programs only (A1+)
* Stage S0 only
* Pre-implementation planning

It explicitly **does not**:

* Define logic
* Define dependencies
* Define algorithms
* Define inputs or outputs
* Define file contents
* Define metric implementations, thresholds, or tooling

Metrics are **declared as obligations only**.

---

## 3. Allowed Inputs (Strict)

The LLM may read **only** the following files:

1. **`A1p0s0f0.md`**
   *Greenfield Start — intent, goals, constraints, users, metric commitments*

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
* Any existing metric catalogs

---

## 4. Output Files

For **each section that contains code**, generate:

### Mandatory

* **One Section Component Map**
  `A1p#s#f#.toon`

### Optional (only if needed)

* **One Section Non-Component Map**
  `A1p#s#f#.toon`

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

Each section is autonomous and independently observable.

---

## 6. Definition of a Component (Greenfield)

A **component (CA)** is a *stable unit of responsibility* that:

* Has a long lifetime
* Represents a conceptual role
* Will likely evolve internally
* May own logic in later phases
* **Will emit metrics once implemented**

### Valid Components

* Services
* Controllers
* Managers
* Engines
* Handlers
* UI modules
* API endpoints (as conceptual units)

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

## 7. Component Entry Requirements (Extended for Metrics)

Each **component entry** must include:

* **Component ID**
  `CA1p#s#f#.#` (stable, permanent)

* **Title**
  Human-readable name

* **Purpose**
  One sentence, *no logic*

* **Stage Declared**
  Always `S0`

* **Owning Section**
  `s#`

* **Metric Obligation Declaration (Mandatory)**
  A short declaration stating that this component will later emit metrics in the following **classes** (not definitions):

  * Usage & access
  * Contract / constraint compliance
  * Determinism & variance
  * Dependency health
  * Safety & violation signals
  * Evolution & change tracking

⚠️ **Do not define metric names, formulas, thresholds, or tools.**

---

### Explicitly Forbidden in Component Maps

* Dependencies
* Inputs or outputs
* Logic or behavior
* Algorithms
* Data flow
* Error handling
* Metric implementations
* Metric thresholds or SLAs

---

## 8. Non-Component Rules (With Metrics)

Non-Components (NCA) include:

* Constants
* Types
* Helpers
* Schemas
* Templates
* Config
* Static data
* Assets

They:

* Receive IDs (`NCA1p#s#f#.#`)
* Are section-scoped
* Do not get NCCFs
* Are not executable units
* **Must still be measurable**

---

### Non-Component Entry Requirements

Each **non-component entry** must include:

* **Non-Component ID**
* **Title**
* **Role / Nature** (what kind of thing it is)
* **Owning Section**
* **Metric Obligation Declaration**, covering (as applicable):

  * Access frequency
  * Read/write or mutation signals
  * Dependency role
  * Staleness or unused detection
  * Promotion signals (NCA behaving like CA)

If unsure → **Non-Component with metrics**

---

## 9. Granularity Rules

* Prefer **fewer, larger components**
* Components may internally grow later
* Never pre-optimize
* Never mirror files or folders

> SCIS components are conceptual, not structural —
> metrics exist to reveal when conceptual boundaries need revision.

---

## 10. ID Rules

* IDs are immutable
* IDs are never reused
* Gaps are allowed
* Deleted components and non-components retain their IDs permanently

IDs exist for **traceability, metrics correlation, and supportability**, not aesthetics.

---

## 11. Metrics Discipline Rules (S0-Safe)

At P0:

* Metrics are **declared as obligations only**
* No metric collection is defined
* No dashboards are implied
* No operational assumptions are allowed

However:

> **No CA or NCA may exist without a declared metric obligation.**

Metric gaps are SCIS violations.

---

## 12. Validation Checklist (Extended)

Before accepting a Component / Non-Component Map, verify:

* [ ] Every code section has exactly one Component Map
* [ ] No logic or behavior is described
* [ ] No dependencies are listed
* [ ] All components have stable IDs
* [ ] All non-components have stable IDs
* [ ] All entries are section-scoped
* [ ] Every CA includes a metric obligation declaration
* [ ] Every NCA includes a metric obligation declaration
* [ ] No metric implementations or thresholds appear

---

## 13. What Comes Next

Once **all Section Component Maps** are complete:

➡ Proceed to **Greenfield NCCF Maker**

That is the **first moment** when:

* Inputs
* Outputs
* Dependencies
* Constraints
* MCP integrations
* **Concrete metric definitions**

are allowed to appear.

---

## 14. Design Rationale (For Humans & LLMs)

This separation ensures:

* Deterministic planning
* No hallucinated observability
* Built-in supportability
* Safe LLM operation
* Metrics-first evolution
* Zero blind spots at scale

SCIS builds:

> **Structure first →
> Measurement obligations second →
> Logic third →
> Code last**

---


