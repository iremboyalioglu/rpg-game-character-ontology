# Validation Results - Phase 2

## Syntax Check

The ontology file `ontology/rpg-game-character-ontology-v2.ttl` was parsed with RDFLib as Turtle syntax.

Result:

```text
Turtle syntax check: PASSED
```

The SHACL file `shapes/rpg-game-character-shapes-v2.ttl` was also parsed as Turtle syntax.

Result:

```text
SHACL syntax check: PASSED
```

## SHACL Validation

The RPG Game Character Ontology v2 was validated using SHACL Play.

### Validation Setup

- Data graph: `ontology/rpg-game-character-ontology-v2.ttl`
- Shapes graph: `shapes/rpg-game-character-shapes-v2.ttl`
- Validation tool: SHACL Play
- Number of evaluated shapes: 5

During validation, the `Avoid resolving targets` option was enabled. This was done to focus the validation process on the explicitly defined SHACL shapes and avoid additional warnings about RDF subjects that were not directly targeted by any shape.

### Validated Shape Areas

The SHACL shapes validate the following ontology areas:

- Game characters
- Quests
- Player profiles
- Gameplay events
- Recommendations

## Validation Result

The validation result was conformant.

```text
Validation results of 5 shapes
Valid
Data is conformant!
```

No critical SHACL violations were detected for the defined SHACL constraints.

The generated Turtle validation report contains the following result:

```ttl
sh:conforms true
```

The downloaded validation report is stored in:

```text
validation/validation-report-v2.ttl
```

## Notes

An initial validation attempt without disabling target resolving produced warnings such as:

```text
Subject of a triple was not validated by any shape
```

These warnings were caused by RDF resources that were present in the ontology but not directly targeted by the selected SHACL shapes. Since the purpose of this validation step was to test the explicitly defined Phase 2 constraints, validation was repeated with target resolving disabled.

The final SHACL Play result confirmed that the ontology conforms to the five defined SHACL shapes.
