# Dépôt de mods TF (custom)

**Ce n'est pas le dépôt officiel de StellarModManager.** C'est un dépôt privé entre potes : il ne liste que les mods de [tidic84](https://github.com/tidic84) et de [Romalaure](https://github.com/Romalaure).

Les mods officiels restent disponibles dans l'app, ils viennent du dépôt officiel ([voxar.dev/mods.json](https://voxar.dev/mods.json)).

## Utilisation

- **TFStellarModManager** : ce dépôt est déjà configuré par défaut, il n'y a rien à faire.
- **StellarModManager (avec dépôts personnalisés)** : *Paramètres → Dépôts personnalisés*, ajouter
  `https://github.com/tidic84/StellarModRepository`

## Mods

| Mod | Auteur |
| --- | --- |
| [Arsenal](https://github.com/tidic84/StellarDrive-Arsenal) | tidic84 |
| [World Backups](https://github.com/tidic84/StellarDrive-WorldBackups) | tidic84 |
| [Custom Seat](https://github.com/tidic84/StellarDrive-CustomSeat) | tidic84 |
| [StellarAnchor](https://github.com/tidic84/StellarDrive-StellarAnchor) | tidic84 |
| [StellarBuild](https://github.com/tidic84/StellarDrive-StellarBuild) | tidic84 |
| [StellarFactory](https://github.com/tidic84/StellarDrive-StellarFactory) (nécessite StellarBuild) | tidic84 |
| [StellarLogistics](https://github.com/tidic84/StellarDrive-StellarLogistics) (nécessite StellarBuild et StellarFactory) | tidic84 |
| [Ship Performance Fix](https://github.com/tidic84/StellarDrive-ShipPerformanceFix) (plus de freeze en construisant les gros vaisseaux) | tidic84 |
| [StellarDrive Demo TF](https://github.com/Romalaure/StellarDrive-demo-TF) | Romalaure |
| [StellarDrive Demo TF Advanced](https://github.com/Romalaure/StellarDrive-demo-TF-advanced) | Romalaure |

## Ajouter un mod

1. Le dépôt du mod doit être **public** sur GitHub, branche `main`.
2. Il contient un `mod.json` (ici dans le dossier `Mods/`) :
   ```json
   {
     "id": "mon_mod",
     "name": "Mon Mod",
     "author": "Pseudo",
     "version": "1.0.0",
     "description": "Ce que fait le mod.",
     "thumbnail": "Thumbnail.png",
     "images": []
   }
   ```
3. Chaque version est une **release GitHub** avec le tag `v<version>` (ex. `v1.0.0`, identique à `version` dans `mod.json`) contenant un zip nommé exactement `<nom-du-dépôt>.zip`, structuré ainsi :
   ```text
   <nom-du-dépôt>.zip
   ├── mod.json
   ├── Mods/       <-- les .dll du mod
   └── Plugins/    <-- optionnel
   ```
4. Ajouter une ligne dans `mods.json` :
   ```json
   { "author": "Pseudo", "repo": "nom-du-dépôt", "metadata": "Mods" }
   ```
   (`metadata` = dossier où se trouve `mod.json` dans le dépôt du mod, vide s'il est à la racine.)

## Publier une mise à jour

Augmenter `version` dans `mod.json`, puis publier la release `v<nouvelle version>` avec le zip. L'app la propose dans *Mises à jour*.
