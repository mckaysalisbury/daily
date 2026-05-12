# CMF and Set Conventions

Use these conventions when populating entries in minifigs.json.

## Entry Shape
Typical key order used by this repository:
1. id
2. name
3. keywords
4. actor/style/rpg/notes (only when applicable)
5. item or part or gear
6. set
7. dates

## Dates
- New entries should use:

```json
"dates": []
```

- Do not auto-fill dates.

## Names
- Prefer set or sub-set description names, especially for CMF series.
- If a public alias exists, include alias terms in keywords.

## Keywords
- Include category terms that match nearby entries (for example "collectible minifigures", "series 29").
- Include obvious object/role tags (for example "witch", "goalkeeper", "robot").
- Add close synonyms when they improve searchability.

## Source Strategy
When a set page does not directly list minifig inventory:
1. Use sub-set pages for CMF series names.
2. Cross-check item IDs from reliable catalog sources.
3. If any item ID is uncertain, stop and ask before writing partial guesses.

## Safety
- Preserve unrelated records.
- Avoid bulk formatting changes.
- Validate syntax after edits.
