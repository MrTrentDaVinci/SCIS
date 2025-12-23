# LLM friendly url: https://raw.githubusercontent.com/MrTrentDaVinci/SCIS/main/Greenfield2MapRules.md

# Greenfield2MapRules.md - Greenfield File Map Template & Rules

**Purpose**: Serves as the authoritative support template and rule set for creating file maps in Stage 0 of any new greenfield SCIS program. LLMs must copy and adapt this to produce A#p0s0f10.md (Program File Map) and ensure all files are declared before existence.


---

# SCIS Greenfield File Map Rules & Template

## Core Principle: Maps First

In SCIS greenfield development:

- **No file may exist until it is declared in a map**
- **No component may be referenced until registered**
- **No logic may be assumed until determined**

This file map is the **authoritative declaration** of all files that will exist for this program.

---

## File Map Rules

1. All files live in the root (flat repository — no subfolders)
2. Naming convention: `A#p#s#f#.<ext>`
   - `#` = program ID (e.g., A1, A2)
   - `p#` = phase index (starts at 0, increments sequentially)
   - `s#` = section within phase (usually s0)
   - `f#` = file sequence within section (10, 20, 30... for readability)
3. Phase 0 = Mapping & Declaration only (no code)
4. Phase 2 = Implementation (code files)
5. Maps must be complete before proceeding — no partial or "to be added later"

---

## File Map Template (Copy to A#p0s0f10.md)

| File Name              | Purpose                                      | Stage/Phase | Required? |
|-----------------------|----------------------------------------------|-------------|-----------|
| A#p0s0f0.md          | Program Summary & Intent                     | Stage 0     | Yes      |
| A#p0s0f10.md         | File Map (this file)                         | Stage 0     | Yes      |
| A#p0s0f20.md         | Sub-Maps / Section Breakdown                 | Stage 0     | Yes      |
| A#p0s0f30.md         | Component Registry                           | Stage 0     | Yes      |
| A#p0s0f40.md         | NCCF (Non-Code Contract Framework)           | Stage 0     | Yes      |
| A#p0s0f50.md         | Logic Map                                    | Stage 0     | Yes      |
| A#p0s0f60.md         | Dependency Map                               | Stage 0     | Yes      |
| A#p0s0f70.md         | Metrics Map                                  | Stage 0     | Yes      |
| A#p2s0f0.py          | Core Implementation Code                     | Stage 2     | Yes      |
| ...                  | ...                                          | ...         | ...      |

**Notes on Table:**
- Replace `#` with actual program ID
- Add/remove rows as needed for program scope
- All listed files MUST be created exactly as declared
- No undeclared files permitted

---

## Compliance Checklist (Before Proceeding)

- [ ] All anticipated files are listed
- [ ] Naming follows exact pattern
- [ ] No duplicates or gaps in sequencing
- [ ] Phase 0 files declared before any Phase 2
- [ ] Map aligns with intent in A#p0s0f0.md
- [ ] No references to undeclared files

---

## Next SCIS Step

After completing the File Map:

1. Create declared Stage 0 files in order
2. Proceed to Component & Non-Component declaration (A#p0s0f30.md)
3. Maintain map-first discipline

---

## End of File
