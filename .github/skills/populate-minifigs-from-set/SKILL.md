---
name: populate-minifigs-from-set
description: 'Populate minifigs.json from a LEGO set number, including standard sets and Collectible Minifigures (CMF) series. Use when asked to add figures from a set, import all minifigs from a set, or add CMF series entries. Preserves repository conventions: no auto-added date values, CMF names from sub-set descriptions, and common keyword style.'
argument-hint: 'Provide set number and optional notes about source style or keyword preferences.'
user-invocable: true
---

# Populate Minifigs From Set

Add one or more entries to minifigs.json from a LEGO set while matching this repository's conventions.

## Use This For
- Adding all minifigures from a regular LEGO set
- Adding all figures from a CMF series or random-pack set (for example 71052)
- Filling in item IDs, set numbers, names, and keyword lists in existing style

## Repository Rules
- Never add date values to dates. Keep new entries as "dates": [].
- Match existing JSON formatting and key order used in nearby entries.
- Prefer set/sub-set naming when applicable (especially CMF), not generic minifig page titles.
- Use common, searchable keywords similar to existing CMF and theme entries.
- Do not alter unrelated records.

## Procedure
1. Inspect current patterns in minifigs.json.
2. Determine whether the request is:
- A standard set with multiple minifigs
- A CMF series where each sub-set maps to one minifig
3. Gather source data:
- Set and sub-set names
- Minifig item IDs (for example col###, sh####, sw####)
- Any aliases useful for keywords
4. Build entry objects:
- Required fields: id, name, keywords, dates, item, set
  - For keywords, be sure to include the following, but only if applicable:
    - original media (e.g. "movie", "tv", "video game")
    - franchise (e.g. "Star Wars", "Marvel")
    - and category terms (e.g. "collectible minifigures", "series 29")
    - name of character (if it has one)
    - Other high-level useful groupings
    - included accessories that are actually included in the set for the minifig.
  - Prefer concise keyword sets over exhaustive extraction.
  - Do not add speculative or noisy keywords (for example text that isn't on the minifig) unless they are likely to appear on other minifigures.
- Typical optional fields: actor, style, notes
- For this repo, set dates to an empty array for new entries
5. Insert entries near the end of data without reformatting the whole file.
6. Validate JSON and schema compatibility.
7. Report exactly what was added and where.

## CMF Series Guidance
- Use each sub-set title as the base name.
- If a sub-set has alternate wording (for example football/soccer), keep your preferred label in name and include both terms in keywords when useful.
- Include series keyword and role/theme keywords.
- Keep keyword lists practical and consistent with nearby collectible entries.

## Quality Checks
- No duplicate id values (generate a new UUID v4 for each new entry)
- No trailing commas or malformed JSON
- No accidental date insertion
- Item IDs correspond to the selected set/sub-set

## References
- Pattern notes: [CMF and Set Conventions](./references/conventions.md)
