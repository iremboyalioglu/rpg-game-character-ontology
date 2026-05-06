# Ontology Requirements Specification Document - Version 2

## Author(s)

İrem Boyalıoğlu - 200316003  
Yunus Erdem Ocak - 200316053

## Creation Date

April 2026

## Modification Date

May 2026

## Project

Knowledge Engineering and Ontologies Course Project

## Version

Version 2 (v2)

---

## 1. Purpose

The purpose of this ontology is to represent and organize knowledge about characters and player behavior in a small-scale role-playing game environment. Version 1 focused on RPG characters and their relationships with classes, races, skills, equipment, quests, factions, and locations. Version 2 extends the ontology by adding player profiles, gameplay events, quest completion, skill usage, play styles, and recommendation-related concepts.

The ontology should support questions such as which class a character belongs to, which skills a character has, which NPC gives a quest, which enemies are located in a specific area, which player controls which character, which quests a player completed, and which recommendations are generated for a player.

## 2. Scope

The scope is limited to a small-scale RPG game character, quest, and player behavior knowledge graph. It focuses on static and semi-structured game-world knowledge rather than game engine implementation.

### In Scope

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
- Player profiles
- Gameplay events
- Quest completion events
- Skill usage events
- Play styles
- Simple recommendation examples

### Out of Scope

- Real-time combat mechanics
- Damage calculation formulas
- Game engine implementation
- Graphics and animation systems
- Multiplayer networking
- Save/load system implementation
- Full inventory management logic
- User interface design
- Actual machine learning model training

## 3. Implementation Language

The ontology is implemented using OWL/RDF concepts and represented in Turtle (`.ttl`) format.

Current ontology file:

```text
ontology/rpg-game-character-ontology-v2.ttl
```

## 4. Intended End-Users

- Knowledge Engineering and Ontologies course instructors
- Students developing and reviewing ontology projects
- Game designers who need a conceptual model of RPG character systems
- Ontology developers interested in modeling game-world knowledge
- Developers who may later use the ontology as a basis for a game knowledge graph or ontology-based question answering system

## 5. Intended Uses

- Representing RPG game character knowledge in a structured way
- Describing relationships between characters, classes, races, skills, items, quests, factions, and locations
- Representing simple player behavior events such as quest completion and skill usage
- Supporting SPARQL queries over character, quest, and player behavior data
- Supporting future natural-language-to-SPARQL or knowledge-grounded question answering
- Supporting SHACL-based validation of required data quality constraints
- Providing a reusable semantic model for a small RPG game world

## 6. Ontology Requirements

### Non-Functional Requirements

- The ontology must be small-scale and understandable for a course project.
- All custom classes and properties should have clear English labels and comments.
- The ontology must be written in RDF/Turtle format.
- The ontology must be documented in a GitHub repository.
- The ontology should be extendable in future iterations.
- The ontology should avoid unnecessary implementation-specific game engine details.
- The ontology should support SPARQL querying and SHACL validation.

### Functional Requirements / Competency Questions

| ID | Competency Question | Expected Elements |
|---|---|---|
| CQ1 | Which class does a character belong to? | GameCharacter, CharacterClass, hasClass |
| CQ2 | Which race does a character have? | GameCharacter, Race, hasRace |
| CQ3 | Which skills does a character have? | GameCharacter, Skill, hasSkill |
| CQ4 | Which weapon is used by a character? | GameCharacter, Weapon, usesWeapon |
| CQ5 | Which NPC gives a specific quest? | NonPlayerCharacter, Quest, givesQuest |
| CQ6 | Which enemies are located in a specific location? | Enemy, Location, locatedIn |
| CQ7 | Which characters belong to the same faction? | GameCharacter, Faction, belongsToFaction |
| CQ8 | Which item is rewarded by a quest? | Quest, Item, rewardsItem |
| CQ9 | Which player controls which character? | Player, PlayerCharacter, controlsCharacter |
| CQ10 | Which quests has a player completed? | Player, QuestCompletion, completedQuest |
| CQ11 | Which skills are frequently used in gameplay events? | SkillUsage, Skill, eventUsesSkill, eventCount |
| CQ12 | What play style is assigned to a player? | Player, PlayStyle, hasPlayStyle |
| CQ13 | Which recommendations are generated for a player? | Recommendation, Player, recommendedQuest, recommendedSkill |

## 7. Pre-Glossary of Terms

### Terms from Competency Questions

- **GameCharacter**: A general character entity in the RPG game world.
- **PlayerCharacter**: A character controlled by the player.
- **NonPlayerCharacter**: A character controlled by the game system.
- **Enemy**: A hostile character that can oppose player characters.
- **BossEnemy**: A stronger enemy character usually associated with an important challenge.
- **CharacterClass**: A role or profession of a character, such as Warrior, Mage, Ranger, or Sage.
- **Race**: The species or ancestry of a character.
- **Skill**: An ability that can be used by a character.
- **Quest**: A mission or task in the game world.
- **Location**: A place or area in the game world.
- **Faction**: A group or organization that characters may belong to.
- **Player**: A player profile that controls one or more player characters.
- **GameplayEvent**: An activity performed by a player or character.
- **QuestCompletion**: A gameplay event representing completion of a quest.
- **SkillUsage**: A gameplay event representing use of a skill.
- **PlayStyle**: A behavior category assigned to a player.
- **Recommendation**: A suggested quest or skill for a player.

### Terms from Answers / Example Individuals

- **Arin**: Example player character.
- **Lyra**: Example player character.
- **Kael**: Example player character.
- **ElderMira**: Example non-player character who gives quests.
- **GoblinWarrior**: Example enemy character.
- **DarkLord**: Example boss enemy.
- **LostRelicQuest**: Example quest.
- **ShadowGateQuest**: Example quest.
- **Player001**: Example player profile.
- **Event001**: Example quest completion event.
- **Recommendation001**: Example recommendation instance.

## 8. Changes Compared to Version 1

- Added player behavior-related concepts.
- Added `Player`, `GameplayEvent`, `QuestCompletion`, `SkillUsage`, `CharacterProgression`, `PlayStyle`, and `Recommendation` classes.
- Added player and event-related properties such as `controlsCharacter`, `performsEvent`, `eventForCharacter`, `completedQuest`, and `hasPlayStyle`.
- Added sample CSV datasets for characters, quests, and gameplay events.
- Added data-to-ontology mapping documentation.
- Added updated SPARQL queries for v2 competency questions.
- Added updated SHACL shapes for v2 validation.
- Added ontology metadata for future Widoco documentation.
