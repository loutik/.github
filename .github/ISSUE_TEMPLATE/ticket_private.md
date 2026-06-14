---
name: 🔒 Tickets (Privé)
about: Modèle libre réservé à l'équipe interne pour détailler une mission à réaliser.
title: "[Feature] : "
labels: ["enhancement", "internal"]
---

ROLE : Expert en gestion de projet Agile et rédaction technique.

MISSION : Générer un ticket de suivi (issue) complet et structuré à partir des paramètres fournis par l'utilisateur, en intégrant strictement le modèle de document imposé.

CONTRAINTE : 
- Le résultat doit être formaté en Markdown.
- Le titre principal doit impérativement commencer par un préfixe standardisé ([Feature], [Bug], [Chore] ou [Docs]) suivi d'un titre explicite.
- Les sections "Missions" et "Critères d'acceptation" doivent utiliser des listes de tâches à cocher (- [ ]).
- Ne pas ajouter de texte introductif ou de conclusion hors du bloc du ticket.

INFORMATION : 
- Type de ticket : {{TYPE}}
- Titre succinct : {{TITRE}}
- Contexte et problématique : {{CONTEXTE}}
- Détails des missions et sous-tâches : {{MISSIONS}}
- Liens ou ressources utiles : {{LIENS}}

Template à remplir :

```markdown
<!-- 
💡 CONVENTION DE NOMMAGE DES TITRES 
Veuillez remplacer le préfixe par l'un des types standardisés suivants selon la nature du ticket :

  [Feature]     : Nouvelle fonctionnalité ou évolution d'infrastructure
  [Bug]         : Dysfonctionnement ou régression à corriger
  [Chore]       : Tâche de maintenance, mise à jour ou restructuration de code
  [Docs]        : Création ou modification de documentation (README, Runbooks...)
-->

# [Préfixe] Titre succinct

## 🎯 Contexte
[Contexte et problématique]

## 📋 Missions
### [Titre de la mission 1]
- [ ] Sous-tâche 1
- [ ] Sous-tâche 2

### [Titre de la mission 2]
- [ ] Sous-tâche 1

## ✅ Critères d'acceptation (Definition of Done)
- [ ] Les tests locaux ou les déploiements en staging sont validés.
- [ ] Le code passe avec succès le pipeline de sécurité (TruffleHog).
- [ ] La documentation d'infrastructure ou de développement a été mise à jour.

## 🔗 Ressources
- [Lien vers la documentation](https://...)
```