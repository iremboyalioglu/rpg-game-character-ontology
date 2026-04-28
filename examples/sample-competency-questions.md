# Sample Competency Questions

This document lists the initial competency questions for the **RPG Game Character Ontology**. These questions describe what the ontology should be able to answer.

| ID | Competency Question | Related Classes | Related Properties |
|---|---|---|---|
| CQ1 | Which class does a character belong to? | GameCharacter, CharacterClass | hasClass |
| CQ2 | Which race does a character have? | GameCharacter, Race | hasRace |
| CQ3 | Which skills does a character have? | GameCharacter, Skill | hasSkill |
| CQ4 | Which weapon is used by a character? | GameCharacter, Weapon | usesWeapon |
| CQ5 | Which armor is worn by a character? | GameCharacter, Armor | wearsArmor |
| CQ6 | Which NPC gives a specific quest? | NonPlayerCharacter, Quest | givesQuest |
| CQ7 | Which characters participate in a specific quest? | GameCharacter, Quest | participatesInQuest |
| CQ8 | Which enemies are located in a specific location? | Enemy, Location | locatedIn |
| CQ9 | Which characters belong to the same faction? | GameCharacter, Faction | belongsToFaction |
| CQ10 | Which boss enemy appears in a certain location? | BossEnemy, Location | locatedIn |
| CQ11 | Which characters are allies of each other? | GameCharacter | allyOf |
| CQ12 | Which characters are enemies of each other? | GameCharacter | enemyOf |
| CQ13 | Which skill is required for a quest? | Quest, Skill | requiresSkill |
| CQ14 | Which item is rewarded by a quest? | Quest, Item | rewardsItem |

## Example Natural Language Answers

- `Arin` belongs to the `Warrior` class.
- `Lyra` has the `Elf` race.
- `DarkLord` has the `Fireball` skill.
- `Arin` uses the `IronSword`.
- `ElderMira` gives the `LostRelicQuest`.
- `GoblinWarrior` is located in `DarkForest`.
- `Arin` and `Lyra` belong to the `AdventurersGuild`.
