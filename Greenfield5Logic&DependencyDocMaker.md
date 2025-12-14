# TOON File: `Greenfield Logic & Dependency Doc Maker`

**Purpose:**
Generate the following SCIS Phase 0 & Phase 1 files for a new Greenfield project:

1. **Logic Map Explainer (`A1p0s0f8.md`)**
2. **Logic Determinization Map (`A1p0s0f9.toon`)**
3. **Program Internal Dependency Map (`A1p1s1f0.toon`)**
4. **Section-to-Section Dependency Map (`A1p1s1f1.toon`)**

---

## **Inputs (provided by the user)**

1. **`A1p0s0f0.md` – Greenfield Start / Program Summary**

   * Program objectives, operational rules, and AI guidance.

2. **`A1p0s0f1.md` – Flat File Map**

   * Complete list of sections and files with purposes.

3. **`A1p0s0f4.toon` – Component Map**

   * All components with IDs and relationships.

4. **`A1p0s0f5.toon` – Non-Component Map**

   * All helpers, utilities, scripts.

5. *(Optional for advanced logic/dependency resolution)* **`A1p1s1f2.toon` – Legacy Mapping**

   * If remaking an old program, provide mapping of legacy components.

---

## **Outputs**

1. **`A1p0s0f8.md` – Logic Map Explainer**

   * Human-readable description of program logic across components and sections.
   * Includes guidance for AI on logical flow.

2. **`A1p0s0f9.toon` – Logic Determinization Map**

   * Machine-readable, deterministic flow for components, non-components, and sections.

3. **`A1p1s1f0.toon` – Program Internal Dependency Map**

   * Maps dependencies between all components and non-components in the program.

4. **`A1p1s1f1.toon` – Section-to-Section Dependency Map**

   * Maps dependencies between program sections (s#), capturing flow across sections.

---

## **LLM Instructions**

1. **Read Inputs:**

   * Parse `f0` for program objectives, constraints, and AI guidance.
   * Use `f1` to determine sections, files, and structural hierarchy.
   * Use `f4` and `f5` for complete component and non-component inventories.

2. **Generate Logic Maps:**

   * Identify logical sequence, loops, conditionals, and component interactions.
   * Write human-readable logic in `A1p0s0f8.md`.
   * Convert the logical flow into deterministic machine-readable format (`A1p0s0f9.toon`).

3. **Generate Dependency Maps:**

   * Create `A1p1s1f0.toon` showing component-to-component and component-to-non-component dependencies.
   * Create `A1p1s1f1.toon` showing section-to-section dependencies across the program.
   * Ensure all IDs from components, non-components, and sections are referenced correctly.

4. **Cross-Validation:**

   * Ensure that the logic maps and dependency maps are consistent with one another.
   * Highlight any potential circular dependencies or conflicts.

---

## **Usage Notes**

* Only **Phase 0 files (f0, f1, f4, f5)** are required to generate all outputs.
* Can be re-run after updates to components, non-components, or program structure.
* Supports deterministic AI generation and safe modification in future iterations.
* Optional: Include legacy mapping if remaking an old program for cross-reference.
