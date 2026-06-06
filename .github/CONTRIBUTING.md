# Guide de contribution

![https://raw.githubusercontent.com/loutik/design-assets/main/banniere_loutik.png](https://raw.githubusercontent.com/loutik/design-assets/main/banniere_loutik.png)

Merci de votre intérêt pour les projets de l'organisation **Loutik**. Ce guide définit les normes techniques et le formalisme obligatoires applicables à l'ensemble de nos dépôts (Infrastructure as Code, documentation MkDocs et développement logiciel).

En participant, vous acceptez de respecter notre [Code de conduite](CODE_OF_CONDUCT.md).

---

## 🗺️ Stratégie de branches

La branche principale de chaque dépôt est `main` (environnement de production et source de vérité). Toute modification doit faire l'objet d'une branche de travail dédiée.

### Format strict des branches :
`[type]/[issue-id]-[courte-description]`

* **Types autorisés :**
    * `feat` : Nouvelle fonctionnalité
    * `fix` : Correction de bug
    * `docs` : Documentation
    * `chore` : Tâche de maintenance

*Exemples conformes :* `feat/12-add-sso-authentik` ou `fix/45-typo-readme-k3s`
*Exemples interdits :* `louis-dev-test` ou `patch-1`

*Note : Les branches générées automatiquement par Dependabot ou Renovate font exception à cette règle.*

---

## 💬 Messages de commit

Nous adoptons la norme industrielle **Conventional Commits**. Cette rigueur est indispensable pour générer des changelogs automatiques et déclencher nos pipelines CI/CD.

### Format strict :
`<type>(<scope>): <description courte>`

* **type** : `feat` (code), `fix` (patch), `docs` (documentation), `style` (formatage), `refactor` (restructuration), `ci` (pipelines), `test` (tests).
* **scope** *(optionnel)* : Le module ou service impacté (ex: `ansible`, `network`, `bot`), **toujours en minuscules**.
* **description** : Écrite à l'impératif, au présent, **sans majuscule au début, ni point final**.

*Exemples conformes :*
* `feat(ansible): ajout du rôle de déploiement apache`
* `fix(network): correction de la route par défaut vers la gateway`
* `docs: mise à jour du schéma d'architecture`

*Exemples interdits :* `Mise à jour du script` (pas de type) ou `feat (WAF): Ajout de Crowdsec.` (majuscule et point final).

---

## 🛠️ Processus de validation

Avant qu'une modification puisse être fusionnée vers la branche `main`, le code doit valider les étapes suivantes :

### 1. Contrôle en local

L'outil **commitlint** doit être configuré sur votre poste local. Il bloquera automatiquement la création de tout commit non conforme à la structure spécifiée ci-dessus.

### 2. Validation par l'Intégration Continue (CI)

Lors de l'ouverture de votre Pull Request (PR) :
* Un workflow automatisé (GitHub Actions / Jenkins) analyse le titre de la PR et l'historique des commits.
* **Tout écart par rapport à la norme rejettera systématiquement la Pull Request** et bloquera la fusion vers `main`.

---
## 🗪 Soumettre un ticket

* **Bugs et Améliorations :** Utilisez l'onglet **Issues** de GitHub et sélectionnez le formulaire correspondant à votre profil (Public ou Interne).
* **Format des Dépôts :** Si vous devez créer un nouveau dépôt associé, son nom doit impérativement utiliser le format `kebab-case` (minuscules séparées par des tirets, ex: `infrastructure-ansible`).

> ❤️ Toute l'équipe vous remercie pour votre contribution !

---

<p align="center">
  <strong>Loutik</strong> — Reprenez le contrôle de vos données.<br>
  <sub>Hébergé avec ❤️ en France sur notre infrastructure et en Suisse via notre partenaire <a href="https://www.infomaniak.com">Infomaniak</a>.</sub><br>
  <sub>© 2026 Loutik. Reprenez le contrôle de vos données !</sub>
</p>