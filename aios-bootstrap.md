---
name: aios-bootstrap
description: Construit un second cerveau / AI OS personnel complet pour l'utilisateur — ossature de dossiers IPCRA + couche de pilotage .claude/ (CLAUDE.md, doctrine, conventions) + journal + mémoire, le tout personnalisé via un interview guidé. Déclencher quand l'utilisateur dit "crée mon second cerveau", "monte mon AI OS", "construis mon deuxième cerveau", "bootstrap mon vault", "démarre mon système de notes", "installe mon second cerveau", "aide-moi à organiser mes notes avec l'IA", ou demande à mettre en place un PKM / personal knowledge management piloté par l'IA. À lancer dans un dossier vide ou un Obsidian neuf.
---

<!--
═══════════════════════════════════════════════════════════════════════════
  FICHIER UNIQUE AUTOSUFFISANT — aios-bootstrap (offert par le Club SMART)
═══════════════════════════════════════════════════════════════════════════

  POUR LE MEMBRE QUI INSTALLE :
  Glisse ce fichier dans le chat de Claude Code et écris :
  « Installe ce skill : crée le dossier ~/.claude/skills/aios-bootstrap/ et
    copie ce fichier dedans sous le nom SKILL.md, puis confirme. »
  Ensuite, dans n'importe quelle session, écris « crée mon second cerveau ».

  POUR CLAUDE QUI EXÉCUTE LE BOOTSTRAP :
  Tout ce dont tu as besoin est dans CE fichier — il n'y a pas de dossier
  references/. Les sections ci-dessous remplacent les fichiers séparés :
    • « FLUX » = l'orchestrateur (les 6 étapes)
    • « STRUCTURE IPCRA » = la spec de l'ossature
    • « INTERVIEW CAPE » = le script de l'entretien
    • « TEMPLATES » = les gabarits à écrire (remplis les {{PLACEHOLDERS}})
═══════════════════════════════════════════════════════════════════════════
-->

# Skill aios-bootstrap

## Objectif

Construire pour la personne **son** second cerveau personnel piloté par l'IA — un vault
organisé (ossature IPCRA) + une couche `.claude/` qui apprend à l'IA à travailler dedans.
À la fin, la personne repart avec un système qui tourne, amorcé avec sa vraie matière.

Cadre de l'interview : **CAPE** — **C**ontexte · **A**ccès · **P**roduction · **E**ntretien.

> **Ne jamais générer à l'aveugle.** On interroge d'abord, on confirme, puis on écrit.
> On n'écrase jamais un dossier non vide sans accord explicite. Zéro `{{placeholder}}`
> résiduel dans les fichiers livrés.

---

## FLUX — les 6 étapes

### Étape 1 — Accueil & cadrage
Explique en 3-4 lignes, ton accessible : ce qu'on construit (« ton AI OS perso — un vault
rangé + une couche qui apprend à l'IA à travailler pour toi »), le déroulé (interview CAPE
en 4 temps → génération → amorçage avec ta vraie matière), ~10-15 min, tout modifiable après.

### Étape 2 — Accès à l'environnement
1. Demande le **chemin du dossier** où installer le vault. → `{{VAULT_PATH}}`
2. Demande la **langue de travail**. → `{{LANGUE}}`
3. **Garde-fou** : `ls` le dossier. S'il contient des fichiers, **n'écris pas** — montre
   le contenu et demande confirmation (ajouter à côté / choisir un autre dossier). Jamais d'écrasement.

### Étape 3 — Interview CAPE
Déroule la section **INTERVIEW CAPE** ci-dessous, **en batches courts** (2-4 questions),
via AskUserQuestion pour les choix fermés, texte libre sinon. Reformule et fais confirmer
après chaque temps. Décide le label du dossier 2 (« Casquettes » par défaut, ou « Domaines »/
« Rôles ») → `{{CASQUETTES_LABEL}}`. À la fin, **récapitule toutes les réponses et fais
valider AVANT d'écrire sur le disque**. Adapte-toi : pas de questions de contenu si la
personne n'est pas créateur ; doctrine mono-couche si aucun outil.

