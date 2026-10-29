# Architecture Agentique - EACL2026 Agentique

```
cette architecture à juste pour but de montrer tous mes agents, et leur fonctionnement, enfin le fonctionnement idéal que je souhaiterais.
``̀
## Arborescence 

```
eacl2026-agentique/
├── AGENTS.md                    # Consignes
├── architecture.md              # Ce fichier - documentation de l'architecture
├── README.md
├── pyproject.toml
├── requirements.txt
├── .python-version
├── uv.lock
├── data/                        # Donnees du projet
│   ├── corpus/                  # Textes a annoter
│   ├── prompt-templates/        # Templates pour les prompts
│   └── tagsets/                 # Jeux d'etiquettes (POS tags)
├── pie-baseline/                # Baseline pour evaluation
├── projet/                      # Sous-projet (structure separée)
│   ├── README.md
│   ├── pyproject.toml
│   └── src/
│       └── projet/
│           └── __init__.py
├── results/                     # Resultats generes
├── scripts/                     # Scripts Python d'automatisation
│   ├── __init__.py
│   ├── config.py
│   ├── main.py
│   └── utils.py
└── src/                         # Code source principal
    └── eacl2026_agentique/
        └── __init__.py
(cette arbre est tiré du document README.md, mais dans le cadre de cet exercice, il ne contient pas de document pour l'instant).

.vibe/                          
├── agents/                      
│   ├── annotateur.toml          # Annote les lemmes avec POS-tags
│   ├── chercheur.toml           # Cherche les lemmes dans les dictionnaires
│   ├── grc.toml                 # Agent specialise pour le grec ancien (GRC)
│   ├── hye.toml                 # Agent specialise pour l'armenien (HYE)
│   ├── kat.toml                 # Agent specialise pour le georgien (KAT)
│   ├── lecteur.toml             # Lit et analyse les consignes
│   ├── maitre.toml              # Orchestrateur principal
│   ├── python.toml              # Genere le code Python d'automatisation
│   ├── syc.toml                 # Agent specialise pour le syriaque (SYC)
│   ├── testeur.toml             # Teste les resultats avec echantillons aleatoires
│   └── verifiant.toml           # Verifie la qualite des annotations
└── skills/                      
    ├── .agents/                
    │   └── skills.toml           # accès à internet pour les agents 
    └── normes.md                 # **Règles d'annotation** (referencées par tous les agents)
```

---


### Pipeline Principal

```
                    ┌─────────────────┐
                    │   AGENTS.md      │ ← Normes et consignes 
                    │   normes.md       │ 
                    └────────┬────────┘
                             │
                             v
                    ┌─────────────────┐
                    │    maitre.toml   │ ← Orchestrateur principal
                    └────────┬────────┘
                             │
        ┌────────────────────┼────────────────────┐
        v                    v                    v
┌───────────────┐   ┌───────────────┐   ┌─────────────────────┐
│  lecteur.toml  │   │ chercheur.toml │   │   Agents Langues    │
│  (Analyse)     │   │ (Recherche)    │   │  (Specialises)      │
└────────┬──────┘   └────────┬──────┘   ├─────────────────────┤
         │                   │               │                     │
         │                   │               V                   V
         │                   │   ┌─────────────────┐   ┌─────────────────┐
         │                   │   │    grc.toml      │   │    hye.toml      │
         │                   │   │   (Grec)        │   │   (Armenien)    │
         │                   │   └─────────────────┘   └─────────────────┘
         │                   │
         │                   │   ┌─────────────────┐   ┌─────────────────┐
         │                   │   │    kat.toml      │   │    syc.toml      │
         │                   │   │   (Georgien)    │   │   (Syriaque)    │
         │                   │   └─────────────────┘   └─────────────────┘
         │                   │
         │                   v
         │            ┌───────────────┐
         │            │ annotateur.toml│
         │            │ (Annotation)   │
         │            └────────┬──────┘
         │                     │
         │                     v
         │            ┌───────────────┐   ┌───────────────┐
         │            │ verifiant.toml│   │ python.toml    │
         │            │ (Verification)│   │ (Generation   │
         │            └────────┬──────┘   │  code Python)  │
         │                     │           └────────┬──────┘
         │                     v                   │
         │            ┌───────────────┐            │
         └───────────►│  testeur.toml │◄──────────┘
                      │  (Tests)      │
                      └──────────────┘
```


