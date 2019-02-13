<!-- $theme: gaia -->

<!-- $size: 16:9 -->
# Présentation projet intégrateur

---

![center](https://upload.wikimedia.org/wikipedia/commons/c/cf/Aoe_fuchs.png)

- RTS Version simplifié
- Multi platforme
- Multijoueur
- Compétitif 1vs1

---

## Version simplifié

- Reduire la charge de travail
- Plus accessible

---

## Multi Platforme

- Godot
- Separation du noyau / application graphique

---

## Multijoueur

- Noyau en Go
- gRPC -> protobuf
- Creation d'instance avec k8s

![center](https://grpc.io/img/landing-2.svg)

---

## Jouer avec des amis

- Création de salons
- Jouer en coopération

---

## Classement

- Jouer avec des personnes de son niveau
- Divisions
- Progresser 

---

# Répartion du travail

- Equipe front
- Equipe backend
- Equipe réseaux
- ![center](graph.png)

---

## Equipe front

- IHM
- UI
- Modélisation
- Animation

---

## Equipe backend

- Créer les interactions entre la partie et les joueurs
	* Gestion des interaction
	* Garant de l'intégrité du jeu
	* Création des statistiques

---

## Equipe réseaux

- Faire communiquer l'application serveur et l'application client
- Deployer l'application serveur
- Matchmaking
- Créer le système de classement

---

# Divers

- gitlab
- ganttlab

---

## gitlab

- groupe
- Milestones
- issues

---

# Extensions

- Jouer avec des amis --> lobby
- Sytème de rangs
- Choix de civilisations
- 2vs2
- Plusieurs cartes

---

## Annexe

### https://git.unistra.fr/AOEINT
