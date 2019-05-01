# Introduction

Ce projet nous permet d'appliquer les compétences que nous avons acquises durant notre licence, dans les différents domaines étudiés, notamment l'image et le réseau en CMI.
Il s'agit de créer un jeu multijoueur en temps réel, reprenant un jeux des années 1980-1990.


# Contexte

Les CMI en option Imagerie ont été amenés à utiliser un moteur de jeu 3D, ici Unity, lors d'un projet au semestre 5. 
Cette matière a permis d'approcer l'utilisation de scripts et la manipulation de l'interface de Unity. Ces connaissance préalables ont permis d'aborder plus rapidement la conception du jeu, ainsi de connaître la solutions à certains problèmes auxquels ils auraient pu faire face auparavant.
En choisissant d'utiliser Unity plutôt qu'un moteur de jeu inconnu des CMI Image du groupe, il a été posible d'avancer plus vite dans l'ensemble de la conception du jeu.

# Choix du jeux

Un premier brainstorming a été réalisé lors des réunions de début, afin de trouver le jeu le plus adapté aux demandes et contraintes du sujet.
Les avis se sont majoritairement dirigés vers un Real Time Strategy (RTS) game, soit un jeu de stratégie en temps réel.
Après reflexion, nous avons fini par choisir Age Of Empire, car cela motivait tous les membres de l'équipe, et qu'une version alégée nous parassait accessible.

# Conception du Jeux

Pour concevoir le jeux, nous nous sommes réuni plusieurs fois pour choisir les technologies et l'architecture du projet.

## Technologie

Un des premiers problème recontrer était l'hétérogénéité entre les compétence techniques.
Nous avons du faire des compromis pour que tous le monde puisse progresser dans de bonne conditions

### Langage de programmation

Pour l'instance de jeux, nous avions hésiter entre JAVA, python et GO.
JAVA étant lourd et en voix d'instinction il restait python et GO.
Go nous a parru plus adapter car il ressemble fortement au C avec les avantages:
* d'etre compilable
* d'integrer des outils de test
* d'integrer une gestion des dépendances
* d'integrer une documentation
* s'integre très bien à une architecture micro-service

## Architecture

Après avoir fait le tour des capacités des membres, nous nous sommes tournés vers une achitecture micro services.

### Micro service

L'avantage d'une architecture micro-service est:
* l'indépendance entre les services
* Chaque service contient une quantité de code raisonable et facilement assimilable
* On peut augmenter la robustesse de l'application en dupliquant uniquement les services les plus solicités.


### API authentification et d'information sur les lobbies

Pour ce projet, nous avons décidé de choisir de faire une api GraphQL pour se connecter/enregister et obtenir la liste des serveurs disponibles.

#### GraphQL

GraphQL est un language créer par Facebook, contrairement à une API restful, on créer un schema derequete, puis le serveur l'analyse et renvoie les informations demandés.
De plus le projet appolo server permet de monter une API graphql très simplement et rapidement

#### Knex / bookshelf

Nous avons choisi d'utiliser un ORM pour la base de donnée contenant les informations sur les partie et les joueurs.


### API de classement

Pas faite


### Instance de partie

Les instances de partie sont écritent en GO et conteneuriser comme les autres services grace à docker.
Cela permetra à terme de générer une partie à la demande et de la supprimer facilement.

### Client

Concernant le client, nous hésitions en GOdot et unity

#### Unity

Unity est un moteur de jeux propriétaire possédant un nombre enorme d'assets permetant de construire un jeux rapidement sans beaucoup de conaissances.

#### Godot

Godot est un moteur de jeux open source et très puissant, il est léger et facilement intégrable avec git.
Malheuresement Adrien voulait absolument unity.

# Organisation

Pour créer le jeux dans les meilleures conditions, il a fallu diviser le projet en plusieurs modules

## Formations des équipes

La formation des équipes est venu naturellement. En effet les CMI images forment l'équipe front car ils ne sont pas très à l'aise à la programmation dure.

### Front

L'équipe front est chargé de déveloper le client.
Elle est composée d'Adrien, Chloé et Marie.

### Noyaux

L'équipe noyaux est chargé de développer le noyaux. E

### Réseaux

L'équipe réseaux est chargé de faire le lien entre le client et l'instance de la partie.

## Répartition des taches

La répartition des taches se fait grâce à gitlab, les issues sont créés et attribué ou choisi par les personnes disponibles.
Ce système permet de d'attribuer des taches correspondantes aux personnes augmentant ainsi la productivité.

### Gitlab

L'utilisation de gitlab est très agréable, contrairement à github, la version gratuite contient un large pannel de fonctionnabilités.

#### Issues

Les issues nous permettent de demander des features et de déclarer qu'on travail sur une feature.

#### Pull request

Lorsqu'une branche est stable, c'est à dire qu'elle passe les tests de l'intégration, une Pull request est créé.
Elle est validée après un test effectué par un membre et après avoir passé tout les test de l'intégration continu.

## Discussions

Les issues sont fort pratique, hélas pour des petites question technique il est utilise d'utiliser de la communication sous forme de chat.

### Discord

Nous avons choisi discord comme logiciel de chat car il permet de faire des groupes d'utilisateurs et différents salons textuel et vocaux.

## CI / CD

Pour pouvoir garantir un maximum de stabilité, à chaque publication de commit, des scripts de test sont lancé sur des runner gitlab.

### gitlab CI

Gitlab permet grace au fichier .gitlab-ci.yaml de déclarer un pipeline qui peut tester, publier et deployer des solutions logiciels

### Webhook gitlab

Lorsqu'il y a un évenement sur un des projet git du groupe gitlab AOEINT, un message apparait dans le salon CI du discord, cela permet de prendre connaissance d'un commit ou d'une issue.

### mirroir github / docker cloud

L'instance gitlab de l'université de possède pas de registry docker.
Dockercloud perme
Dockercloud n'est pas compatible avec gitlab, pour pouvoir profiter de la ci il a falu faire un mirroir github.

# Developement

Le developement à était compliqué par le faite que tous le monde à un OS différent.

## S'adapter aux configs

Il a falu des heures de labeur pour installer go, unity et des dépendances sur chaques machines.


## docker

Pour palier à ce problème, l'utilisation de docker à permis de faciliter le dévelopement.
Par ailleurs cela à était long et plusieurs personnes ont du passer de windows familial à windows pro.

## git

Pour developer, l'utilisation de git est obligatoire parce que c'est bien

### branches

Pour le pas se marcher dessus et travailler en parallèle chaque feature était déveloper sur des
branches indépendantes

#### b -> develop

Dès qu'une feature est jugée terminé. Une pull request est ouverte pour merge les modifications.
Cela permet d'intégrer les features au fur et à mesure et d'avancer par itérations

# Deploiement

## Kubernetes

## HA

## Montée en charge



# Test

## Go test

### Data race



