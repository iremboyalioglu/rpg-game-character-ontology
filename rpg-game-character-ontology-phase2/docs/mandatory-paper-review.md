# Mandatory Paper Review - Phase 2

## Reviewed Paper

Fernandez, F. M. H., Ramana, T. V., Shabana, M., Kannagi, V., & Nalini, M. (2023). *Personalized ontology and deep training tree-based optimal gated recurrent unit-recurrent neural network for prediction of students' behavior*. Concurrency and Computation: Practice and Experience, 35, e7420. https://doi.org/10.1002/cpe.7420

## Core Methodology

The paper proposes a personalized digital library framework that combines ontology modeling and machine learning for predicting student behavior. The ontology component is created with the Protégé editor and is used to organize concepts related to students, digital library resources, learning objects, and user needs. The system aims to support personalization by representing domain knowledge and user-related information in a structured form.

The prediction component uses a gated recurrent unit-recurrent neural network (GRU-RNN) combined with a deep training tree (DTT). The DTT is introduced to reduce the vanishing gradient problem that can occur in recurrent neural networks. The model is further optimized using a black widow optimization algorithm to tune the network weights. The predicted behavioral categories include cognitive behavior, learning speed behavior, sedentary behavior, and aggressive behavior.

The overall methodology can be summarized as follows:

1. Acquire domain knowledge related to personalized digital library usage.
2. Build and organize the ontology with Protégé.
3. Represent user needs, learning objects, and behavioral concepts as ontology elements.
4. Use GRU-RNN with DTT to predict behavior patterns.
5. Optimize model weights using black widow optimization.
6. Evaluate the model using metrics such as accuracy, precision, recall, F-score, and loss.

## Key Contributions

The key contributions of the paper are:

- It combines ontology engineering with deep learning for personalization.
- It uses Protégé to model personalized digital library services and user needs.
- It proposes a GRU-RNN + DTT approach for predicting different behavioral traits.
- It uses black widow optimization to improve network training and address convergence and overfitting issues.
- It evaluates the model using standard machine learning metrics such as accuracy, precision, recall, F-score, and loss.

## How Similar Ideas Could Be Adapted to Our Project

Although the mandatory paper focuses on student behavior in digital libraries, its ideas can be adapted to the RPG Game Character Ontology by replacing the educational behavior domain with the player behavior domain.

| Paper Concept | Adaptation in RPG Project |
|---|---|
| Student behavior | Player behavior |
| Digital library resource | Quest, item, skill, or location |
| Learning object | Gameplay entity or quest objective |
| Personalized ontology | Player-specific RPG knowledge graph |
| Student behavior prediction | Play style or quest/skill recommendation |
| Recommendation system | Quest, skill, or item recommendation |

For Phase 2, we adapted this idea conceptually by extending the ontology with `Player`, `GameplayEvent`, `QuestCompletion`, `SkillUsage`, `PlayStyle`, and `Recommendation`. These classes allow the knowledge graph to represent how players interact with the RPG world. For example, a player who frequently uses attack skills and completes combat-heavy quests can be associated with a `CombatFocused` play style. Similarly, a player who controls a Mage character and frequently uses `Fireball` may receive a recommendation for a magic-related quest or skill.

## Integration Level in Current Project

The current project does not implement a GRU-RNN model. Instead, it adapts the paper's conceptual contribution: combining structured ontology-based user modeling with behavior-aware recommendation. The machine learning component is considered a future extension. In the current v2 ontology, the necessary semantic foundation is created so that behavior prediction or recommendation could later be added.

## Conclusion

The mandatory paper is relevant because it demonstrates how ontologies can support personalization when combined with behavior modeling. Our RPG ontology uses a similar idea at a smaller scale by representing player profiles, gameplay events, play styles, and recommendations in the knowledge graph.
