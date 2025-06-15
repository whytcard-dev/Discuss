# WhytCard Discuss

Bienvenue dans le dépôt WhytCard Discuss, une zone de discussion et de documentation pour le projet WhytCard, un logiciel open source en développement.

[![Auto-Translate](https://github.com/whytcard-dev/Whytcard_discuss/actions/workflows/auto-translate.yml/badge.svg)](https://github.com/whytcard-dev/Whytcard_discuss/actions/workflows/auto-translate.yml)
[![Setup Discussions](https://github.com/whytcard-dev/Whytcard_discuss/actions/workflows/discussions.yml/badge.svg)](https://github.com/whytcard-dev/Whytcard_discuss/actions/workflows/discussions.yml)

## À propos

Ce dépôt sert de plateforme centrale pour :
- La documentation multilingue du projet WhytCard
- Les discussions communautaires
- Le partage d'idées et de retours

## Documentation multilingue

La documentation est disponible dans plusieurs langues :

- [Documentation en anglais](/EN/)
- [Documentation en français](/FR/)
- [Documentation en espagnol](/ES/)
- [Documentation en allemand](/DE/)
- [Documentation en chinois](/ZH/)
- [Documentation en japonais](/JA/)
- [Documentation en russe](/RU/)
- [Et plus encore...](/Langues.md)

Toutes les traductions sont générées automatiquement à partir des fichiers sources en anglais.

## Système d'autotraduction

Ce dépôt intègre un système d'autotraduction qui traduit automatiquement tous les fichiers Markdown du répertoire `EN` vers plusieurs langues cibles.

### Comment ça fonctionne

1. Les fichiers sources en anglais sont stockés dans le répertoire `EN/`
2. Lorsqu'un fichier est modifié ou ajouté dans `EN/`, il est automatiquement traduit
3. Les traductions sont générées dans les répertoires correspondant à chaque langue (FR/, ES/, etc.)
4. Les modifications sont automatiquement validées dans le dépôt

### Installation locale

Pour installer et utiliser le système d'autotraduction localement :

1. Clonez ce dépôt :
   ```bash
   git clone https://github.com/whytcard-dev/Whytcard_discuss.git
   cd Whytcard_discuss
   ```

2. Installez les dépendances :
   ```bash
   npm install
   ```

3. Configurez l'API Google Cloud Translation :
   - Créez un projet sur Google Cloud Console
   - Activez l'API Cloud Translation
   - Créez une clé de compte de service avec les permissions nécessaires
   - Téléchargez le fichier JSON de clé
   - Définissez la variable d'environnement `GOOGLE_APPLICATION_CREDENTIALS` :
     ```bash
     export GOOGLE_APPLICATION_CREDENTIALS="/chemin/vers/votre-fichier-cle.json"
     ```

### Script de mise à jour automatique

Un script unique a été créé pour mettre à jour le dépôt, traduire les fichiers et synchroniser avec GitHub :

```bash
npm run update
```

Ce script effectue les actions suivantes :
1. Met à jour les répertoires de langues
2. Traduit tous les fichiers Markdown
3. Optimise les fichiers pour GitHub
4. Prépare les commits

## Discussions

Nous utilisons [GitHub Discussions](https://github.com/whytcard-dev/Whytcard_discuss/discussions) pour les conversations communautaires. N'hésitez pas à :

- Poser des questions
- Partager des idées
- Discuter des fonctionnalités
- Donner votre avis sur le projet

## Contribuer

Nous accueillons toutes les contributions ! Consultez notre [guide de contribution](.github/CONTRIBUTING.md) pour commencer.

## Code de conduite

Ce projet adhère à un [code de conduite](.github/CODE_OF_CONDUCT.md). En participant, vous êtes tenu de respecter ce code.

## Licence

Ce projet est sous licence MIT. 