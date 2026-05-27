# Lightsaber Referee App (Android)

Application Android développée en Kotlin pour l’arbitrage de combats en temps réel.

Projet réel utilisé en club (code privé)

---

## Contexte

Application développée pour répondre à un besoin réel d’arbitrage en club, avec des contraintes de rapidité, lisibilité et fiabilité en situation de combat.

## Fonctionnalités principales

- Création et gestion de combattants
- Sélection des combattants avant combat
- Gestion des manches
- Score en temps réel
- Attribution de points : +1, +2, -1, -2
- Timer configurable : 1 minute / 1 minute 30
- Gestion des égalités
- Gestion des pénalités par cartons
- Sauvegarde de l’historique des combats
- Détail d’un combat terminé
- Statistiques par combattant :
  - combats
  - victoires
  - défaites
  - égalités
  - points donnés
  - points reçus
  - manches gagnées / perdues / égalité
  - ratios
- Favoris

---

## Stack technique

- Kotlin
- Jetpack Compose
- Clean Architecture
- Room
- Hilt

## Aperçu

### Arbitrage — début de combat
![Arbitrage - Début de combat](screenshots/referee-fight-start.png)

### Arbitrage — combat en cours
![Arbitrage - Combat en cours](screenshots/referee-fight-progress.png)

### Arbitrage — combat avec pénalité
![Arbitrage - Combat avec pénalité](screenshots/referee-fight-with-penalty.png)

### Ajout d’un combattant
![Ajout d’un combattant](screenshots/add-fighter.png)

### Liste des combattants
![Liste des combattants](screenshots/fighters-list.png)

### Profil d’un combattant
![Profil d’un combattant](screenshots/fighter-detail1.png)

### Statistiques avancées d’un combattant
![Statistiques avancées d’un combattant](screenshots/fighter-detail2.png)

### Historique des combats
![Historique des combats](screenshots/match-history1.png)

### Historique des combats — autre état
![Historique des combats - autre état](screenshots/match-history2.png)

### Écran de pénalité jaune
![Écran de pénalité jaune](screenshots/yellow-penalty.png)

### Fin de combat
![Fin de combat](screenshots/combat-end.png)
## Architecture

Application structurée selon les principes de Clean Architecture avec séparation des responsabilités.

- Data layer : Room (DAO, Database), repositories avec interfaces  
- Domain layer : modèles métier + use cases découplés  
- UI layer : ViewModel, UI State, Jetpack Compose  
- Injection de dépendances avec Hilt  
- Organisation des use cases via des containers pour simplifier l’injection et structurer la logique métier  

Logique métier encapsulée (gestion des combats, scores, statistiques)  
Séparation stricte des responsabilités pour garantir testabilité et maintenabilité  

---

### Data Layer
![Data](architecture/data-layer.png)

- Room (DAO, Database)
- Repositories avec interfaces

---

### Domain Layer
![Domain](architecture/domain-layer.png)

- Modèles métier (Warrior, Statistics)
- Use cases organisés par domaine
- Containers de use cases (WarriorUseCases, StatisticsUseCases)

---

### UI Layer
![UI](architecture/ui-layer.png)

- ViewModel et UI State
- Jetpack Compose
- Composants UI réutilisables

---

### Core / Utils
![Utils](architecture/utils.png)

- Conversion Bitmap ↔ Base64
- Détection device (tablet / mobile)
- Logique partagée (calculs statistiques)

---

## Points techniques

- Application conçue pour un usage réel
- Gestion d’état complexe en temps réel
- Composants UI dynamiques
- Encapsulation de la logique métier
- Architecture modulaire facilitant la maintenabilité

---

## Évolution

Application initialement développée en XML puis migrée vers Jetpack Compose.

---

## Note

Le code source complet n’est pas public car utilisé dans un cadre réel.

Ce dépôt présente l’architecture et les fonctionnalités développées.
