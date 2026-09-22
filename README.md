# Intégration NetGeo (Niveau 3) & contrôle qualité des Niveaux 1-2

> **🔒 The source code in this repository is encrypted.**
> The archive `netgeo-integration.zip` is protected with **WinZip AES-256** encryption.
> The password is shared privately with recruiters / reviewers on request.

## What it does

Suite d'outils Python pour préparer, valider et corriger les données d'import NetGeo : shapefiles, CSV NDS, câblage, épissures.

- **Validation topologique** : graphe des câbles NDS, détection du nœud source, traçage des chemins terminaux, contrôle de la couverture fibre/port, détection des épissures manquantes.
- **Correction automatique** : ajout des épissures manquantes, déduplication des fibres, correction des champs obligatoires (ETAT, CODE_BOITE, CODE_SITE/NIVEAU), rapports d'anomalies Excel et texte.
- **Pipeline « one-click »** : fix → finalize → validate.

## Results

- Import NetGeo **sans erreur**.
- Contrôle qualité automatisé des Niveaux 1 et 2.

## Stack

Python · pandas · geopandas · BFS · shapefile · openpyxl · JSON

## Decrypt & run

```bash
pip install pyzipper
python3 decrypt.py          # prompts for the password, extracts to ./src
# or without the helper (7-Zip / WinZip / unzip all support AES-256):
7z x netgeo-integration.zip -p
```

## Integrity

Every file inside the archive is listed with its SHA-256 in `MANIFEST.sha256`.
Verify **from the repository root** (the paths are relative to it):

```bash
sha256sum -c MANIFEST.sha256      # Linux / macOS / Git Bash
certutil -hashfile src\main.py SHA256   # Windows, per file
```

---
*Ali Nouna — alinouna@gmail.com — linkedin.com/in/AliNouna*
