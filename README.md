# .github

![Bannière Loutik](https://raw.githubusercontent.com/loutik/design-assets/main/banniere_loutik.png)

## Contexte

Ce dépôt centralise la configuration globale, les modèles (templates), les documents de référence et les pipelines d'intégration continue (CI/CD) pour l'ensemble de l'organisation GitHub Loutik. Il sert de socle commun pour garantir une standardisation des pratiques de contribution, maintenir la cohérence de l'image de marque publique et imposer le cadre légal et éthique défini pour nos projets open-source.

-----

## Structure du dépôt

L’organisation du dépôt suit la logique standard de GitHub pour les fichiers de communauté et de configuration :

```text
.github/
├── profile/
│   └── README.md
├── ISSUE_TEMPLATE/
│   ├── bug_report.yml
│   └── feature_request.yml
├── workflows/
│   ├── lint-iac.yml
│   ├── build-mkdocs.yml
│   └── docker-publish.yml
├── PULL_REQUEST_TEMPLATE.md
└── LICENSE.md

```

* **`profile/`** : Contient les éléments liés à l'identité visuelle et la présentation de l'organisation sur GitHub.
* **`ISSUE_TEMPLATE/`** : Regroupe les modèles standardisés permettant aux contributeurs de remonter des bugs ou de proposer des fonctionnalités.
* **`workflows/`** : Stocke les GitHub Actions réutilisables (Reusable Workflows) pour standardiser nos déploiements.
* **`PULL_REQUEST_TEMPLATE.md`** : Trame de base imposée lors de la création d'une Pull Request.
* **`LICENSE.md`** : Le texte intégral de la licence Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0).

---

## Utilisation de .github

### 1. Cloner le dépôt localement

```bash
# 'git clone' : Télécharge une copie locale du dépôt distant.
git clone [https://github.com/loutik/.github.git](https://github.com/loutik/.github.git)
# 'cd' : Change le répertoire de travail actuel pour entrer dans le dossier cloné.
cd .github
```

### 2. Modifier un modèle de communauté

Les modifications apportées aux templates nécessitent d'être éditées localement avant d'être poussées.

```bash
# 'nano' : Ouvre l'éditeur de texte en ligne de commande pour modifier le fichier spécifié.
nano PULL_REQUEST_TEMPLATE.md
```

### 3. Valider et propager les modifications

```bash
# 'git add .' : Ajoute tous les fichiers modifiés dans le répertoire courant à la zone de préparation (staging area).
git add .
# 'git commit -m' : Enregistre les modifications préparées dans l'historique local avec un message descriptif.
git commit -m "chore(templates): mise à jour du modèle de Pull Request"
# 'git push origin main' : Envoie les commits locaux vers le dépôt distant ('origin') sur la branche 'main'.
git push origin main
```

---

## Workflows réutilisables

Ce dépôt centralise nos pipelines d'intégration et de déploiement continu.

### Intégrer un workflow dans un autre dépôt

Pour utiliser un workflow centralisé, créez un fichier `.github/workflows/ci.yml` dans le dépôt cible de l'organisation et appelez-le de la manière suivante :

```yaml
name: 🚀 Fuseline

# 'on' : Définit les événements déclencheurs.
# 'push' -> 'branches: [main]' : Le workflow s'exécute à chaque fois que du code est poussé sur la branche principale.
on:
  push:
    branches:
      - main
  pull_request:

jobs:
  # 'call-workflow' : Nom arbitraire attribué à cette tâche d'exécution.
  security:
    # Syntaxe : propriétaire/dépôt/chemin/vers/fichier.yml@branche
    uses: loutik/.github/.github/workflows/security.yml@main

    # 'secrets: inherit' : Directive permettant de transmettre automatiquement 
    # tous les secrets configurés dans le dépôt appelant au workflow réutilisable.
    secrets: inherit
```

### Workflows disponibles

* **`workflows/lint-iac.yml`** : Pipeline d'analyse statique pour l'Infrastructure as Code (IaC). Il vérifie la syntaxe et valide les bonnes pratiques sur nos fichiers de configuration (Ansible, Docker Compose, manifests Kubernetes).
* **`workflows/build-mkdocs.yml`** : Pipeline de construction et de déploiement de nos documentations techniques. Il automatise la génération du site statique via MkDocs (suivant le framework Diátaxis) et le publie sur GitHub Pages.
* **`workflows/docker-publish.yml`** : Pipeline de conteneurisation. Il construit nos images Docker, applique les tags de versioning (semver) et pousse les artefacts sécurisés vers notre registre d'images.

---

## Bonnes pratiques et sécurité

1. **Généricité des modèles** : Les templates et workflows de ce dépôt doivent rester agnostiques pour s'adapter à la diversité de nos projets (bots Discord, IaC, web).
2. **Conformité des licences** : Toute intégration de nouveaux outils doit rester compatible avec notre engagement éthique et la licence CC BY-SA 4.0.

```bash
# 'markdownlint' : Commande exécutant un linter pour vérifier la conformité syntaxique et stylistique de tous les fichiers Markdown (**.md).
markdownlint '**/*.md'
```

---

## 👨‍💻 Mainteneurs

* **Louis MEDO** | [LinkedIn](https://www.linkedin.com/in/louismedo/) | [Portfolio](https://louis.loutik.fr/) | [GitHub](https://github.com/FireToak) | [louis.medo@loutik.fr](mailto:louis.medo@loutik.fr)

---

<div align="center">
<br>
<small><i>Dernière mise à jour : 06 juin 2026</i></small>
</div> 