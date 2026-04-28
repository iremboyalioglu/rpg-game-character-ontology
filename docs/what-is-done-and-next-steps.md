# Ödevde Ne Yapıldı ve Bundan Sonra Ne Yapılacak?

## 1. Domain Seçildi

Seçilen domain:

**RPG Game Character Ontology**

Bu, küçük ölçekli bir rol yapma oyunu dünyasında karakterleri, sınıfları, ırkları, yetenekleri, silahları, zırhları, görevleri, faction'ları ve bölgeleri modelleyen bir ontolojidir.

## 2. Grup Bilgisi Eklendi

Proje iki kişilik grup olarak hazırlanmıştır:

- İrem Boyalıoğlu - 200316003
- Yunus Erdem Ocak - 200316053

## 3. Scope ve Purpose Belirlendi

Ontology'nin amacı, oyun karakterleri ve oyun dünyasındaki temel varlıklar arasındaki ilişkileri anlamlı ve sorgulanabilir şekilde modellemektir.

Kapsam bilinçli olarak küçük tutuldu. Bu ontology oyun motoru, grafik, animasyon, multiplayer veya gerçek zamanlı combat hesaplamaları gibi teknik konuları kapsamaz.

## 4. İlk Ontology Dosyası Hazırlandı

Hazırlanan dosya:

```text
ontology/rpg-game-character-ontology.ttl
```

Bu dosyada temel class'lar, ilişkiler ve örnek bireyler yer alır.

## 5. README Hazırlandı

Hazırlanan dosya:

```text
README.md
```

README dosyası GitHub reposunun ana açıklama dosyasıdır. Projenin adı, grup bilgisi, amacı, kapsamı, dosya yapısı ve mevcut ilerleme durumu burada açıklanır.

## 6. ORSD Draft Hazırlandı

Hazırlanan dosyalar:

```text
docs/ORSD-draft.docx
docs/ORSD-draft.md
```

Bu dosya ontology specification document taslağıdır. Purpose, Scope, Implementation Language, Intended End-Users, Intended Uses, Ontology Requirements ve Pre-Glossary bölümlerini içerir.

## 7. Design Decisions Dosyası Hazırlandı

Hazırlanan dosya:

```text
docs/design-decisions.md
```

Bu dosyada domain seçimi, kapsam sınırlaması, TBox/ABox yapısı, class hierarchy, property seçimi ve kapsam dışı bırakılan detaylar açıklanır.

## 8. Competency Questions Hazırlandı

Hazırlanan dosya:

```text
examples/sample-competency-questions.md
```

Bu dosyada ontology'nin cevaplayabilmesi gereken örnek sorular yer alır.

## 9. SPARQL Query Dosyası Hazırlandı

Hazırlanan dosya:

```text
queries/competency-questions.sparql
```

Bu dosyada competency question'ları cevaplamak için kullanılabilecek başlangıç SPARQL sorguları yer alır.

## 10. SHACL Shapes Dosyası Hazırlandı

Hazırlanan dosya:

```text
shapes/rpg-game-character-shapes.ttl
```

Bu dosya, ontology içindeki karakter, quest, NPC ve enemy verilerini kontrol etmek için başlangıç SHACL kuralları içerir.

## 11. GitHub İçin Yapılacaklar

1. GitHub'da `rpg-game-character-ontology` adlı repository oluştur.
2. Repository açıklamasında şunu kullan:

```text
An OWL/RDF ontology for modeling RPG game characters, classes, skills, quests, factions, and locations for the Knowledge Engineering and Ontologies course.
```

3. Dosyaları klasör yapısını koruyarak yükle.
4. İlk commit mesajı olarak şunu kullan:

```text
Initial ontology draft and specification document
```

## 12. Haftaya Hocaya Anlatılacak Kısa Açıklama

Our selected domain is RPG Game Character Ontology. The ontology aims to model characters, classes, races, skills, weapons, armor, quests, factions, and locations in a small-scale role-playing game world. For the initial version, we defined the core classes, properties, and example individuals. We also prepared a GitHub repository structure, README file, ontology file, draft specification document, design decisions, competency questions, initial SPARQL queries, and initial SHACL shapes.
