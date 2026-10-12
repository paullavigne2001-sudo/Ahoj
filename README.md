# Prague : tchèque et visite

Petite application web (PWA) pour préparer un séjour à Prague : mots et phrases avec audio, repères de prononciation, quiz, histoire en 8 étapes, lieux à voir, gastronomie et infos pratiques.

Tout fonctionne hors ligne une fois l'app ouverte une première fois. Aucune dépendance, aucun build : des fichiers statiques.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | L'application (pages, données, quiz, audio) |
| `manifest.webmanifest` | Nom, couleurs et icônes pour l'installation sur Android |
| `sw.js` | Service worker : mise en cache pour le hors ligne |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` | Icônes |
| `.nojekyll` | Demande à GitHub Pages de servir les fichiers tels quels |

## Audio

La prononciation utilise la synthèse vocale du téléphone (voix tchèque `cs-CZ`). Sur Android, si aucune voix tchèque n'est détectée, l'installer dans Réglages > Synthèse vocale.

## Tester en local

```
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000 (le service worker demande http://localhost ou https).

## Publier

**GitHub Pages** : Settings > Pages > Deploy from a branch > `main` / `(root)`.

**Vercel** : importer le dépôt, framework « Other », sans commande de build, répertoire de sortie à la racine.

## Mettre à jour l'app installée

Après une modification, augmenter le numéro de version du cache dans `sw.js` (`prague-v1` devient `prague-v2`) pour que les téléphones récupèrent la nouvelle version.

## Contenu à vérifier avant le départ

Horaires, jours de fermeture, tarifs et lignes de transport changent : les confirmer sur les sites officiels.

 
