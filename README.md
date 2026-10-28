# Mémo

Cartes de révision à répétition espacée (méthode Leitner), installable sur téléphone (application web / PWA), sans compte ni serveur.

## Principe

Tu lis une face d'une carte et tu cherches ce qu'il y a derrière, puis tu la retournes :

- **Je savais** : la carte monte d'une boîte et reviendra plus tard ;
- **Je ne savais pas** : elle descend d'une boîte (ou repart en boîte 1, au choix dans les réglages) pour revenir plus vite.

| Boîte | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Révision | tous les jours | tous les 2 jours | tous les 4 jours | chaque semaine | chaque mois | tous les 3 mois | tous les 6 mois | chaque année |

Après chaque révision, la carte **change de côté** : la fois suivante, c'est l'autre face qui est posée, pour retrouver l'information dans les deux sens.

## Fonctionnalités

- **Aujourd'hui** : cartes à réviser (en retard comprises), par paquet ou toutes ensemble, répartition dans les 8 boîtes, prévision des 7 prochains jours, série de jours.
- **Révision** : carte qui se retourne, bouton haut-parleur pour écouter chaque face (synthèse vocale du téléphone, langue choisie par face dans le paquet), « Je savais / Je ne savais pas », annulation de la dernière réponse, puis possibilité de revoir tout de suite les cartes ratées (entraînement sans effet sur les boîtes). Au clavier : Espace pour retourner, L pour écouter, → je savais, ← je ne savais pas.
- **Paquets** : un paquet par thème avec sa couleur (20 au choix), le nom de ses deux faces (ex. Anglais / Français) et la langue de lecture de chacune. Un paquet peut être fusionné dans un autre (Modifier → Fusionner) : ses cartes y passent avec leur progression, les doublons sont retirés. Ajout de cartes une par une ou en lot (`face 1 ; face 2` par ligne, copier-coller depuis un tableur, ou fichier `.txt` / `.csv` au même format), recherche, modification, changement de boîte. Appui long sur une carte pour en sélectionner plusieurs, puis les déplacer vers un autre paquet ou les supprimer.
- **Carte** : une carte peut porter un lieu (latitude, longitude). Il s'affiche sur une mini carte de l'Europe au dos de la carte pendant la révision, et le paquet gagne une vue d'ensemble avec tous ses lieux (toucher un point affiche son nom). En lot, le lieu est une 3e colonne facultative : `Golfe de Botnie ; Au nord de la mer Baltique ; 63, 20.5`. Si la carte existe déjà dans le paquet (même texte sur une face), elle reçoit simplement le lieu et garde sa progression. Le lieu se modifie aussi dans « Modifier la carte ». Fond de carte : Natural Earth (domaine public), dans `carte-europe.js`.
- **Données** : sauvegarde JSON ; à l'import, choix entre ajouter aux cartes existantes (les paquets de même nom sont fusionnés, les doublons ignorés) ou tout remplacer.

Les données restent dans le navigateur de l'appareil (`localStorage`, clé `memo-cartes`). Exporte régulièrement une sauvegarde.

## Lancer en local

```sh
python3 -m http.server 8000
```

Puis ouvre <http://localhost:8000>.

## Installer sur le téléphone

Avec GitHub Pages activé sur le dépôt, l'appli est à l'adresse `https://petitlu3617.github.io/Memo/`. Ouvre-la sur le téléphone, puis « Ajouter à l'écran d'accueil » (Safari) ou « Installer l'application » (Chrome). Elle fonctionne ensuite hors ligne. Après une modification des fichiers, incrémente `VERSION` dans `sw.js`.
