




## TP : Authentification personnalisée avec Spring Security



**Objectif du TP**


Ce TP a pour but de comprendre et personnaliser le mécanisme d’authentification fourni par Spring Security.
L'objectif final est de remplacer la page de connexion par défaut par un formulaire HTML personnalisé, tout en gérant :

- l’authentification via un formulaire dédié,

- les erreurs de connexion,

- la redirection après succès ou échec,

- la déconnexion,

- l’accès aux pages en fonction du rôle de l’utilisateur.

- Ce TP repose sur la configuration du TP précédent (authentification en mémoire).

## Compétences visées

À la fin du TP, l’étudiant doit être capable de :

- décrire le fonctionnement complet du flux d’authentification Spring Security,

- configurer un formulaire de login personnalisé,

- gérer les redirections après connexion et les erreurs d’authentification,

- comprendre l’usage de HttpSecurity, UserDetailsService, SecurityFilterChain,

- implémenter la déconnexion,

- contrôler l’accès aux pages selon les rôles (USER/ADMIN).

## Étape 1 : Préparation du projet

- Le projet contient les dépendances suivantes :

- Web (spring-boot-starter-web)

- Sécurité (spring-boot-starter-security)

- Moteur de templates (spring-boot-starter-thymeleaf)

- Devtools pour le rechargement automatique

**La structure du projet est organisée en :**

- config : configuration de Spring Security



- web : contrôleurs gérant les vues

- templates : pages HTML Thymeleaf

## Étape 2 : Comprendre le flux d’authentification

**Le flux d’authentification se déroule comme suit :**

- L’utilisateur tente d’accéder à une page protégée.

- Spring Security intercepte la requête via la SecurityFilterChain.

- L’utilisateur non authentifié est redirigé vers la page /login.

- Le formulaire de login envoie les identifiants à une URL dédiée.

- Spring Security vérifie les identifiants via le UserDetailsService.

**En cas de succès :**

- l’utilisateur est authentifié,

- une session est créée,

- il est redirigé vers /home.

- En cas d'échec, il est renvoyé vers /login?error=true.

## Étape 3 : Configuration de Spring Security

**La configuration définit :**

- les utilisateurs en mémoire (admin et user),

- les règles d’accès par rôle,

- la page de login personnalisée,

- l’URL de traitement du formulaire,

- la redirection en cas de succès ou d’échec,

- la gestion de la déconnexion.

## Étape 4 : Contrôleur des vues

**Un contrôleur unique gère toutes les pages HTML :**

- /login : page d’authentification

- /home : page d’accueil après connexion

- /user/dashboard : espace utilisateur

- /admin/dashboard : espace administrateur

- Spring Security contrôle l’accès selon les règles configurées.

## Étape 5 : Formulaire de login personnalisé

**Une page HTML dédiée permet :**

- de saisir les identifiants,

- d'afficher un message en cas d’erreur,

- d'afficher un message après déconnexion,

- d’envoyer le formulaire à Spring Security via l’URL configurée.

- Le formulaire est stylisé pour améliorer l’expérience utilisateur.

## Étape 6 : Pages associées aux rôles

**Trois pages sont créées :**

- page d’accueil après connexion,

- page utilisateur,

- page administrateur.

- Chacune contient un lien ou un bouton permettant de se déconnecter proprement.

## Gestion de la déconnexion

La déconnexion est effectuée via un formulaire POST pour respecter les règles CSRF de Spring Security.
Après déconnexion, l’utilisateur est redirigé vers /login?logout=true.




https://github.com/user-attachments/assets/de4e2392-88d5-47df-a519-11b2af805e54









**Objectif du TP**


Ce TP a pour but de comprendre et personnaliser le mécanisme d’authentification fourni par Spring Security.
L'objectif final est de remplacer la page de connexion par défaut par un formulaire HTML personnalisé, tout en gérant :

- l’authentification via un formulaire dédié,

- les erreurs de connexion,

- la redirection après succès ou échec,

- la déconnexion,

- l’accès aux pages en fonction du rôle de l’utilisateur.

- Ce TP repose sur la configuration du TP précédent (authentification en mémoire).

## Compétences visées

À la fin du TP, l’étudiant doit être capable de :

- décrire le fonctionnement complet du flux d’authentification Spring Security,

- configurer un formulaire de login personnalisé,

- gérer les redirections après connexion et les erreurs d’authentification,

- comprendre l’usage de HttpSecurity, UserDetailsService, SecurityFilterChain,

- implémenter la déconnexion,

- contrôler l’accès aux pages selon les rôles (USER/ADMIN).

## Étape 1 : Préparation du projet

- Le projet contient les dépendances suivantes :

- Web (spring-boot-starter-web)

- Sécurité (spring-boot-starter-security)

- Moteur de templates (spring-boot-starter-thymeleaf)

- Devtools pour le rechargement automatique

**La structure du projet est organisée en :**

- config : configuration de Spring Security

- web : contrôleurs gérant les vues

- templates : pages HTML Thymeleaf

## Étape 2 : Comprendre le flux d’authentification

**Le flux d’authentification se déroule comme suit :**

- L’utilisateur tente d’accéder à une page protégée.

- Spring Security intercepte la requête via la SecurityFilterChain.

- L’utilisateur non authentifié est redirigé vers la page /login.

- Le formulaire de login envoie les identifiants à une URL dédiée.

- Spring Security vérifie les identifiants via le UserDetailsService.

**En cas de succès :**

- l’utilisateur est authentifié,

- une session est créée,

- il est redirigé vers /home.

- En cas d'échec, il est renvoyé vers /login?error=true.

## Étape 3 : Configuration de Spring Security

**La configuration définit :**

- les utilisateurs en mémoire (admin et user),

- les règles d’accès par rôle,

- la page de login personnalisée,

- l’URL de traitement du formulaire,

- la redirection en cas de succès ou d’échec,

- la gestion de la déconnexion.

## Étape 4 : Contrôleur des vues

**Un contrôleur unique gère toutes les pages HTML :**

- /login : page d’authentification

- /home : page d’accueil après connexion

- /user/dashboard : espace utilisateur

- /admin/dashboard : espace administrateur

- Spring Security contrôle l’accès selon les règles configurées.

## Étape 5 : Formulaire de login personnalisé

**Une page HTML dédiée permet :**

- de saisir les identifiants,

- d'afficher un message en cas d’erreur,

- d'afficher un message après déconnexion,

- d’envoyer le formulaire à Spring Security via l’URL configurée.

- Le formulaire est stylisé pour améliorer l’expérience utilisateur.

## Étape 6 : Pages associées aux rôles

**Trois pages sont créées :**

- page d’accueil après connexion,

- page utilisateur,

- page administrateur.

- Chacune contient un lien ou un bouton permettant de se déconnecter proprement.

## Gestion de la déconnexion

La déconnexion est effectuée via un formulaire POST pour respecter les règles CSRF de Spring Security.
Après déconnexion, l’utilisateur est redirigé vers /login?logout=true.




https://github.com/user-attachments/assets/de4e2392-88d5-47df-a519-11b2af805e54








