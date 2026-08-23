# QuadrantCompose

Exercice Jetpack Compose (Android Basics with Compose) : un écran divisé en
4 quadrants égaux, chacun présentant le nom d'une fonction Composable
(`Text`, `Image`, `Row`, `Column`) accompagné d'une courte description.

## Aperçu

L'écran est découpé en une grille 2x2 :

| Text composable    | Image composable      |
|--------------------|-----------------------|
| **Row composable** | **Column composable** |

Chaque quadrant a sa propre couleur de fond et affiche :
- un titre en gras,
- une description en dessous, alignée en justifié.

## Caractéristiques techniques

- Grille 2x2 obtenue avec une `Column` contenant 2 `Row`, et
  `Modifier.weight(1f)` appliqué à la fois sur les `Row` (pour la hauteur)
  et sur chaque `Quadrant` à l'intérieur (pour la largeur) → 4 rectangles
  strictement égaux.
- Contenu de chaque quadrant centré verticalement (`Arrangement.Center`) et
  horizontalement (`Alignment.CenterHorizontally`), avec 16dp de padding
  sur les 4 côtés.
- Titre en `FontWeight.Bold` avec 16dp de marge sous lui.
- Description en `TextAlign.Justify`.
- Le composable `Quadrant` reçoit et chaîne son propre paramètre
  `modifier` (et non `Modifier` brut), pour que l'appelant garde le
  contrôle de la taille/position depuis `QuadrantCompose`.

## Structure du projet

```
app/src/main/java/com/example/quadrantcompose/
├── MainActivity.kt          # Activité + composables Quadrant / QuadrantCompose
└── ui/theme/                # Thème Material 3 généré par Android Studio
```

## Lancer le projet

1. Ouvrir le dossier dans Android Studio (`File > Open...`).
2. Laisser Gradle synchroniser les dépendances.
3. Lancer sur un émulateur ou un appareil physique (▶️ Run), ou utiliser
   directement l'aperçu `QuadrantComposePreview` dans l'onglet Design.