# Ontology Usage and Expansion Methodology - Phase 2

## Existing Ontologies

The current version of the RPG Game Character Ontology mainly uses a custom vocabulary. No domain-specific external game ontology was directly reused in the v2 implementation.

The ontology still uses standard Semantic Web vocabularies:

- RDF (`rdf:`)
- RDFS (`rdfs:`)
- OWL (`owl:`)
- XML Schema Datatypes (`xsd:`)
- Dublin Core Terms (`dc:`) for ontology metadata
- VANN (`vann:`) for preferred namespace metadata

These vocabularies are used for class/property definitions, labels, comments, datatypes, and ontology metadata.

## Reason for Limited Domain Ontology Reuse

The project models a small fictional RPG game world. Public ontologies for commercial game worlds may be too specific, too large, or semantically different from our intended scope. Therefore, the initial domain model was kept custom and lightweight.

In future iterations, external vocabularies such as Schema.org, Dublin Core, FOAF, Wikidata, or game-related ontologies may be investigated for reusable metadata, agent, organization, or creative work concepts.

## Expansion Methodology

The v2 expansion follows a lightweight version of Modular Ontology Modeling (MOMo) and competency-question-driven design.

### 1. Competency Question Review

The Phase 1 competency questions focused on characters, classes, skills, weapons, quests, locations, and factions. Phase 2 adds questions related to player behavior, gameplay events, play styles, and recommendations.

### 2. Module Identification

The ontology is organized conceptually into modules:

- Character module
- Quest module
- Item and equipment module
- Location and faction module
- Player behavior module
- Recommendation module

### 3. TBox Extension

The TBox was extended with new classes:

- `Player`
- `GameplayEvent`
- `QuestCompletion`
- `SkillUsage`
- `CharacterProgression`
- `PlayStyle`
- `Recommendation`

New properties were added:

- `controlsCharacter`
- `performsEvent`
- `eventForCharacter`
- `eventRelatedQuest`
- `eventUsesSkill`
- `completedQuest`
- `hasPlayStyle`
- `recommendationForPlayer`
- `recommendedQuest`
- `recommendedSkill`

### 4. ABox Extension

The ABox was extended with sample player profiles, gameplay events, play style categories, and recommendation examples.

### 5. Validation Planning

The SHACL shapes were updated to validate required fields for game characters, quests, players, gameplay events, and recommendations.

## Version 2 Changes Compared to Version 1

- Added player behavior modeling.
- Added gameplay events such as quest completion and skill usage.
- Added play style and recommendation concepts.
- Added sample CSV datasets.
- Added data-to-ontology mapping documentation.
- Added updated SPARQL competency queries.
- Added updated SHACL shapes.
- Added ontology metadata for documentation and future Widoco generation.
