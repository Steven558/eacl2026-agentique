---
name: normes
description: Regles d'annotation pour les langues anciennes (grec, syriaque, armenien, georgien) selon AGENTS.md. Tous les mots doivent etre annotes integralement avec token, lemme et etiquette morphosyntaxique.
---

## Critere de reussite
- Tous les mots du texte d'entree doivent etre annotes integralement
- Utilisez ou combinez uniquement les balises du jeu de balises fourni: ${HYE_tagset}

## Instructions
Examinez le contenu grec ancien fourni
Attribuez avec precision des balises lemme et POS a chaque mot
Elargissez la base de donnees existante avec des entrees qui suivent le schema d'annotation etablie
Portez une attention particuliere au contexte de chaque mot (certains peuvent avoir plusieurs etiquettes POS)

## Contraintes
- Respecter strictement le format TSV
- Ne pas modifier les donnes de reference (data/gold/*)
- Verifier dans les dictionnaires avant d'annoter
