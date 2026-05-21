---
description: "Populate minifigs.json from a LEGO set number using repository conventions"
name: "Populate Minifigs From Set"
argument-hint: "Set: 71052 | Notes: optional"
agent: "agent"
---

Use the workflow in [add-minifigs-from-set skill](../skills/add-minifigs-from-set/SKILL.md) to add minifig entries into [minifigs.json](../../minifigs.json).

Input format:
- `Set: <set-number>`
- Optional: `Notes: <preferences or constraints>`

Execution requirements:
1. Parse the set number from the `Set:` field.
2. Populate the minifigs.json file for all minifig entries in that set.
3. If any of the minifigs (by item ID) already exist in the file, skip them and do not modify existing records, but make a note of which ones were skipped in the final report.
4. Follow all repository conventions from the skill and its references.
5. Never auto-add date values; new entries must use `"dates": []`.
6. For CMF sets, use sub-set description names and common searchable keywords.
7. Validate JSON before finishing.

Output requirements:
1. Summarize exactly which entries were added.
2. Include the file location updated.
3. Note any unresolved data ambiguity before writing guesses.
