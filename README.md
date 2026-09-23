# Éditeur de « Livre dont vous êtes le héros » en Qt / C++

## Contexte

Projet réalisé en **groupe de 3** en **BUT Informatique (1re année)** à l'**IUT Lyon 1 - site de Bourg-en-Bresse**.

L'objectif était de développer une **application de bureau complète en C++ avec Qt** : un logiciel qui permet de **créer, jouer et exporter** un « livre dont vous êtes le héros », un récit où le lecteur avance de page en page selon ses choix, en gérant ses points de vie, son expérience et ses objets.

---

## Objectifs pédagogiques

- Développer une application graphique avec **Qt Widgets**
- Concevoir un **modèle objet** (livre, pages, choix, conditions, état du joueur)
- **Sauvegarder et charger** des données en **JSON**
- **Générer un site web** à partir de l'application
- Travailler en équipe avec **Git** (GitLab de l'IUT)

---

## Fonctionnalités

### Édition
- Éditeur de **texte riche** : gras, italique, police, couleur, surlignage, alignements
- Insertion d'**images**, de **listes** et de **liens**
- Annuler / rétablir, couper / copier / coller, zoom, affichage du code HTML
- Gestion **multi-pages** (ajout / suppression de pages)

### Structure du livre
- **Liens entre les pages** qui portent des effets, par exemple :
  `page3.html#pv=-10;objet=Epee` fait perdre 10 PV et donne une épée
- **Choix sous condition** : objet possédé ou page déjà visitée
- **Vérification de la cohérence** : pages jamais accessibles, liens vers une page inexistante

### Lecture (mode jeu)
- **Points de vie**, **expérience**, **inventaire**
- Détection des fins : victoire, défaite, PV à zéro
- Boutons **Continuer** et **Retour** (avec restauration de l'état précédent)

### Sauvegarde et export
- Enregistrement / ouverture au format **JSON**
- **Export d'un site web complet** : une page HTML par page du livre + une page d'accueil avec une **carte interactive** (Leaflet)
- Sur le site exporté, l'état du joueur est conservé d'une page à l'autre avec le **localStorage** du navigateur
- **Export PDF** et aperçu avant impression

---

## Organisation du code

| Fichier | Rôle |
|---|---|
| `main.cpp` | Point d'entrée |
| `mainwindow.h / .cpp / .ui` | Fenêtre principale à onglets : Édition, Lecture, Paramètres |
| `fenetrerun.h / .cpp / .ui` | Fenêtre de lecture du livre |
| `livre.h / .cpp` | Le livre : pages, sérialisation JSON |
| `page.h / .cpp` | Une page : titre, contenu HTML, choix |
| `choix.h / .cpp` | Un choix : page cible et effets |
| `condition.h / .cpp` | Conditions d'accès à un choix |
| `EtatJoueur.h` | PV, XP et objets du joueur |
| `ressources.qrc`, `Icones/` | Icônes de l'interface |
| `Livre/` | Exemple de livre : *La Caverne Maudite* |

---

## Lancer le projet

1. Installer **Qt 6** et **Qt Creator** (ou CMake)
2. Ouvrir `CMakeLists.txt` dans Qt Creator
3. Compiler et lancer
4. Pour tester : **Fichier → Ouvrir**, puis choisir `Livre/La_Caverne_Maudite.json`

---

## Organisation du travail

Projet réalisé en groupe de 3 : **Tristan Muller**, **Yann Madry** et **Thomas Bonnefoy**.
Le code a été versionné sur le GitLab de l'IUT.

---

## Documents

- `docs/dossier-projet.docx` : manuel utilisateur, description des fonctionnalités et aspects techniques

---

## Suite du projet

- éditeur visuel du graphe des pages (glisser-déposer)
- thèmes graphiques supplémentaires pour l'export web
- tests unitaires du modèle (livre, choix, conditions)

---

## Auteur

**Tristan Muller** - BUT Informatique, IUT Lyon 1 (Bourg-en-Bresse)
[Portfolio](https://tristanmuller007.github.io/Portfolio/) · [GitHub](https://github.com/tristanmuller007)