### Étape 4 — Génération
Récupère la date du jour → `{{DATE_DU_JOUR}}`. Crée l'arbre, puis écris les fichiers depuis
la section **TEMPLATES** en remplissant les placeholders :
```
{{VAULT_PATH}}/
├── 0 - Inbox/        (INSTRUCTIONS.md + inbox.md)
├── 1 - Projets/      (INSTRUCTIONS.md + projets.md)
├── 2 - {{CASQUETTES_LABEL}}/  (INSTRUCTIONS.md + casquettes.md)
├── 3 - Ressources/   (INSTRUCTIONS.md + ressources.md + moi.md + anti-ia.md)
├── 4 - Archives/     (INSTRUCTIONS.md + archives.md)
├── CLAUDE.md · log.md · MEMORY.md
└── .claude/doctrine.md · .claude/conventions.md
```
Vérifie qu'il ne reste **aucun `{{...}}`** dans les fichiers écrits. Récapitule l'arborescence créée.

### Étape 5 — Bootstrap « première session »
Transforme l'interview en matière réelle :
1. Crée 1-2 fiches **projet** réelles (`{{USER_PROJECTS}}`) dans `1 - Projets/<slug>/<slug>.md`
   (template de fiche projet des conventions). Référence-les dans `projets.md`.
2. Crée 1-2 fiches **casquette** réelles (`{{USER_AREAS}}`) dans `2 - {{CASQUETTES_LABEL}}/<slug>/<slug>.md`.
   Référence-les dans `casquettes.md`.
3. Relie les pages avec des `[[wikilinks]]`. Vérifie la 1re ligne de `log.md`.

### Étape 6 — Clôture
Affiche l'arborescence finale. Explique les **3 opérations** (Ingest / Query / Lint) en une
phrase chacune. Donne **une prochaine étape concrète** (ex. « dépose ta prochaine idée dans
`0 - Inbox/` et dis "range ça" »). Rappelle qu'il peut rouvrir Claude Code **dans ce dossier**
quand il veut : le `CLAUDE.md` sera lu automatiquement.

---

## STRUCTURE IPCRA — spec de l'ossature

Tri par **actionnabilité**, appliqué **dans l'ordre** (le 1er dossier qui colle gagne ;
en cas de doute → `0 - Inbox/`) :

```
0 - Inbox/        → pas le temps de traiter maintenant (file de capture, rien ne dort >7j)
1 - Projets/      → fait avancer un objectif avec un début et une fin
2 - Casquettes/   → fait avancer une responsabilité continue, sans fin
3 - Ressources/   → référence évergreen, réutilisable, sans échéance
4 - Archives/     → terminé, fermé, en pause — lecture seule
```

- **Projet vs Casquette** : un projet finit, une casquette se maintient. « Lancer mon site »
  = projet. « Faire vivre mon site » = casquette.
- Chaque dossier a un **index** ; on lit l'index avant de descendre.
- Couche cerveau : `CLAUDE.md` (orchestrateur, lu à chaque session), `.claude/doctrine.md`
  (où vit chaque chose), `.claude/conventions.md` (nommage/routing/templates), `log.md`
  (journal), `MEMORY.md` (faits durables).
- **3 opérations** : *Ingest* (intégrer une source → pages + index + liens + log) ·
  *Query* (répondre via l'index, classer si valeur durable) · *Lint* (orphelines,
  contradictions, périmés, liens brisés).

---

## INTERVIEW CAPE — script

Règles : batches courts (max 2-4 questions), reformule/confirme à chaque temps, capture les
réponses, mène dans `{{LANGUE}}`. Récap final avant d'écrire.

**Temps C — Contexte** (→ `CLAUDE.md`)
- C1 Comment tu t'appelles, et en une phrase, qu'est-ce que tu fais ? → `{{USER_NAME}}`, `{{USER_PITCH}}`
- C2 Tes 2-4 grandes casquettes/rôles (pro et perso) ? → `{{USER_CASQUETTES}}`
- C3 Tes sujets/domaines au quotidien ? → `{{USER_TOPICS}}`
- C4 Ton objectif principal des 6 prochains mois ? → `{{USER_GOAL}}`
- C5 Comment tu veux que l'IA te parle (tu/vous, direct/posé, niveau de détail) ? → `{{USER_TONE}}`
- C6 Raconte-moi ton parcours en quelques lignes : d'où tu viens, ce qui t'a amené là, ta façon
  de bosser et de décider. Plus tu m'en donnes, mieux l'IA parlera et décidera comme toi. → `{{USER_BIO}}`
