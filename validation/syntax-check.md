# Local Syntax Check

The Turtle files were parsed with `rdflib` to check basic syntax.

| File | Status | Parsed Triples |
|---|---|---:|
| `ontology/rpg-game-character-ontology.ttl` | OK | 246 |
| `shapes/rpg-game-character-shapes.ttl` | OK | 87 |

This is a syntax check, not a full SHACL validation result. Full SHACL validation should be run in SHACL Play, GraphDB, or `pyshacl`.
