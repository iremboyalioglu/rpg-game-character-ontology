# RPG Game Character Ontology

## Project Overview

This project is a small-scale ontology development project for the **Knowledge Engineering and Ontologies** course.  
The selected domain is an RPG game character system. The ontology represents core knowledge about game characters, their roles, races, classes, skills, equipment, quests, factions, and locations.

The project is designed as an initial ontology draft and will be extended in future iterations based on feedback.

## Group Information

This project is developed by a group of two students.

### Group Members

- İrem Boyalıoğlu - 200316003
- Yunus Erdem Ocak - 200316053

## Domain

The selected domain is:

**RPG Game Character Ontology**

The ontology focuses on a role-playing game environment where characters can have classes, races, skills, weapons, armor, quests, factions, and locations.

## Purpose

The purpose of this ontology is to represent and organize knowledge about RPG game characters and their relationships with game-world entities. It aims to provide a structured model that can answer questions such as:

- Which class does a character belong to?
- Which skills does a character have?
- Which weapon is used by a character?
- Which NPC gives a specific quest?
- Which enemies are located in a specific location?

## Scope

### Included in Scope

The ontology includes the following core concepts:

- Game characters
- Player characters
- Non-player characters
- Enemies and boss enemies
- Character classes
- Races
- Skills
- Weapons and armor
- Items
- Quests
- Locations
- Factions

### Out of Scope

The ontology does not cover:

- Real-time combat calculations
- Game engine implementation details
- Graphics and animation systems
- Multiplayer networking
- Save/load systems
- Full inventory mechanics
- Damage formulas or balancing algorithms
- User interface design

## Ontology Format

The initial ontology is written in RDF/Turtle format and uses OWL vocabulary.

Ontology file:

```text
ontology/rpg-game-character-ontology.ttl
```

At this stage, the TBox and ABox are kept in the same Turtle file for simplicity:

- **TBox**: classes, subclass hierarchy, object properties, data properties, domain/range definitions.
- **ABox**: example individuals such as `Arin`, `Lyra`, `ElderMira`, `GoblinWarrior`, `DarkLord`, `IronSword`, `DarkForest`, and `LostRelicQuest`.

## Initial Core Classes

The current ontology includes the following main classes:

- `GameEntity`
- `GameCharacter`
- `PlayerCharacter`
- `NonPlayerCharacter`
- `Enemy`
- `BossEnemy`
- `CharacterClass`
- `Race`
- `Skill`
- `Equipment`
- `Weapon`
- `Armor`
- `Item`
- `ConsumableItem`
- `Quest`
- `Location`
- `Faction`

## Initial Object Properties

The initial ontology includes relationships such as:

- `hasClass`
- `hasRace`
- `hasSkill`
- `usesWeapon`
- `wearsArmor`
- `belongsToFaction`
- `locatedIn`
- `givesQuest`
- `participatesInQuest`
- `allyOf`
- `enemyOf`
- `requiresSkill`
- `rewardsItem`

## Example Instances

The initial ontology includes example individuals such as:

- `Arin` - a player character
- `Lyra` - a player character
- `ElderMira` - a non-player character
- `GoblinWarrior` - an enemy
- `DarkLord` - a boss enemy
- `IronSword` - a weapon
- `Fireball` - a skill
- `DarkForest` - a location
- `LostRelicQuest` - a quest

## Repository Structure

```text
rpg-game-character-ontology/
├── README.md
├── ontology/
│   └── rpg-game-character-ontology.ttl
├── docs/
│   ├── ORSD-draft.docx
│   ├── ORSD-draft.md
│   ├── design-decisions.md
├── examples/
│   └── sample-competency-questions.md
├── queries/
│   └── competency-questions.sparql
├── shapes/
│   └── rpg-game-character-shapes.ttl
└── validation/
    └── shacl-play-instructions.md
    └── syntax-check.md
```

## Current Progress

- Domain selected: RPG game character system
- Group information added
- Scope and purpose defined
- Initial classes and properties created
- Example instances added
- Draft ORSD specification document prepared
- Design decisions documented
- Competency questions listed
- Initial SPARQL queries prepared
- Initial SHACL shapes prepared for future validation

## Planned Future Work

Future iterations may include:

- Separating TBox and ABox into different files
- Expanding the class hierarchy
- Adding more restrictions and cardinality constraints
- Running SHACL validation and documenting the results
- Executing SPARQL queries against the ontology in GraphDB or another RDF tool
- Adding more example characters, quests, factions, and locations
- Publishing ontology documentation on GitHub Pages

## License

This project is licensed under the MIT License.
