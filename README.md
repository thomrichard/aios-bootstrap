# aios-bootstrap — Construis ton second cerveau / AI OS personnel

Un skill Claude Code qui te construit **ton** second cerveau piloté par l'IA : un vault
rangé (méthode IPCRA) + une couche de pilotage qui apprend à l'IA à travailler dedans,
le tout personnalisé via un court interview. À la fin, tu repars avec un système qui
tourne, amorcé avec ta vraie matière.

> Offert par [le Club SMART](https://skool.com/club-smart).

---

## Ce que tu obtiens

```
Ton-Vault/
├── 0 - Inbox/        → ce que tu captures sans avoir le temps de ranger
├── 1 - Projets/      → tes objectifs avec un début et une fin
├── 2 - Casquettes/   → tes rôles et responsabilités continues
├── 3 - Ressources/   → tes références réutilisables
│   ├── moi.md        → qui tu es, en profondeur (l'IA parle et décide comme toi)
│   └── anti-ia.md    → tes interdits (ce que l'IA ne fait jamais)
├── 4 - Archives/     → ce qui est terminé (lecture seule)
├── CLAUDE.md         → apprend à l'IA qui tu es et comment ranger
├── log.md            → le journal de ton système
├── MEMORY.md         → ce que l'IA retient de toi
└── .claude/
    ├── doctrine.md   → où vit chaque chose, quel outil pour quoi
    └── conventions.md→ nommage, routing, templates
```

---

## Pré-requis

- **Claude Code** installé (CLI ou extension VSCode).
- Un dossier où installer ton vault — idéalement un coffre **Obsidian** (existant et vide,
  ou nouveau). Obsidian n'est pas obligatoire pour démarrer, mais c'est le meilleur lecteur
  pour naviguer dans les liens `[[...]]`.

---

## Installation — un seul fichier, Claude fait le reste

Tu n'as **rien à déplacer à la main**, ni rien à dézipper. Un seul fichier : `aios-bootstrap.md`.

1. Télécharge **[`aios-bootstrap.md`](https://raw.githubusercontent.com/thomrichard/aios-bootstrap/main/aios-bootstrap.md)** (clic droit → « Enregistrer le lien sous… »).
2. Ouvre Claude Code et **glisse le fichier dans le chat** (ou colle son chemin).
3. Écris :
   > **« Installe ce skill : crée le dossier ~/.claude/skills/aios-bootstrap/ et copie ce
   > fichier dedans sous le nom SKILL.md, puis confirme qu'il est bien détecté. »**
4. Claude crée le dossier, range le fichier et vérifie. C'est installé.
5. Dans la même session (ou une nouvelle), écris :
   > **« crée mon second cerveau »**

Le skill se déclenche, te pose ses questions, et construit tout.

> **Pourquoi ça marche** : Claude Code a accès à ton disque. Lui glisser un fichier et lui
> demander de l'installer fait partie de son travail normal — tu n'as pas besoin de savoir
> où vit le dossier `.claude/`.

---

## Comment ça marche

L'interview suit le framework **CAPE** :

- **C — Contexte** : qui tu es, tes casquettes, ton objectif, ton parcours, tes interdits.
- **A — Accès** : où vit ton vault, quels outils tu utilises.
- **P — Production** : ce que tu veux que l'IA produise + tes premiers projets réels.
- **E — Entretien** : ton rythme, le journal, la mémoire.

Puis le skill génère toute la structure et l'amorce avec ta vraie matière.

---

## Après l'installation

Rouvre une session Claude Code **dans le dossier de ton vault** quand tu veux : le
`CLAUDE.md` est lu automatiquement, l'IA sait comment travailler. Tu pilotes ton second
cerveau avec 3 gestes :

- **Ingest** — « range cette idée », « intègre cette source »
- **Query** — « qu'est-ce que je sais sur X ? »
- **Lint** — « fais le ménage dans le vault »

Tout est modifiable : `CLAUDE.md`, la doctrine et les conventions t'appartiennent.
Fais-les évoluer avec ton système.

---

## Aller plus loin

Ce skill pose les fondations. Pour la personnalisation, les échanges et les exemples
concrets, rejoins [le Club SMART](https://skool.com/club-smart) — et retrouve les autres
ressources de la masterclass AIOS sur
[thomrichard.com/masterclass-aios-ressources](https://www.thomrichard.com/masterclass-aios-ressources/).

Chaîne YouTube : [Thomas Richard](https://www.youtube.com/@thomasrichard1978)
