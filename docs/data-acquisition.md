# Data Acquisition - Phase 2

## Data Sources

The current version of the project uses a manually prepared synthetic RPG dataset. The dataset was created specifically for the course project because the ontology represents a fictional small-scale RPG game world rather than an existing commercial game.

The data files are:

- `data/sample-rpg-characters.csv`
- `data/sample-rpg-quests.csv`
- `data/sample-gameplay-events.csv`

The dataset includes fictional characters, quests, skills, equipment, factions, locations, players, and gameplay events. This controlled data source allows us to test whether the ontology can represent the intended concepts without the noise and licensing issues of real game data.

## Data Format

The data is stored in CSV format. CSV was selected because it is simple, human-readable, easy to edit, and easy to map to RDF triples.

### Character Dataset

The character dataset includes fields such as:

- `character_id`
- `character_name`
- `character_type`
- `character_class`
- `race`
- `level`
- `skills`
- `weapon`
- `armor`
- `faction`
- `location`
- `active_quest`

### Quest Dataset

The quest dataset includes fields such as:

- `quest_id`
- `quest_title`
- `quest_giver`
- `required_skill`
- `reward_item`
- `related_location`
- `difficulty`

### Gameplay Event Dataset

The gameplay event dataset includes fields such as:

- `event_id`
- `player_id`
- `character_id`
- `event_type`
- `related_quest`
- `used_skill`
- `event_count`
- `timestamp`

## Collection Methodology

The dataset was created manually based on common RPG game structures. The following steps were followed:

1. Identify the main entities required by the competency questions.
2. Create representative fictional characters, quests, skills, weapons, factions, and locations.
3. Add player behavior examples such as quest completion and skill usage events.
4. Store the data in CSV files.
5. Map CSV fields to ontology classes, object properties, and data properties.
6. Convert the representative examples into RDF individuals in the v2 ontology file.

## Preprocessing Steps

The preprocessing steps were simple because the data is synthetic and controlled. The following checks were applied conceptually:

- Character and quest names were normalized into URI-friendly identifiers.
- Empty optional fields, such as NPC weapon or armor, were allowed only when the ontology did not require them.
- Duplicate character and quest records were avoided.
- Multi-value fields such as `skills` were separated using semicolons.
- Character types were mapped to ontology classes such as `PlayerCharacter`, `Enemy`, `BossEnemy`, or `NonPlayerCharacter`.
- Numeric fields such as `level` and `event_count` were represented with integer datatypes.
- Timestamps were represented with `xsd:dateTime`.

## Mapping to Ontology Concepts

The CSV fields were mapped to ontology concepts as follows:

| Dataset Field | Ontology Mapping |
|---|---|
| `character_name` | `rpg:characterName` |
| `character_type` | `rpg:PlayerCharacter`, `rpg:Enemy`, `rpg:BossEnemy`, or `rpg:NonPlayerCharacter` |
| `character_class` | `rpg:CharacterClass` via `rpg:hasClass` |
| `race` | `rpg:Race` via `rpg:hasRace` |
| `skills` | `rpg:Skill` via `rpg:hasSkill` |
| `weapon` | `rpg:Weapon` via `rpg:usesWeapon` |
| `armor` | `rpg:Armor` via `rpg:wearsArmor` |
| `faction` | `rpg:Faction` via `rpg:belongsToFaction` |
| `location` | `rpg:Location` via `rpg:locatedIn` |
| `active_quest` | `rpg:Quest` via `rpg:participatesInQuest` |
| `event_type` | `rpg:QuestCompletion` or `rpg:SkillUsage` |
| `related_quest` | `rpg:eventRelatedQuest` or `rpg:completedQuest` |
| `used_skill` | `rpg:eventUsesSkill` |
| `timestamp` | `rpg:eventTimestamp` |

## Data Quality and Limitations

The main advantage of the dataset is that it is consistent, explainable, and easy to map to the ontology. However, it is small and synthetic. Therefore, it does not represent the full complexity of real RPG games. Future versions may use public game datasets, game wiki pages, or LLM-assisted extraction from character descriptions to populate a larger knowledge graph.
