# SHACL Play Validation Instructions

This folder contains notes for validating the ontology with SHACL Play.

## Files to Use

Upload these two files to a SHACL validator such as SHACL Play:

```text
ontology/rpg-game-character-ontology.ttl
shapes/rpg-game-character-shapes.ttl
```

## Purpose

The SHACL file defines initial validation rules for the RPG Game Character Ontology. These rules check whether important information exists for characters, quests, enemies, and NPCs.

## Example Checks

- Every game character should have a character name.
- Every game character should have a level value.
- Every game character should have a race.
- Every player character should have a class.
- Every player character should have at least one skill.
- Every NPC in the sample data should give at least one quest.
- Every quest should have a title.
- Every quest should be connected to at least one required skill and one reward item.

## Note

The current repository includes SHACL shapes, but the project should only be described as **SHACL-validated** after the shapes are executed in a validator and the results are documented.