- C7 Qu'est-ce que tu ne veux **jamais** que l'IA fasse ? (ex. envoyer un message à ta place,
  supprimer sans demander, un ton trop vendeur, des emojis partout…) → `{{USER_ANTI_IA}}`
  (C6-C7 alimentent les fiches de contexte perso `3 - Ressources/moi.md` et `3 - Ressources/anti-ia.md`,
  référencées dans `ressources.md` et pointées depuis le `CLAUDE.md`.)

**Temps A — Accès** (→ `doctrine.md`)
- A1 Confirme le dossier du vault → `{{VAULT_PATH}}`
- A2 Quels outils tu utilises déjà (Notion, Drive, Airtable, Gmail, rien…) ? → `{{USER_TOOLS}}`
- A3 Ta « source de vérité » pour les données structurées ? (ou « aucune ») → `{{USER_SOURCE_OF_TRUTH}}`
- A4 Des MCP/connecteurs branchés à Claude Code ? → `{{USER_MCP}}`
  (En V1 on **documente** seulement, on ne branche pas. Aucun outil = doctrine mono-couche, c'est OK.)

**Temps P — Production** (→ routing + bootstrap)
- P1 Quels types de choses l'IA doit produire/organiser pour toi ? → `{{USER_OUTPUTS}}`
- P2 1-2 **projets en cours** (avec début et fin) ? → `{{USER_PROJECTS}}`
- P3 1-2 **casquettes/responsabilités** continues ? → `{{USER_AREAS}}`
- P4 Un type de note récurrent qui mériterait un template ? → `{{USER_TEMPLATE_NEEDS}}`

**Temps E — Entretien** (→ maintenance + log/mémoire)
- E1 Fréquence d'usage prévue ? → `{{USER_RHYTHM}}`
- E2 L'IA tient-elle un **journal** (log) à chaque session ? (oui recommandé) → `{{USER_LOG}}`
- E3 L'IA **retient-elle tes préférences** (mémoire) ? (oui recommandé) → `{{USER_MEMORY}}`

---

## TEMPLATES

> Écris chaque bloc ci-dessous dans le fichier indiqué, en remplaçant les `{{PLACEHOLDERS}}`.
> (Les blocs sont délimités par `~~~` pour ne pas casser les fences internes en backticks.)

### → `CLAUDE.md` (racine du vault)
~~~markdown
# CLAUDE.md — Instructions pour l'IA de ce second cerveau

> Lu au début de chaque session. Apprend à l'IA qui tu es, comment ranger, comment
> travailler dans ce vault. Mets-le à jour quand ton contexte change.

## Mon rôle
Tu es l'assistant de pensée, de rangement et de rédaction de {{USER_NAME}} dans son second
cerveau. Tu crées des fichiers, les nommes, les places au bon endroit, rédiges, relies les
pages, et maintiens ce vault comme une base qui s'enrichit.
Langue : {{LANGUE}}. Ton : {{USER_TONE}}.

## Qui je suis
{{USER_NAME}} — {{USER_PITCH}}
Casquettes : {{USER_CASQUETTES}} · Sujets : {{USER_TOPICS}}
Objectif 6 mois : {{USER_GOAL}}
Contexte perso détaillé (parcours, façon de travailler) : [[moi]]

## Ce que je ne veux pas
La liste complète de mes interdits vit dans [[anti-ia]] — la lire et s'y tenir.

## Architecture du vault (IPCRA)
```
0 - Inbox/        → pas le temps de traiter maintenant
1 - Projets/      → objectif avec un début et une fin
2 - {{CASQUETTES_LABEL}}/   → responsabilité continue
3 - Ressources/   → référence évergreen, réutilisable
4 - Archives/     → terminé, fermé (lecture seule)
```
Applique l'arbre **dans l'ordre** ; en cas de doute → `0 - Inbox/`.
Doctrine : `.claude/doctrine.md`. Conventions : `.claude/conventions.md`.

## Les 3 opérations
- **Ingest** : lire la source → discuter → créer/MAJ les pages → MAJ les index → ajouter les `[[liens]]` → logger.
- **Query** : lire l'index concerné → descendre si besoin → synthétiser → classer si valeur durable.
- **Lint** : orphelines, contradictions, périmés, concepts sans page, liens brisés.

## Routing
« Ouvre le projet X » → identifier le dossier IPCRA → lire son index (`projets.md`,
`casquettes.md`, `ressources.md`) → ouvrir le fichier → confirmer avant d'attaquer.

## Garde-fous
- Jamais supprimer sans confirmation. `4 - Archives/` en lecture seule.
- Pas de dossier hors IPCRA. Toujours MAJ l'index touché + logger dans `log.md`.

## Fichiers spéciaux
- `log.md` — journal append-only, format `## [YYYY-MM-DD] action | sujet`.
- `MEMORY.md` — faits durables rechargés chaque session.
- `.claude/doctrine.md` · `.claude/conventions.md`.
~~~

### → `.claude/doctrine.md`
~~~markdown
# Doctrine — Architecture de mon second cerveau

> « Où ça vit / qui lit quoi / quel outil ». À mettre à jour explicitement.
Posée le {{DATE_DU_JOUR}}.

## Principe central
Ce vault est le **hub** : j'y pense, synthétise, navigue par liens. Ce qui vit ailleurs a
une **projection** ici (micro-synthèse + lien retour). Le vault n'a pas besoin de tout
contenir, il doit savoir **où est tout**.

## Couches de stockage
{{DOCTRINE_LAYERS}}
<!-- Si outils : table Cerveau-hub (ce vault) / Base structurée ({{USER_SOURCE_OF_TRUTH}}) /
Plateformes ({{USER_TOOLS}}). Si aucun outil : une seule couche, le vault. -->

## Règle 1 — Source de vérité par objet
| Objet | Source de vérité | Projection |
|---|---|---|
| Idée / note brute | Vault (Inbox puis rangée) | — |
| Référence évergreen | Vault (Ressources) | — |
| Projet / Casquette | Vault (Projets / {{CASQUETTES_LABEL}}) | — |
| Donnée structurée | {{USER_SOURCE_OF_TRUTH}} | Synthèse + lien retour si durable |

## Règle 2 — Liaison bidirectionnelle
Toute projection porte le lien vers sa source. Lier généreusement en `[[wikilinks]]`.

## Règle 3 — `0 - Inbox/` = file de traitement
Pas un entrepôt. Tout y est destiné à être traité et rangé. Rien ne dort >7 jours.

## Règle 4 — Ordre de lecture de l'IA
1. Le vault (index + synthèses). 2. Les outils externes (détail/stats). 3. Sources lourdes sur besoin.

## Règle 5 — Ajout d'un outil
Aucun outil ajouté si la capacité est déjà couverte. Un système simple qui tourne bat un
stack complexe qu'on n'entretient pas.
~~~

### → `.claude/conventions.md`
~~~markdown
# Conventions du vault

## Nommage
- **kebab-case**, sans accents ni espaces : `idee-newsletter-aout.md`.
- Un fichier = un objet. Préfixes Inbox optionnels : `meeting-AAAA-MM-JJ-<sujet>`,
  `idee-<sujet>`, `veille-<source>-<sujet>`.
{{USER_NAMING_EXTRA}}

## Routing
| Contenu | Dossier |
|---|---|
| Capture non triée | `0 - Inbox/` |
| Objectif daté | `1 - Projets/<projet>/` |
| Responsabilité continue | `2 - {{CASQUETTES_LABEL}}/<casquette>/` |
| Référence réutilisable | `3 - Ressources/` |
| Terminé / en pause | `4 - Archives/` |

## Index par dossier (lire l'index avant de descendre)
`0 - Inbox/`→`inbox.md` · `1 - Projets/`→`projets.md` · `2 - {{CASQUETTES_LABEL}}/`→`casquettes.md`
· `3 - Ressources/`→`ressources.md` · `4 - Archives/`→`archives.md`

## Template fiche projet
# [Nom] — **Statut** actif/pause/terminé — **Début** AAAA-MM-JJ — **Objectif** [ce que « fini » veut dire]
## Contexte / ## Avancement (cases à cocher) / ## Liens [[...]]

## Template fiche casquette
# [Nom] — **Standard à maintenir** [à quoi ressemble « bien tenu »]
## Quoi / ## Routines / ## Liens [[...]]
~~~

### → `INSTRUCTIONS.md` dans CHAQUE dossier IPCRA
~~~markdown
# INSTRUCTIONS — {{FOLDER_DISPLAY}}/
> Règles propres à ce dossier. Transverses : `CLAUDE.md` + `.claude/doctrine.md` + `.claude/conventions.md`.

## Rôle
{{FOLDER_ROLE}}
## Critère d'entrée
{{FOLDER_CRITERE}}
## Index
`{{FOLDER_INDEX}}` — à consulter avant de descendre dans les fichiers.
## Sortie attendue après traitement
{{FOLDER_SORTIE}}
~~~
Valeurs par dossier :
- **0 - Inbox** — RÔLE : sas de capture, file de traitement (rien >7j). CRITÈRE : « je capture, je traite plus tard ». INDEX : `inbox.md`. SORTIE : fichier traité puis rangé en IPCRA + ligne de log.
- **1 - Projets** — RÔLE : objectifs datés, 1 sous-dossier/projet actif. CRITÈRE : « ça se termine ». INDEX : `projets.md`. SORTIE : à la clôture, déplacer vers `4 - Archives/`.
- **2 - {{CASQUETTES_LABEL}}** — RÔLE : rôles/responsabilités continues. CRITÈRE : « un standard à maintenir, pas un objectif ». INDEX : `casquettes.md`. SORTIE : si fermée, déplacer vers Archives.
- **3 - Ressources** — RÔLE : références évergreen réutilisables. CRITÈRE : « je veux relire/réutiliser ça ». INDEX : `ressources.md`. SORTIE : si périmé, archiver/supprimer (avec confirmation).
- **4 - Archives** — RÔLE : terminé/fermé/en pause — LECTURE SEULE. CRITÈRE : « fini ou en sommeil, à ne pas perdre ». INDEX : `archives.md`. SORTIE : pour réactiver, ressortir vers Projets/Casquettes.

### → fichier index dans chaque dossier
~~~markdown
# {{FOLDER_DISPLAY}} — Index
> {{FOLDER_ONELINER}}

<!-- Projets/Casquettes = table | nom | statut | lien | ; Inbox/Ressources/Archives = liste à puces.
Quasi vide à l'amorçage, se remplit à l'usage. -->

Conventions du dossier : [[INSTRUCTIONS]].
~~~

### → `3 - Ressources/moi.md`
~~~markdown
# Moi — {{USER_NAME}}

> Fiche de contexte perso. L'IA la lit pour parler et décider comme toi.
> Enrichis-la au fil du temps : plus elle est riche, plus l'IA est juste.

## En une phrase
{{USER_PITCH}}

## Mon parcours
{{USER_BIO}}

## Mes casquettes
{{USER_CASQUETTES}}

## Mes sujets
{{USER_TOPICS}}

## Mon objectif des 6 prochains mois
{{USER_GOAL}}

## Ma façon de travailler
- Ton attendu de l'IA : {{USER_TONE}}
- Rythme d'utilisation du second cerveau : {{USER_RHYTHM}}
~~~

### → `3 - Ressources/anti-ia.md`
~~~markdown
# Anti-IA — ce que l'IA ne fait jamais

> La liste de tes interdits. L'IA la lit à chaque session et s'y tient.
> Ajoute une ligne chaque fois que l'IA fait quelque chose qui t'agace.

## Mes interdits
{{USER_ANTI_IA}}

## Les interdits de base (recommandés, garde-les)
- Ne jamais supprimer un fichier sans confirmation explicite.
- Ne jamais envoyer un message / email / publication à ma place sans validation.
- Ne pas inventer une information manquante : dire « je ne sais pas » et demander.
- Ne pas créer de dossiers hors de la structure du vault.
~~~

### → `log.md` (racine)
~~~markdown
# Log du vault
Journal chronologique — append-only. Format : `## [YYYY-MM-DD] action | sujet`

---

## [{{DATE_DU_JOUR}}] bootstrap | Second cerveau créé via aios-bootstrap — IPCRA + couche .claude + première matière ({{USER_PROJECTS}}, {{USER_AREAS}})
~~~

### → `MEMORY.md` (racine)
~~~markdown
# MEMORY.md — Index des faits durables
> Un fait par ligne. Rechargé chaque session. Ajoute une ligne quand un fait mérite d'être retenu.

- **Identité** — {{USER_NAME}}, {{USER_PITCH}}. Casquettes : {{USER_CASQUETTES}}.
- **Objectif 6 mois** — {{USER_GOAL}}.
- **Ton attendu** — l'IA parle en {{USER_TONE}}.
- **Stack** — outils : {{USER_TOOLS}}. Source de vérité structurée : {{USER_SOURCE_OF_TRUTH}}.
~~~
