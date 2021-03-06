# Rust

#### Table des matières

* [Introduction](#introduction)
* [Programmer un jeu de nombre à deviner](#programmer-un-jeu-de-nombre-à-deviner)
* [Concepts communs de programmation](#concepts-communs-de-programmation)
    + [Variables et mutabilité](#variables-et-mutabilité)
    + [Types de données](#types-de-données)
    + [Fonctions](#fonctions)
    + [Commentaires](#commentaires)
    + [Contrôle de flux](#contrôle-de-flux)
* [Comprendre la propriété](#comprendre-la-propriété)
    + [Qu'est-ce que la propriété](#quest-ce-que-la-propriété)
    + [Référence et emprunt](#référence-et-emprunt)
    + [Type slice](#type-slice)
* [Utiliser Struct pour structurer des informations](#utiliser-struct-pour-structurer-des-informations)
    + [Définir et instancier des structures](#définir-et-instancier-des-structures)
    + [Un exemple de programme utilisant des structures](#un-exemple-de-programme-utilisant-des-structures)
    + [Syntaxe de méthode](#syntaxe-de-méthode)
* [Enums et Correspondance de motifs](#enums-et-correspondance-de-motifs)
    + [Définir un Enum](#définir-un-enum)
    + [L'opérateur de correspondance de contrôle de flux](#lopérateur-de-correspondance-de-contrôle-de-flux)
    + [Contrôle de flux concis avec if let](#contrôle-de-flux-concis-avec-if-let)
* [Gérer des projets avec Packages, Crates et Modules](#gérer-des-projets-avec-packages-crates-et-modules)
    + [Packages et Crates](#package-et-crates)
    + [Définir des modules pour contrôler l'étendue et le privé](#définir-des-modules-pour-contrôler-létendue-et-le-privé)
    + [Chemins pour désigner un item du module Tree](#chemins-pour-désigner-un-item-du-module-tree)
    + [Apporter des chemins dans l'étendue à l'aide de mots-clefs](#apporter-des-chemins-dans-létendue-à-laide-de-mots-clefs)
    + [Séparer des modules dans différents fichiers](#séparer-des-modules-dans-différents-fichiers)
* [Collections communes](#collections-communes)
    + [Stocker des listes de valeurs à l'aide de vecteurs](#stocker-des-listes-de-valeurs-à-laide-de-vecteurs)
    + [Stocker du texte encodé en UTF-8 à l'aide de chaînes](#stocker-du-texte-encodé-en-utf-8-à-laide-de-chaînes)
    + [Stockage clefs-valeurs dans une table de hashage](#stocktage-clefs-valeurs-dans-une-table-de-hashage)
* [Gestion d'erreurs](#gestion-derreurs)
    + [Erreurs irrécupérables à l'aide de panic!](#erreurs-irrécupérables-à-laide-de-panic)
    + [Erreurs récupérables à l'aide de Result](#erreurs-récupérables-à-laide-de-result)
    + [Panic! ou ne pas panic!](#panic-ou-ne-pas-panic)
* [Types génériques, Traits et Lifetimes](#types-génériques-traits-et-lifetimes)
    + [Types de données génériques](#types-de-données-génériques)
    + [Traits : Définir des comportements partagés](#traits--définir-des-comportements-partagés)
    + [Valider des références à l'aide de Lifetimes](#valider-des-références-à-laide-de-lifetimes)
* [Écrire des tests automatisés](#écrire-des-tests-automatisés)
    + [Comment écrire des tests](#comment-écrire-des-tests)
    + [Contrôler l'exécution des tests](#contrôler-lexécution-des-tests)
    + [Organisation des tests](#organisation-des-tests)
* [Un projet E/S : Construire un programme ligne de commande](#un-projet-es--construire-un-programme-ligne-de-commande)
    + [Accepter des arguments de ligne de commande](#accepter-des-arguments-de-ligne-de-commande)
    + [Lire un fichier](#lire-un-fichier)
    + [Refactoriser : modularité et gestion d'erreurs](#refactoriser--modularité-et-gestion-derreurs)
    + [Développer la bibliothèque : développement orienté test](#développer-la-bibliothèque--développement-orienté-test)
    + [Travailler avec les variables d'environnement](#travailler-avec-les-variables-denvironnement)
    + [Écrire des messages vers stderr](#écrire-des-messages-vers-stderr)
* [Caractéristiques fonctionnelles : Itérateurs et clôtures](#caractéristiques-fonctionnelles--itérateurs-et-fermetures)
    + [Clôtures : Fonctions anonymes capturant leur environnement](#clôtures--fonctions-anonymes-capturant-leur-environnement)
    + [Traiter une série d'items à l'aide d'itérateurs](#traiter-une-série-ditems-à-laide-ditérateurs)
    + [Améliorer le projet E/S](#améliorer-le-projet-es)
    + [Comparer la performance des boucles aux itérateurs](#comparer-la-performance-des-boucles-aux-itérateurs)
* [Plus à propos de Cargo et de Crates.io](#plus-à-propos-de-cargo-et-de-cratesio)
    + [Personnaliser les builds à l'aide des profils de release](#personnaliser-les-builds-à-laide-des-profils-de-release)
    + [Publier un Crate sur Crates.io](#publier-un-crate-sur-cratesio)
    + [Espaces de travail Cargo](#espaces-de-travail-cargo)
    + [Installer des binaires depuis Crates.io avec cargo install](#installer-des-binaires-depuis-cratesio-avec-cargo-install)
    + [Étendre Cargo à l'aide de commandes personnalisées](#étendre-cargo-à-laide-de-commandes-personnalisées)
* [Pointeurs intelligents](#pointeurs-intelligents)
    + [Utiliser Box pour pointer vers la donnée sur le tas](#utiliser-box-pour-pointer-vers-la-donnée-sur-le-tas)
    + [Pointeurs intelligents : références avec deref Trait](#pointeurs-intelligents--références-régulières-avec-deref-trait)
    + [Exécuter du code au nettoyage avec drop Trait](#exécuter-du-code-au-nettoyage-avec-drop-trait)
    + [Rc, le pointeur intelligent compté référence](#rc-le-pointeur-intelligent-compté-référence)
    + [RefCell et le motif de mutabilité interne](#refcell-et-le-motif-de-mutabilité-interne)
    + [Les cycles de références possibilités de fuites mémoires](#les-cycles-de-références-possibilités-de-fuites-mémoires)
* [Concurrence](#concurrence)
    + [Utiliser des threads pour exécuter du code simultanément](#utiliser-des-threads-pour-exécuter-du-code-simultanément)
    + [Passage de messages transférer la donnée entre threads](#passage-de-messages-transferer-la-donnée-entre-threads)
    + [Concurrence et états partagés](#concurrence-et-états-partagés)
    + [Concurrence étendue à l'aide des traits Sync et Send](#concurrence-étendue-à-laide-des-traits-sync-et-send)
* [Programmation orienté objet en Rust](#programmation-orienté-objet-en-rust)
    + [Caractéristiques des langages orientés objet](#caractéristiques-des-langages-orientés-objet)
    + [Traits objets permettant différents types aux valeurs](#Traits-objets-permettant-différents-types-aux-valeurs)
    + [Implémenter un motif de design orienté objet](#implémenter-un-motif-de-design-orienté-objet)
* [Correspondances et motifs](#correspondances-et-motifs)
    + [Usage des motifs](#usage-des-motifs)
    + [Réfutabilité : Si un motif échoue à la correspondance](#réfutabilité--si-un-motif-échoue-à-la-correspondance)
    + [Syntaxe de motif](#syntaxe-de-motif)
* [Fonctionnalités avancées](#fonctionnalités-avancées)
    + [Unsafe Rust](#unsafe-rust)
    + [Traits avancés](#traits-avancés)
    + [Types avancés](#types-avancés)
    + [Fonctions et clôtures avancées](#fonctions-et-clôtures-avancées)
    + [Macros](#macros)
* [Projet final : Serveur web multi-threadé](#projet-final--serveur-web-multi-threadé)
    + [Construire un serveur web simple](#construire-un-serveur-web-simple)
    + [Multi-threader le serveur web](#multi-threader-le-serveur-web)
    + [Arrêt et nettoyage](#arrêt-et-nettoyage)
* [Appendice](#appendice)
    + [A. Mots-clefs](#a-mots-clefs)
    + [B. Opérateurs et symboles](#b-opérateurs-et-symboles)
    + [C. Traits dérivables](#c-traits-dérivables)

## Introduction

## Programmer un jeu de nombre à deviner

## Concepts communs de la programmation

### Variables et mutabilité

### Types de données

### Fonctions

### Commentaires

### Contrôle de flux

## Compendre la propriété

### Qu'est-ce que la propriété

### Références et emprunt

### Type slice

## Utiliser Struct pour structurer des informations

### Définir et instancier des structures

### Un exemple de programme utilisant des structures

### Syntaxe de méthode

## Enums et correspondance de motifs

### Définir un Enum

### L'opérateur de correspondance de contrôle de flux

### Contrôle de flux concis avec if let

## Gérer des projets avec Packages, Crates et Modules

### Packages et Crates

### Définir des modules pour contrôler l'étendue et le privé

### Chemins pour désignner un item dans le module Tree

### Apporter des chemins dans l'étendue à l'aide de mots clefs

### Séparer des modules dans différents fichiers

## Collections communes

### Stocker des listes de valeurs à l'aide de vecteurs

### Stocker du texte encodé en UTF-8 à l'aide de chaînes

### Stockage clefs-valeurs dans une table de hashage

## Gestion d'erreurs

### Erreurs irrécupérables à l'aide de panic!

### Erreurs récupérables à l'aide de Result

### Panic! ou ne pas panic!

## Types génériques, Traits et Lifetimes

### Types de données génériques

### Traits : Définir des comportements partagés

### Valider des références à l'aide de Lifetimes

## Écrire des test automatisés

### Comment écrire des tests

### Contrôler l'exécution des tests

### Organiser des tests

## Un projet E/S : Construire un programme ligne de commande

### Accepter des arguments de ligne de commande

### Lire un fichier

### Refactoriser : modularité et gestion d'erreurs

### Développer la bibliothèque : développement orienté test

### Travailler avec des variables d'environnement

### Écrire des messages vers stderr

## Caractéristiques fonctionnelles : Itérateurs et clôtures

### Clôtures : Fonctions anonymes capturant leur environnement

### Traiter une série d'items à l'aide d'itérateurs

### Améliorer le projet E/S

### Comparer la performance des boucles aux itérateurs

## Plus à propos de Cargo et de Crates.io

### Personnaliser les builds à l'aide des profils de release

### Publier un crate sur Crates.io

### Espaces de travail Cargo

### Installer des binaires depuis Crates.io avec cargo install

### Étendre Cargo à l'aide de commandes personnalisées

## Pointeurs intelligents

### Utiliser Box pour pointer vers la donnée sur le tas

### Pointeurs intelligents : références avec deref Trait

### Exécuter du code au nettoyage avec drop Trait

### Rc, le pointeur intelligent compté réference

### RefCell et le motif de mutabilité interne

### Les cycles de références possibilité de fuites mémoires

## Concurrence

### Utiliser des threads pour exécuter du code simultanément

### Passage de messages transférer la donnée entre threads

### Concurrence et états partagés

### Concurrence étendue à l'aide des traits Sync et Send

## Programmation orienté objet en Rust

### Caractéristiques des langages orientés objet

### Traits objets permettant différents types aux valeurs

### Implémenter un motif de design orienté objet

## Correspondances et motifs

### Usage des motifs

### Réfutabilité : Si un motif échoue à la correspondance

### Syntaxe de motif

## Fonctionnalités avancées

### Unsafe Rust

### Traits avancés

### Types avancés

### Fonctions et clôtures avancées

### Macro

## Projet final : Serveur web multi-threadé

### Construire un serveur web simple

### Multi-threader le serveur web

### Arrêt et nettoyage

## Appendice

### A. Mots-clefs

### B. Opérateurs et symboles

### C. Traits dérivables
