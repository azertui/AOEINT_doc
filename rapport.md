# Introduction

Ce projet nous permet d'appliquer les compétences que nous avons acquéri durant notre licence.
Il s'agit de créer un jeux multijoueur et en temps réel reprenant un jeux des années 1980-1990.


# Contexte

Les CMI images ont deja utilisés utilisé unity pour faire un petit jeux durant le S5.

# Choix du jeux

Nous avons fait un brainstorming pour trouver le jeux qui serait le plus adapter.
Les idées tendaient vers un RTS.
Après reflexions, nous avons fini par choisir age of empire car cela motivé tous les membres de l'équipe, et une version aléger nous parassait accessible.

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

#### Godot

# Organisation

## Formations des équipes

### Front

### Noyaux

### Réseaux

## Répartition des taches

### Gitlab

#### Issues

#### Pull request

## Discussions

### Discord

## CI / CD

### gitlab CI

### Webhook gitlab

### mirroir github / docker cloud



# Developement

## git

### branches


# Deploiement

## Kubernetes

## HA

## Montée en charge



# Test

## Go test

### Data race



