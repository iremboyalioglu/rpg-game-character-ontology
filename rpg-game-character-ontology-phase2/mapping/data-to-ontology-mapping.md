# Data-to-Ontology Mapping

This document explains how the Phase 2 CSV dataset is mapped to the RPG Game Character Ontology v2.

## Character Data Mapping

| CSV Field | Example Value | Ontology Mapping |
|---|---:|---|
| `character_id` | `char_arin` | Used to create URI `rpg:Arin` |
| `character_name` | `Arin` | `rpg:characterName "Arin"` |
| `character_type` | `PlayerCharacter` | `rdf:type rpg:PlayerCharacter` |
| `character_class` | `Warrior` | `rpg:hasClass rpg:Warrior` |
| `race` | `Human` | `rpg:hasRace rpg:Human` |
| `level` | `12` | `rpg:level 12` |
| `skills` | `PowerStrike;ShieldBlock` | `rpg:hasSkill rpg:PowerStrike`, `rpg:hasSkill rpg:ShieldBlock` |
| `weapon` | `IronSword` | `rpg:usesWeapon rpg:IronSword` |
| `armor` | `LeatherArmor` | `rpg:wearsArmor rpg:LeatherArmor` |
| `faction` | `AdventurersGuild` | `rpg:belongsToFaction rpg:AdventurersGuild` |
| `location` | `OldVillage` | `rpg:locatedIn rpg:OldVillage` |
| `active_quest` | `LostRelicQuest` | `rpg:participatesInQuest rpg:LostRelicQuest` |

## Quest Data Mapping

| CSV Field | Example Value | Ontology Mapping |
|---|---:|---|
| `quest_id` | `quest_lost_relic` | Used to create URI `rpg:LostRelicQuest` |
| `quest_title` | `The Lost Relic` | `rpg:questTitle "The Lost Relic"` |
| `quest_giver` | `ElderMira` | `rpg:ElderMira rpg:givesQuest rpg:LostRelicQuest` |
| `required_skill` | `PowerStrike` | `rpg:LostRelicQuest rpg:requiresSkill rpg:PowerStrike` |
| `reward_item` | `HealingPotion` | `rpg:LostRelicQuest rpg:rewardsItem rpg:HealingPotion` |
| `related_location` | `DarkForest` | `rpg:LostRelicQuest rpg:locatedIn rpg:DarkForest` |

## Gameplay Event Data Mapping

| CSV Field | Example Value | Ontology Mapping |
|---|---:|---|
| `event_id` | `event_001` | Used to create URI `rpg:Event001` |
| `player_id` | `player_001` | `rpg:Player001 rpg:performsEvent rpg:Event001` |
| `character_id` | `Arin` | `rpg:Event001 rpg:eventForCharacter rpg:Arin` |
| `event_type` | `QuestCompletion` | `rdf:type rpg:QuestCompletion` |
| `related_quest` | `LostRelicQuest` | `rpg:eventRelatedQuest rpg:LostRelicQuest` |
| `used_skill` | `PowerStrike` | `rpg:eventUsesSkill rpg:PowerStrike` when event is `SkillUsage` |
| `event_count` | `7` | `rpg:eventCount 7` |
| `timestamp` | `2026-04-20T18:45:00` | `rpg:eventTimestamp "2026-04-20T18:45:00"^^xsd:dateTime` |

## Mapping Notes

- Multi-value fields are split by semicolon.
- Empty optional values are not converted into triples.
- URI names are normalized into CamelCase identifiers.
- Character behavior data is represented as instances of `GameplayEvent` subclasses.
