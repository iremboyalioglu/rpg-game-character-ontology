# Research Integration - Phase 2

## Selected Study

**Ontology Population using LLMs** by Norouzi, Barua, Christou, Gautam, Eells, Hitzler, and Shimizu (2024) was selected from the Week 11 materials.

## Why This Study Was Selected

The study was selected because Phase 2 of the RPG Game Character Ontology requires a stronger data acquisition and ontology population component. Our project contains structured entities such as characters, character classes, races, skills, weapons, quests, factions, and locations. These entities can be populated manually from CSV files in the current version, but the same process could later be supported by LLM-based extraction from natural language game descriptions, quest logs, or character profiles.

The selected study is directly relevant because it investigates how Large Language Models can be guided by a modular ontology to extract triples for knowledge graph population. The paper reports that, when a modular ontology is supplied as prompt guidance, LLMs can extract a high percentage of expected triples compared with a ground truth dataset. This supports the idea that ontology-guided prompting can be used as a semi-automatic population method.

## Relevance to Our Project

In our RPG ontology, natural language descriptions such as "Arin is a level 12 Human Warrior who uses an Iron Sword and belongs to the Adventurers Guild" can be converted into RDF statements:

- `rpg:Arin rdf:type rpg:PlayerCharacter`
- `rpg:Arin rpg:hasClass rpg:Warrior`
- `rpg:Arin rpg:hasRace rpg:Human`
- `rpg:Arin rpg:usesWeapon rpg:IronSword`
- `rpg:Arin rpg:belongsToFaction rpg:AdventurersGuild`

This matches the selected paper's central idea: use the ontology schema to constrain and guide extraction into triples.

## Integration Plan

The selected study will be integrated into the project at the **data processing and ontology population layer**.

### Proposed Architecture

1. **Input Layer**: CSV files and short natural language descriptions of RPG characters, quests, and gameplay events.
2. **Extraction Layer**: In the current version, values are manually extracted from the CSV files. In a future version, an LLM can extract entities and relations from text.
3. **Ontology Mapping Layer**: Extracted fields are mapped to ontology classes and properties such as `GameCharacter`, `Quest`, `Skill`, `hasClass`, `hasSkill`, and `participatesInQuest`.
4. **Knowledge Graph Layer**: RDF triples are loaded into an ontology file or a triple store such as GraphDB.
5. **Validation Layer**: SHACL shapes are used to check required fields such as character name, level, quest title, and event timestamp.
6. **Query/QA Layer**: SPARQL queries retrieve structured answers, and an LLM may later be used to translate natural language questions into SPARQL.

## Expected Impact on Ontology Design

The research integration influenced the v2 ontology in three ways:

1. It encouraged the addition of a documented data acquisition and mapping layer.
2. It motivated the creation of sample CSV datasets that can be transformed into ontology individuals.
3. It guided the addition of player behavior-related classes such as `GameplayEvent`, `QuestCompletion`, and `SkillUsage`, because these can be extracted from gameplay logs.

## Limitations

The current Phase 2 implementation does not perform fully automated LLM extraction. Instead, it documents a realistic integration plan and provides manually prepared sample datasets. This approach is appropriate for the current project stage because it keeps the ontology small, understandable, and verifiable.
