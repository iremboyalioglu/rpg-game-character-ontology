# Ontology Requirements Specification Document

## Author(s)

- İrem Boyalıoğlu - 200316003
- Yunus Erdem Ocak - 200316053

## Creation Date

April 2026

## Modification Date

April 2026

## Project(s) Related

Knowledge Engineering and Ontologies Course Project

---

## 1. Purpose

The purpose of this ontology is to represent and organize knowledge about characters in a small-scale role-playing game environment.

The ontology models game characters and their relationships with character classes, races, skills, equipment, quests, factions, and locations.

It should support questions such as which class a character belongs to, which skills a character has, which NPC gives a quest, and which enemies are located in a specific area.

---

## 2. Scope

The scope is limited to a small-scale RPG game character and quest system. It focuses on static game-world knowledge rather than game engine implementation.

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

### Out of Scope

- Real-time combat mechanics
- Damage calculation formulas
- Game engine implementation
- Graphics and animation systems
- Multiplayer networking
- Save/load system implementation
- Full inventory management logic
- User interface design

---

## 3. Implementation Language

The ontology is implemented using OWL/RDF concepts and represented in Turtle (`.ttl`) format.

Initial ontology file:

```text
ontology/rpg-game-character-ontology.ttl
```

---

## 4. Intended End-Users

- Knowledge Engineering and Ontologies course instructors
- Students developing and reviewing ontology projects
- Game designers who need a conceptual model of RPG character systems
- Ontology developers interested in modeling game-world knowledge
- Developers who may later use the ontology as a basis for a game knowledge base

---

## 5. Intended Uses

- Representing RPG game character knowledge in a structured way.
- Describing relationships between characters, classes, races, skills, items, quests, factions, and locations.
- Supporting simple queries about game-world entities.
- Serving as a foundation for future ontology development iterations.
- Supporting documentation and explanation of a small RPG game world.
- Providing a reusable semantic model for game character and quest data.

---

## 6. Ontology Requirements

### Non-Functional Requirements

- Be small-scale and understandable for an initial course project.
- Use clear and meaningful class names.
- Use clear and meaningful property names.
- Be written in a standard ontology-compatible format such as RDF/Turtle.
- Be documented in a GitHub repository.
- Be extendable in future iterations.
- Avoid unnecessary implementation-specific game engine details.
- Remain focused on semantic representation rather than gameplay programming.

### Functional Requirements: Competency Questions

| ID | Competency Question | Expected Elements |
|---|---|---|
| CQ1 | Which class does a character belong to? | GameCharacter, CharacterClass, hasClass |
| CQ2 | Which race does a character have? | GameCharacter, Race, hasRace |
| CQ3 | Which skills does a character have? | GameCharacter, Skill, hasSkill |
| CQ4 | Which weapon is used by a character? | GameCharacter, Weapon, usesWeapon |
| CQ5 | Which armor is worn by a character? | GameCharacter, Armor, wearsArmor |
| CQ6 | Which NPC gives a specific quest? | NonPlayerCharacter, Quest, givesQuest |
| CQ7 | Which characters participate in a specific quest? | GameCharacter, Quest, participatesInQuest |
| CQ8 | Which enemies are located in a specific location? | Enemy, Location, locatedIn |
| CQ9 | Which characters belong to the same faction? | GameCharacter, Faction, belongsToFaction |
| CQ10 | Which boss enemy appears in a certain location? | BossEnemy, Location, locatedIn |
| CQ11 | Which characters are allies of each other? | GameCharacter, allyOf |
| CQ12 | Which characters are enemies of each other? | GameCharacter, enemyOf |
| CQ13 | Which skill is required for a quest? | Quest, Skill, requiresSkill |
| CQ14 | Which item is rewarded by a quest? | Quest, Item, rewardsItem |

---

## 7. Pre-Glossary of Terms

### Terms from Competency Questions

- **GameCharacter**: A general character entity in the RPG game world.
- **PlayerCharacter**: A character controlled by the player.
- **NonPlayerCharacter**: A character controlled by the game system.
- **Enemy**: A hostile character that can oppose player characters.
- **BossEnemy**: A stronger enemy character usually associated with an important challenge.
- **CharacterClass**: A role or profession of a character, such as Warrior, Mage, or Ranger.
- **Race**: The species or ancestry of a character, such as Human, Elf, or Orc.
- **Skill**: An ability that can be used by a character.
- **Weapon**: Equipment used by a character for attacking.
- **Armor**: Equipment used by a character for protection.
- **Quest**: A mission or task in the game world.
- **Location**: A place or area in the game world.
- **Faction**: A group or organization that characters may belong to.

### Terms from Answers

- **Arin**: Example player character.
- **Lyra**: Example player character.
- **ElderMira**: Example non-player character who gives a quest.
- **GoblinWarrior**: Example enemy character.
- **DarkLord**: Example boss enemy.
- **IronSword**: Example weapon.
- **Fireball**: Example skill.
- **DarkForest**: Example location.
- **LostRelicQuest**: Example quest.
- **AdventurersGuild**: Example faction.

### Objects

- Arin - PlayerCharacter
- Lyra - PlayerCharacter
- ElderMira - NonPlayerCharacter
- GoblinWarrior - Enemy
- DarkLord - BossEnemy
- Warrior - CharacterClass
- Mage - CharacterClass
- Human - Race
- Elf - Race
- IronSword - Weapon
- LeatherArmor - Armor
- Fireball - Skill
- PowerStrike - Skill
- HealingPotion - Item
- LostRelicQuest - Quest
- DarkForest - Location
- OldVillage - Location
- AdventurersGuild - Faction
- ShadowCult - Faction
