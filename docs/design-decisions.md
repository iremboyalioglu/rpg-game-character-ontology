# Design Decisions

## 1. Selected Domain

The selected domain is **RPG Game Character Ontology**. This domain was chosen because RPG games contain clearly identifiable entities such as characters, classes, races, skills, equipment, quests, factions, and locations. These entities also have meaningful relationships that can be represented in an ontology.

## 2. Scope Decision

The ontology is intentionally kept small-scale for the initial project version. It focuses on static game-world knowledge rather than gameplay programming.

### Included

- Characters
- Character classes
- Races
- Skills
- Weapons and armor
- Items
- Quests
- Locations
- Factions

### Excluded

- Real-time combat mechanics
- Damage calculation formulas
- Game engine implementation
- Graphics and animation
- Multiplayer networking
- Save/load systems
- Full inventory logic
- User interface design

This decision prevents scope creep and keeps the project suitable for an initial ontology development assignment.

## 3. TBox and ABox Design

At this stage, the ontology keeps TBox and ABox content in the same Turtle file for simplicity.

### TBox

The TBox contains the conceptual structure of the ontology:

- Classes
- Subclass relations
- Object properties
- Data properties
- Domain and range definitions

Examples:

- `PlayerCharacter` is a subclass of `GameCharacter`.
- `BossEnemy` is a subclass of `Enemy`.
- `usesWeapon` relates a `GameCharacter` to a `Weapon`.
- `givesQuest` relates a `NonPlayerCharacter` to a `Quest`.

### ABox

The ABox contains example individuals that instantiate the TBox structure.

Examples:

- `Arin` is a `PlayerCharacter`.
- `Lyra` is a `PlayerCharacter`.
- `ElderMira` is a `NonPlayerCharacter`.
- `GoblinWarrior` is an `Enemy`.
- `DarkLord` is a `BossEnemy`.
- `LostRelicQuest` is a `Quest`.

## 4. Class Hierarchy Decision

A general root class called `GameEntity` was used to group major game-world entities. `GameCharacter`, `Quest`, `Location`, `Faction`, `Skill`, `Item`, and `Equipment` are modeled as game-world concepts.

The character hierarchy was designed as:

```text
GameEntity
└── GameCharacter
    ├── PlayerCharacter
    ├── NonPlayerCharacter
    └── Enemy
        └── BossEnemy
```

Equipment and item concepts were separated because some objects are equippable, while others may simply be reward items or consumables.

## 5. Property Design

Object properties were selected according to the competency questions.

Examples:

- `hasClass` answers which class a character belongs to.
- `hasRace` answers which race a character has.
- `hasSkill` answers which skills a character has.
- `usesWeapon` answers which weapon is used by a character.
- `givesQuest` answers which NPC gives a quest.
- `locatedIn` answers where a character or entity is located.
- `belongsToFaction` answers which faction a character belongs to.

Data properties were added for literal values such as character names, levels, quest titles, location names, and item names.

## 6. Reusable Ontology Decision

For the initial version, the ontology mainly uses a custom vocabulary because the project domain is specific to an RPG game character system.

Possible reusable ontologies may be investigated in future iterations:

- Dublin Core Terms for metadata
- FOAF for people or creator metadata
- Schema.org for general creative work or game-related metadata
- Existing game ontologies if semantically appropriate

At this stage, no external ontology was reused for domain classes because the goal is to keep the model simple and understandable.

## 7. Validation and Future Extension

The current ontology is an initial draft. Future iterations may include:

- Separating TBox and ABox into different files
- Adding SHACL validation rules
- Running validation in SHACL Play or with `pyshacl`
- Writing SPARQL queries for all competency questions
- Adding more sample characters, quests, locations, factions, and skills
- Publishing generated ontology documentation
