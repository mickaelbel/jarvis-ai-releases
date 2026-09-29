# Jarvis AI — Releases

Dépôt public de **distributions** de Jarvis AI uniquement. Il ne contient ni code source ni documentation technique : c'est le point d'accès que l'application interroge pour les mises à jour automatiques, sans authentification (l'API GitHub refuse les appels anonymes sur un dépôt privé).

**Le code source est dans un dépôt privé distinct**, `mickaelbel/jarvis-ai`.

## Télécharger

[Télécharger la dernière version](https://github.com/mickaelbel/jarvis-ai-releases/releases/latest)

## Vérifier l'intégrité

Chaque release publie un fichier `SHA256.txt`. Pour vérifier un installateur téléchargé :

```powershell
Get-FileHash .\JarvisAI-Setup-<version>.exe -Algorithm SHA256
```

La valeur obtenue doit correspondre à celle annoncée dans `SHA256.txt` de la release.

## Installation et mises à jour

L'installateur s'installe en espace utilisateur, sans privilèges administrateur. WebView2 est fourni par le système (Evergreen) : Edge ou Chrome doivent être présents, ou le bootstrap s'en charge au premier lancement.

L'application recherche seule les nouvelles versions. Elle lit `app-version.txt` dans son propre répertoire et compare avec la dernière release publiée ici.

## Licence

Les licences sont signées hors ligne en RSA-2048. La clé privée ne quitte jamais la machine qui émet les licences ; seule la clé publique est embarquée dans l'application. Une licence est un fichier texte unique de la forme :

```
<Base64 du payload JSON>.<signature hexadécimale>
```

Aucune licence n'est valide si elle n'a pas été émise par le détenteur de la clé privée correspondante.
